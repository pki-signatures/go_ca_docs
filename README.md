# GO CA CLI Documentation

The go-ca is a command line CA utility used for generation of PKI. It includes the following features:

- Support for hardware based PKI (key pairs for PKI in PKCS#11 based hardware device)
- Support for software based PKI (key pairs for PKI in files - PEM encoded)
- RSA algorithm support (2048, 3072 and 4096 key length) in both software and hardware
- ECDSA algorithm support (P-256, P-384 and P-521 curves) in both software and hardware
- Support for multiple types of certificate e.g. TLS server, client authentication and so on based on certificate profile
- Digest algorithms (sha256, sha384 and sha512) support to sign certificates and CRLs
- X509 Certificate and CRL generation

Note:- The go-ca CLI is written 100% in Go Language.

## Go CA CLI Installation Instructions

- Pick the platform specific go-ca executable from [releases directory](./releases) and place it on your system
- Create logs directory in the same folder where go-ca executable will be placed
- Read the following guides for required configuration files
  - [Certificate Profile Settings](./docs/certificate_profile_settings.md)
  - [CA Settings](./docs/ca_settings.md)
  - [Key CSR Settings](./docs/key_csr_settings.md)
  - [PKCS#11 Settings](./docs/p11_settings.md)
  - [Subject Information Request](./docs/subject_info_request.md)
  - [Revocation Entries Settins](./docs/revocation_entries.md)
- [Sample configuration files and associated generated data based on configuration files](./test_data)