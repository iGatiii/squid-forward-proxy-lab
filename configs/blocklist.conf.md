```
http_port 3128

acl localnet src 192.168.10.0/24

acl blocked_sites dstdomain .facebook.com .youtube.com

http_access deny blocked_sites
http_access allow localhost
http_access allow localnet
http_access deny all
```

