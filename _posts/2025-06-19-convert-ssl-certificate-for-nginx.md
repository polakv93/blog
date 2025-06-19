---
title: Converting SSL Certificate for Nginx 🔐
date: 2025-06-19 12:00:00+0100
categories: [devops]
tags: [nginx, ssl, certificate, openssl, devops]
---

Nginx native use two files for handling ssl certificate in `nginx.conf`.

```conf
ssl_certificate     /etc/ssl/cert.pem;
ssl_certificate_key /etc/ssl/private.key;
```

But most of the vendors sells certificate in `.pfx` format with password,  
so to convert we first needs to install `openssl` and then extract the private key
```bash
openssl pkcs12 -in certificate.pfx -nocerts -nodes -out private.key
```
and extract certificate key via
```bash
openssl pkcs12 -in certificate.pfx -clcerts -nokeys -out cert.pem
```

Next replace old files with new and restart nginx :D

Of course better is to use nginx certbot with let's encrypt but this is not always possible.