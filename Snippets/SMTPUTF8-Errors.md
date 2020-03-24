# SMTPUTF8 Errors

## SMPTUTF8 Bounce

### Disable SMPTUTF8
Why would you disable SMPTUTF8? You might decide to do this if your Mail provider/server does not support SMPTUTF8 and handles it in their own way.
For example Sengrid only accepts ASCII but will translate [some parameters](https://sendgrid.com/docs/API_Reference/Parse_Webhook/inbound_email.html) automatically

Place the following in main.cf to disable SMPTUTF8
```cf
smtputf8_enable = no
```

