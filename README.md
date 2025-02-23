# Updates a dns recordset from AWS Route53

Simply run this command from some machine inside your LAN behind a NAT firewall
you would like to update its public ip address:

```
docker run \
  -e AWS_ACCESS_KEY_ID=XXXX \
  -e AWS_SECRET_ACCESS_KEY=YYYY \
  -e ZONEID=ZZZZZ \
  -e RECORDSET=some-name.example.com \
  --rm -i jonnyb3010/aws-route53-dynamic-update:latest
```

It can also admit the following environment variables:

* **IP**: an IP address different than the one https://ifconfig.me returns.
  Defaults to be dynamically updated.
* **DNS_SERVER**: which DNS server use to get current DNS respose to RECORDSET.
  Defaults to 8.8.8.8
* **TTL**: TTL of recordset. Defaults to 60 seconds
* **TYPE**: which DNS record tu update. Defaults to A record

