# Certificate Authority Authorization (CAA) check command

The CAA check command is as follows:

````text
bilal.ashraf@192 go-ca % ./go-ca -h                                                                                                 
go-ca is a command line CA for PKI operations

Usage:
  go_ca [command]

Available Commands:
  caa_check   CAA check of domain name
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
bilal.ashraf@192 go-ca % ./go-ca caa_check -h
CAA check of domain name against provided CA name

Usage:
  go_ca caa_check [flags]

Flags:
      --ca_name string              name of the CA e.g. digicert.com, letsencrypt.org, ssl.com and so on
      --domain_name string          domain or wildcard domain. It's value must be in qoutes
  -h, --help                        help for caa_check
      --resolver_host_port string   resolver host and port of format e.g. 8.8.8.8:53
  -v, --version                     version for caa_check
````