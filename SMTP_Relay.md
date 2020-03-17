# SMTP Relay Configuration
## Sengrid
Place the following in main.cf
```cf
smtp_sasl_auth_enable = yes
smtp_sasl_password_maps = hash:/etc/postfix/sasl_passwd
smtp_sasl_security_options = noanonymous
smtp_sasl_tls_security_options = noanonymous
smtp_tls_security_level = encrypt
header_size_limit = 4096000
relayhost = [smtp.sendgrid.net]:587
```
Place the following in sasl_passwd (Replace {key} with the API Key)
```cf
[smtp.sendgrid.net]:587 apikey:{key}
```
Run the following commands:
```bash
sudo chmod 600 /etc/postfix/sasl_passwd
sudo postmap /etc/postfix/sasl_passwd
sudo systemctl restart postfix
```
