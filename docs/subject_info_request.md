# Subject Information Request

This file contains Subject DN and SAN values present in request to CA for certificate issuance. Of course, the
final values will be calculated as per certificate profile. See 
[Certificate Profile Settings](certificate_profile_settings.md) for more information. The settings file is in
TOML format.

````toml
# Subject information to present in request. Any absent RDN value will not be presented in request to CA
[SUBJECT_INFO]
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

# Subject alternative name to present in request
[SUBJECT_ALT_NAME]
dns_names = ["test.com", "check.com"]
email_addresses = ["test@test.com"]
````