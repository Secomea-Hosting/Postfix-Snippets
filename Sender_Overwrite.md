# Postfix Sender Domain Overwrite
Place the following in main.cf
```cf
sender_canonical_maps = hash:/etc/postfix/canonical
```
Place the following in canonical (Replace {domain1} with the domain you want to change and {domain2} with the domain you want to change to)
```cf
@{domain1}    @{domain2}
```
Run the following commands:
```bash
sudo chmod 600 /etc/postfix/canonical
sudo postmap /etc/postfix/canonical
sudo systemctl restart postfix
```
