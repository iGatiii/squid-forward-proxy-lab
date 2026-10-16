```
http_port 3128

acl localnet src 192.168.10.0/24

acl allowed_site dstdomain .kali.org

http_access allow localhost allowed_site
http_access allow localnet allowed_site
http_access deny all
```
