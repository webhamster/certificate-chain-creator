# certificate-chain-creator
**Creates certificate chains of an arbitrary length with a self-signed root CA.**

This script is based on https://github.com/pinae/certificate-chain-creator

Usage example:

```
python3 ../certchaincreator.py -d 1 --country DE --state XY --locality Ort --company-name Test --organizational-unit Bla --email 'Test@example.com' --ca-password 'cacacaca' --intermediate-password 'imimimim' example2.com -i 10
```

where `-i 10` defines the number of intermediary certificate authorities.

Full usage:

```
usage: certchaincreator.py [-h] -i INTERMEDIATES [-s KEY_SIZE] [-d DAYS]
                           [--country COUNTRY] [--state STATE] --locality
                           LOCALITY [--company-name COMPANY_NAME]
                           --organizational-unit ORGANIZATIONAL_UNIT --email
                           EMAIL --ca-password CA_PASSWORD
                           --intermediate-password INTERMEDIATE_PASSWORD
                           domain

Generate a certificate chain.

positional arguments:
  domain                Domain name without www.

optional arguments:
  -h, --help            show this help message and exit
  -i INTERMEDIATES, --intermediates INTERMEDIATES
                        Number of intermediary CAs.
  -s KEY_SIZE, --key-size KEY_SIZE
                        Size of the key in bits. 2048 bit is quite common.
                        4096 bit is more secure and the default.
  -d DAYS, --days DAYS  Validity time in days. Default is 2492 (7 years).
  --country COUNTRY     Country code with two letters. Default is DE.
  --state STATE         State or region. Default is "Some-State".
  --locality LOCALITY   City or place.
  --company-name COMPANY_NAME
                        Company name. Default is the domain.
  --organizational-unit ORGANIZATIONAL_UNIT
                        Name of your unit or team.
  --email EMAIL         Email.
  --ca-password CA_PASSWORD
                        CA key password.
  --intermediate-password INTERMEDIATE_PASSWORD
                        intermediate key password.
```
