# Key and CSR Generation Command

The Key pair and CSR generation command is as follows:

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
bilal.ashraf@192 go-ca % ./go-ca key_csr_gen -h
Generates RSA and ECDSA key pairs and optionally CSR based on provided config file
Usage:
  go_ca key_csr_gen [flags]

Flags:
      --config_file_path string   Key csr generation config file path
  -h, --help                      help for key_csr_gen
  -v, --version                   version for key_csr_gen
````