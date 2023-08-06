# Certificate Profile Settings

This file contains all the information related to certificate template of the to be issued certificate. The certificate 
profile settings file is in TOML format.

````toml
# Unique name of the certificate profile
name = "certificate_profile_full"

# Digest algorithm use to sign the certificate. Possible values are sha256, sha384 or sha512.
cert_digest_algorithm = "sha256"

# Either DELEGATED_CA_CERTIFICATE or SELF_SIGNED_CERTIFICATE_KEY_HARDWARE or SELF_SIGNED_CERTIFICATE_KEY_SOFTWARE
# must be present. The DELEGATED_CA_CERTIFICATE is used when certificate is to be issued by some CA
[DELEGATED_CA_CERTIFICATE]
# CA settings file path. This settings must be in TOML format. See ca_settings.md for more information
ca_settings_path = "<CA_SETTINGS_TOML_FILE_PATH>"

# Either DELEGATED_CA_CERTIFICATE or SELF_SIGNED_CERTIFICATE_KEY_HARDWARE or SELF_SIGNED_CERTIFICATE_KEY_SOFTWARE
# must be present. It is used when private key use to sign certificate is in HSM
[SELF_SIGNED_CERTIFICATE_KEY_HARDWARE]
# P11 settings must be present if the private key is in HSM.
p11_settings_path = "<P11_SETTINGS_TOML_FILE_PATH>"
# ID of the private key use to sign certificate.
key_id = "<KEY_ID>"

# Either DELEGATED_CA_CERTIFICATE or SELF_SIGNED_CERTIFICATE_KEY_HARDWARE or SELF_SIGNED_CERTIFICATE_KEY_SOFTWARE
# must be present. It is used when private key use to sign certificate is in software mode. The private and public
# key must be in PEM format
[SELF_SIGNED_CERTIFICATE_KEY_SOFTWARE]
private_key_path = "<PRIVATE_KEY_PATH>"
public_key_path = "<PUBLIC_KEY_PATH>"

# - If RDN is present and REQ value is present, which means value is required from subject info file otherwise error.
# see subject.info.md for more information.
# - If RDN is present and value is also present other than REQ, which means it's value will be hardcoded in every 
# issued certificate.
# - Any absent RDN means it is not required in the certificate
[SUBJECT_INFO]
commonName = "REQ"
givenName = "REQ"
surname = "REQ"
organization = "XYZ"
organizationalUnit = "Development"
organizationIdentifier = "ORD-123"
country = "REQ"
locality = "REQ"        
serialNumber = "REQ"
stateOrProvince = "REQ"
streetAddress = "REQ"
postalCode = "REQ"
custom_rdns = [
    {oid = "2.5.4.12", value = "REQ"},
    {oid = "2.5.4.13", value = "Test value"}
]

[VALIDITY_INFO]
# # Possible values are "1Y or 2MO or 3D or 6H or 4M or 5S".
# Y(years), MO(months), D(days), H(hours), M(minutes) and S(seconds).
duration = "1Y"

# If present and enabled, this extension will be added in the issued certificate
[KEY_USAGES]
# Following are the key usages that can be used here:
# digitalSignature
# nonRepudiation
# keyEncipherment
# dataEncipherment
# keyAgreement
# keyCertSign
# cRLSign
# encipherOnly
# decipherOnly
enabled = true
values = ["digitalSignature", "nonRepudiation"]

# If present and enabled, this extension will be added in the issued certificate.
[EXTENDED_KEY_USAGES]
# Following are the extended key usages that can be used here:
# Any
# ServerAuth
# ClientAuth
# CodeSigning
# EmailProtection
# TimeStamping
# OCSPSigning
# Custom OIDs
enabled = true
critical = false
values = ["ServerAuth", "ClientAuth"]

# If present and enabled, this extension will be added in the issued certificate.
[SUBJECT_ALT_NAME]
enabled = true
# If dns_names values are expected in request, then single element array with value REQ must be present
dns_names = ["test.com", "check.com"]
# If email_addresses values are expected in request, then single element array with value REQ must be present
email_addresses = ["test@test.com"]

# If present and enabled, this extension will be added in the issued certificate.
[AUTHORITY_KEY_IDENTIFIER]
enabled = true

# If present and enabled, this extension will be added in the issued certificate.
[SUBJECT_KEY_IDENTIFIER]
enabled = true

# If present and enabled, this extension will be added in the issued certificate.
[CRL_DISTRIBUTION_POINTS]
enabled = true
urls = ["http://crl.com"]

# If present and enabled, this extension will be added in the issued certificate.
[AUTHORITY_INFORMATION_ACCESS]
enabled = true
ocsp_urls = ["http://ocsp.test.com"]
cert_issuer_urls = ["http://test.com/subca1.cer"]

# If present and enabled, this extension will be added in the issued certificate.
[CERTIFICATE_POLICIES]
enabled = true
critical = true
policy_infos = [
    {policy_oid = "2.4.3.12", cps_uri = "https://cps.com", user_notice = "test certificate"},
    {policy_oid = "2.4.3.13"}
]

# If present and enabled, this extension will be added in the issued certificate.
[BASIC_CONSTRAINTS]
enabled = true
# is_ca must be true for CA certificate
is_ca = false
# path_length is only used in case of CA certificate
path_length = -1

# If present and enabled, this extension will be added in the issued certificate.
[OCSP_NO_CHECK]
enabled = true
critical = true

# If present and enabled, this extension will be added in the issued certificate.
[CUSTOM_EXTENSIONS]
extensions = [
    # The value must be base64 encoded ASN.1 structure
    {oid = "2.5.4.12", critical = false, value = "VGhpcyBpcyBqdXN0IGEgdGVzdA=="},
    {oid = "2.5.4.13", critical = false, value = "VGhpcyBpcyBqdXN0IGEgYW5vdGhlciB0ZXN0"}
]
````