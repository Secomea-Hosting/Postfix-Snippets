# Postfix Domain Reject
## Sengrid
Place the following in main.cf
```cf
smtpd_sender_restrictions = check_sender_access hash:/etc/postfix/sender_access
```
Place the following in sender_access (Replace {domain} with the domain you want to block)
```cf
{domain} REJECT
```
Run the following commands:
```bash
sudo chmod 600 /etc/postfix/sender_access
sudo postmap /etc/postfix/sender_access
sudo systemctl restart postfix
```
