skycalhl.duckdns.org

```
docker run -v "/opt/letsencrypt:/etc/letsencrypt" -v "/var/log/letsencrypt:/var/log/letsencrypt" infinityofspace/certbot_dns_duckdns:latest \
   certonly \
     --non-interactive \
     --agree-tos \
     --email <your-email> \
     --preferred-challenges dns \
     --authenticator dns-duckdns \
     --dns-duckdns-token <your-duckdns-token> \
     --dns-duckdns-propagation-seconds 60 \
     -d "git1.skycalhl.duckdns.org"
```

