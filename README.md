# SSLMate Certificate Installer
A GitHub action for installing an SSLMate certificate

## Inputs
### distro
The distribution being used for the build pipeline.  This distribution short name should match the name used for the distribution in this [list](https://sslmate.com/help/cmdline/install).  Example, Ubuntu 20.04 is ubuntu2004. The default is ubuntu2004 which should match the ubuntu-latest os configuration for GitHub.

### api-key
The API Key provided to you by SSLMate

### certificate-directory
The directory relative to the $HOME directory that the certificates will be installed in.  The default is `ssl_certificates`

### certificate-domain
The domain to which the SSL certificate will be applied (e.g. mydomain.com or wildcard.mydomain.com)

## certificate-key-content
The content of the domain certificate key file

## wildcard-filename
The name of the file to use for wildcard domains. For example, `wildcard.mydomain.com` instead of `*.mydomain.com`.

## Usage
# Sample
```
- uses: catchco/sslmate-certificate-installer
  with:
    distro: ubuntu2004
    api-key: 123456
    certificate-directory: ssl_certificates
    certificate-domain: wildcard.mydomain.com
    certificate-key-content: ${{ secrets.WILDCARD_MYDOMAIN_COM_KEY }}
    wildcard-filename: wildcard
```