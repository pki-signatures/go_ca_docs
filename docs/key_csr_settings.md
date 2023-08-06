# Key and CSR Settings

This file contains all the information related to key pair and optionally CSR generation. The settings file is in
TOML format.

````toml
# Unique name of the key and CSR settings.
name = "key_csr_settings_full"

# One of RSA or ECDSA must be present. 
[RSA]
# Possible values are 2048, 3072 and 4096. Only present in case of RSA
key_length = 2048

# One of RSA or ECDSA must be present.
[ECDSA]
# Possible values are secp256r1, secp384r1 or secp521r1. Only present in case of ECDSA
curve = "secp256r1"

# One of KEY_SOURCE_SOFTWARE or KEY_SOURCE_HARDWAE must be present.
[KEY_SOURCE_SOFTWARE]
# Ouput path of the software private key file. The generated private key will be in PEM format
private_key_out_path = "<PRIVATE_KEY_OUTPUT_PATH>"
# Output path of the software public key file. The generated public key will be in PEM format
public_key_out_path = "<PUBLIC_KEY_OUTPUT_PATH>"

# Only one of KEY_SOURCE_SOFTWARE or KEY_SOURCE_HARDWAE must be present.
[KEY_SOURCE_HARDWARE]
# P11 settings file path which includes module name, slot and pin.
p11_settings_path = "<P11_SETTINGS_TOML_FILE_PATH>"
# Id of the to be generated key pair in HSM.
key_id = "<KEY_ID>"
# Path of the exported public key from HSM.
public_key_out_path = "<PUBLIC_KEY_OUTPUT_PATH>"

# Only present when KEY_SOURCE_HARDWARE.
[HARDWARE_PRIVATE_KEY_TEMPLATE]
token = true 
private = true 
sensitive = true
extractable = false
decrypt = true
sign = true
unwrap = false

# Only present when KEY_SOURCE_HARDWARE.
[HARDWARE_PUBLIC_KEY_TEMPLATE]
token = true
verify = true
encrypt = true
wrap = false

# Optinally generates CSR.
[CSR]
# Digest algorithm use to sign CSR. Possible values are sha256, sha384 and sha512
csr_digest_algorithm = "sha256"
# Path of the output CSR. The CSR will be generated in PEM format
csr_out_path = "<CSR_OUTPUT_FILE_PATH>"

# Subject DN information to put in the output CSR. Any absent RDN value will not be added in CSR subject DN
[CSR_SUBJECT_INFO]
commonName = "Bilal Ashraf"
givenName = "Bilal"
surname = "Ashraf"
organization = "XYZ"
organizationalUnit = "Development"
organizationIdentifier = "ORD-123"
country = "PK"
locality = "Lahore"        
serialNumber = "1234567890"
stateOrProvince = "Punjab"
streetAddress = "301"
postalCode = "456"
custom_rdns = [
    {oid = "2.5.4.12", value = "Mr."},
    {oid = "2.5.4.13", value = "Test CSR"}
]

# Subject alternative name to put in the CSR. If required
[CSR_SUBJECT_ALT_NAME]
dns_names = ["test.com", "check.com"]
email_addresses = ["test@test.com"]
````