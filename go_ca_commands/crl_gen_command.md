# CRL Generation Command

The CRL generation command is as follows:

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
bilal.ashraf@192 go-ca % ./go-ca crl_gen -h 
Generates RSA and ECDSA based CRLs based on provided config files
Usage:
  go_ca crl_gen [flags]

Flags:
      --ca_settings_file_path string          Path of the CA Settings file
  -h, --help                                  help for crl_gen
      --previous_crl_file_path string         Last published CRL file path. Required only, if not the first CRL
      --revocation_entries_file_path string   Revocation entries file path, which contains revocation entries to 
                                              add/remove from the new CRL. Only required, if add/remove revocation entries from new CRL
  -v, --version                               version for crl_gen
````