# Week 7 – DNS with BIND9 (Ubuntu)

## What I built
Forward + reverse zones on BIND9 with A, MX, CNAME, TXT, PTR.

## Files
- named.conf.local – zones
- db.test.local – forward records
- db.192 – reverse PTR records

## Commands used
```bash
sudo named-checkconf
sudo named-checkzone test.local /etc/bind/db.test.local
sudo named-checkzone 1.168.192.in-addr.arpa /etc/bind/db.192
sudo systemctl restart bind9
dig @localhost server1.test.local +noall +answer
dig @localhost -x 192.168.1.1 +noall +answer
