```
└─$ nmap -sC -sV  -Pn 10.10.11.223 -oA .

Nmap scan report for 10.10.11.223
PORT     STATE SERVICE            VERSION

443/tcp  open  ssl/http           nginx 1.14.0 (Ubuntu)
|_http-server-header: nginx/1.14.0 (Ubuntu)
|_http-title: Did not follow redirect to **https://www.webhosting.htb/**
|_ssl-date: TLS randomness does not represent time
| ssl-cert: Subject: organizationName=free-hosting/stateOrProvinceName=Berlin/countryName=DE
| Not valid before: 2023-02-01T20:19:22
|_Not valid after:  2024-02-01T20:19:22

5000/tcp open  ssl/upnp?
| ssl-cert: Subject: commonName=*.webhosting.htb/organizationName=Acme, Inc./stateOrProvinceName=GD/countryName=CN
| Subject Alternative Name: DNS:webhosting.htb, DNS:webhosting.htb
| Not valid before: 2023-03-26T21:32:06
|_Not valid after:  2024-03-25T21:32:06
| fingerprint-strings: 
|   GenericLines: 
|     HTTP/1.1 400 Bad Request
|     Content-Type: text/plain; charset=utf-8
|     Connection: close
|_    Request

5001/tcp open  ssl/commplex-link?
|_ssl-date: TLS randomness does not represent time
| tls-alpn: 
|   h2
|_  http/1.1
| ssl-cert: Subject: commonName=*.webhosting.htb/organizationName=Acme, Inc./stateOrProvinceName=GD/countryName=CN
| Subject Alternative Name: DNS:webhosting.htb, DNS:webhosting.htb
| Not valid before: 2023-03-26T21:32:06
|_Not valid after:  2024-03-25T21:32:06
| fingerprint-strings: 
|   GenericLines, Help: 
|     HTTP/1.1 400 Bad Request
|     Content-Type: text/plain; charset=utf-8
|     Connecti
