# GratisDNS DNS Authenticator plugin for Certbot

## Installation

### Prerequisites
* Working python pip installation
* *pyotp* installed (`pip install pyotp`)
* 2FA enabled at gratisdns.dk
  * if you need the secret, scan the QR code with another app and write the url down.

### Installation steps

1. Clone this repository to a folder `certbot-dns-gratisdns`
1. Run `pip install -e certbot-dns-gratisdns`

## Configuration

Create a text file with the following content:

```
# GratisDNS credentials used by Certbot
dns_gratisdns_username = example
dns_gratisdns_password = hunter2
dns_gratisdns_otp_secret = GE4GMZJSGNRTCNJSGEZDKYZYGEZGEYZXGU3TIYRXMZTGCODFGRQWMOBSGYYDEYTE
```
## Execution

Run the following command: `sudo certbot certonly -d \*.example.com -d example.com -a certbot-dns-gratisdns:dns-gratisdns`

When prompted for the config file, enter the path to the above text file.

## About

This plugin is a fork of `certbot_dns_gehirn`.

The logic is based on [`acme.sh_dns_gratisdns`](https://github.com/zylopfa/acme.sh_dns_gratisdns).
