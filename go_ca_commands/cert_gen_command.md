# Certificate Generation Command

The certificate generation command is as follows:

````text
bilal.ashraf@192 go-ca % ./go-ca -h
go-ca is a command line CA for PKI operations
Usage:
  go_ca [command]

Available Commands:
  cert_gen    Certificate generation command
  crl_gen     CRL generation command
  help        Help about any command
  key_csr_gen Key pair and optionally CSR generation command

Flags:
  -h, --help      help for go_ca
  -v, --version   version for go_ca

Use "go_ca [command] --help" for more information about a command.
````

````text
bilal.ashraf@192 go-ca % ./go-ca cert_gen -h   
Generates RSA and ECDSA based certificates based on provided config files
Usage:
  go_ca cert_gen [flags]

Flags:
      --cert_out_file_path string       Path of the to be generated certificate including file name
      --cert_profile_file_path string   Certificate profile file path
      --csr_file_path string            CSR file path. Required for non self-signed certificates
  -h, --help                            help for cert_gen
      --subject_file_path string        Subject information request file path. If not provided, subject info in CSR is used. For self-signed certificate, this must be provided
  -v, --version                         version for cert_gen
````