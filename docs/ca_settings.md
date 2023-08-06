# CA Settings

The CA settings file contains all the information for the CA to sign the certificates and CRLs. Every CA
must have a unique CA settings file. The CA settings file is in TOML format.

````toml
# Unique name of the CA
name = "sub_ca_1"

# Either CA_KEY_SOURCE_SOFTWARE_SETTINGS or CA_KEY_SOURCE_HARDWARE_SETTINGS must be present.
[CA_KEY_SOURCE_SOFTWARE_SETTINGS]
# CA private key path. The private key must be in PEM format.
ca_private_key_path = "<CA_PRIVATE_KEY_PATH>"
# CA certificate path. The certificate must be in PEM format
ca_cert_path = "<CA_CERTIFICATE_PATH>"

# Either CA_KEY_SOURCE_SOFTWARE_SETTINGS or CA_KEY_SOURCE_HARDWARE_SETTINGS must be present.
[CA_KEY_SOURCE_HARDWARE_SETTINGS]
# P11 settings path. This settings conatins P11 module, slot and pin.
p11_settings_path = "<P11_SETTINGS_TOML_FILE_PATH>"
# CA key ID in HSM.
ca_key_id = "<CA_KEY_ID>"
# CA certificate path. The certificate must be in PEM format
ca_cert_path = "<CA_CERTIFICATE_PATH>"

# CRL publish settings
[CRL_SETTINGS]
# Digest algorithm use to sign CRL response. Possible values are sha256, sha384 and sha512.
digest_algorithm = "sha256"
# CRL validity. Possible values are "1Y or 2MO or 3D or 4M or 5S". Y(years), MO(months), D(days), M(minutes) and S(seconds)
crl_validity = "1MO"
# Path of the to be published CRL path. It publishes PEM format CRL. Time in milliseconds is appended in the CRL file name
crl_publishing_path = "<CRL_FILE_PATH>"
````