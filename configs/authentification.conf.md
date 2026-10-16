```
http_port 3128

acl localnet src 192.168.10.0/24
acl blocked_sites dstdomain .facebook.com .youtube.com

auth_param basic program /usr/lib/squid/basic_ncsa_auth /etc/squid/passwords
auth_param basic realm Squid Proxy Authentication
auth_param basic credentialsttl 2 hours

acl authenticated proxy_auth REQUIRED

http_access deny blocked_sites
http_access deny !authenticated
http_access allow localhost
http_access allow localnet
http_access deny all
```

