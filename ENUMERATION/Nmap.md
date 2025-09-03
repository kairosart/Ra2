## Simple enumeration.

#Attacking_machine
```
nmap <MACHINE IP>
```

![[Nmap-20250903200810941.webp]]


## Deeper enumeration

PORT     STATE SERVICE             VERSION
53/tcp   open  domain              Simple DNS Plus

80/tcp   open  http                Microsoft IIS httpd 10.0
|http-server-header: Microsoft-IIS/10.0
|http-title: Did not follow redirect to https://fire.windcorp.thm/

88/tcp   open  kerberos-sec        Microsoft Windows Kerberos (server time: 2025-09-03 18:55:11Z)

135/tcp  open  msrpc               Microsoft Windows RPC

139/tcp  open  netbios-ssn         Microsoft Windows netbios-ssn

389/tcp  open  ldap                Microsoft Windows Active Directory LDAP (Domain: windcorp.thm0., Site: Default-First-Site-Name)
| ssl-date: 2025-09-03T18:56:41+00:00; -1s from scanner time.
| ssl-cert: Subject: commonName=fire.windcorp.thm
| Subject Alternative Name: DNS:fire.windcorp.thm, DNS:selfservice.windcorp.thm, DNS:selfservice.dev.windcorp.thm
| Not valid before: 2020-05-29T03:31:08
|Not valid after:  2028-05-29T03:41:03

443/tcp  open  ssl/http            Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|ssl-date: 2025-09-03T18:56:40+00:00; -1s from scanner time.
|http-title: Not Found
|http-server-header: Microsoft-HTTPAPI/2.0
| tls-alpn: 
|_  http/1.1
| ssl-cert: Subject: commonName=fire.windcorp.thm
| Subject Alternative Name: DNS:fire.windcorp.thm, DNS:selfservice.windcorp.thm, DNS:selfservice.dev.windcorp.thm
| Not valid before: 2020-05-29T03:31:08
|Not valid after:  2028-05-29T03:41:03

445/tcp  open  microsoft-ds?

464/tcp  open  kpasswd5?

593/tcp  open  ncacn_http          Microsoft Windows RPC over HTTP 1.0

636/tcp  open  ssl/ldap            Microsoft Windows Active Directory LDAP (Domain: `windcorp.thm0`., Site: Default-First-Site-Name)
| ssl-date: 2025-09-03T18:56:40+00:00; -1s from scanner time.
| ssl-cert: Subject: commonName=fire.windcorp.thm
| Subject Alternative Name: `DNS:fire.windcorp.thm, DNS:selfservice.windcorp.thm, DNS:selfservice.dev.windcorp.thm`
| Not valid before: 2020-05-29T03:31:08
| Not valid after:  2028-05-29T03:41:03

2179/tcp open  vmrdp?

3268/tcp open  ldap                Microsoft Windows Active Directory LDAP (Domain: windcorp.thm0., Site: Default-First-Site-Name)
| ssl-cert: Subject: commonName=fire.windcorp.thm
| Subject Alternative Name: DNS:fire.windcorp.thm, DNS:selfservice.windcorp.thm, DNS:selfservice.dev.windcorp.thm
| Not valid before: 2020-05-29T03:31:08
| Not valid after:  2028-05-29T03:41:03
| ssl-date: 2025-09-03T18:56:40+00:00; -1s from scanner time.

3269/tcp open  ssl/ldap            Microsoft Windows Active Directory LDAP (Domain: windcorp.thm0., Site: Default-First-Site-Name)
| ssl-date: 2025-09-03T18:56:40+00:00; -1s from scanner time.
| ssl-cert: Subject: commonName=fire.windcorp.thm
| Subject Alternative Name: DNS:fire.windcorp.thm, DNS:selfservice.windcorp.thm, DNS:selfservice.dev.windcorp.thm
| Not valid before: 2020-05-29T03:31:08
| Not valid after:  2028-05-29T03:41:03

3389/tcp open  ms-wbt-server       Microsoft Terminal Services
| ssl-date: 2025-09-03T18:56:40+00:00; -1s from scanner time.
| ssl-cert: Subject: commonName=Fire.windcorp.thm
| Not valid before: 2025-09-02T17:16:49
| Not valid after:  2026-03-04T17:16:49

5222/tcp open  jabber              Ignite Realtime Openfire Jabber server 3.10.0 or later
| ssl-cert: Subject: commonName=fire.windcorp.thm
| Subject Alternative Name: DNS:fire.windcorp.thm, DNS:.fire.windcorp.thm**
| Not valid before: 2020-05-01T08:39:00
| Not valid after:  2025-04-30T08:39:00
| ssl-date: 2025-09-03T18:56:41+00:00; -1s from scanner time.
| xmpp-info: 
|   STARTTLS Failed
|   info: 
|     unknown: 
|     errors: 
|       invalid-namespace
|       (timeout)
|     features: 
|     capabilities: 
|     auth_mechanisms: 
|     stream_id: 5fteuw7dn9
|     xmpp: 
|       version: 1.0
|_    compression_methods: 

5269/tcp open  xmpp                Wildfire XMPP Client
| xmpp-info: 
|   Respects server name
|   STARTTLS Failed
|   info: 
|     unknown: 
|     errors: 
|       host-unknown
|       (timeout)
|     features: 
|     capabilities: 
|     auth_mechanisms: 
|     stream_id: 4shrur5meq
|     xmpp: 
|       version: 1.0
|_    compression_methods: 

7070/tcp open  http                Jetty 9.4.18.v20190429
| http-title: Openfire HTTP Binding Service
| http-server-header: Jetty(9.4.18.v20190429)

7443/tcp open  ssl/http            Jetty 9.4.18.v20190429
| http-server-header: Jetty(9.4.18.v20190429)
| http-title: Openfire HTTP Binding Service
| ssl-cert: Subject: commonName=fire.windcorp.thm
| Subject Alternative Name: DNS:fire.windcorp.thm, DNS:.fire.windcorp.thm
| Not valid before: 2020-05-01T08:39:00
| Not valid after:  2025-04-30T08:39:00

7777/tcp open  socks5              (No authentication; connection not allowed by ruleset)
| socks-auth-info: 
|_  No authentication

9090/tcp open  zeus-admin?
| fingerprint-strings: 
|   GetRequest: 
|     HTTP/1.1 200 OK
|     Date: Wed, 03 Sep 2025 18:55:11 GMT
|     Last-Modified: Fri, 31 Jan 2020 17:54:10 GMT
|     Content-Type: text/html
|     Accept-Ranges: bytes
|     Content-Length: 115
|     <html>
|     <head><title></title>
|     <meta http-equiv="refresh" content="0;URL=index.jsp">
|     </head>
|     <body>
|     </body>
|     </html>
|   HTTPOptions: 
|     HTTP/1.1 200 OK
|     Date: Wed, 03 Sep 2025 18:55:18 GMT
|     Allow: GET,HEAD,POST,OPTIONS
|   JavaRMI, drda, ibm-db2-das, informix: 
|     HTTP/1.1 400 Illegal character CNTL=0x0
|     Content-Type: text/html;charset=iso-8859-1
|     Content-Length: 69
|     Connection: close
|    

9091/tcp open  ssl/xmltec-xmlmail?
| ssl-cert: Subject: commonName=fire.windcorp.thm
| Subject Alternative Name: DNS:fire.windcorp.thm, DNS:.fire.windcorp.thm
| Not valid before: 2020-05-01T08:39:00
| Not valid after:  2025-04-30T08:39:00
| fingerprint-strings: 
|   DNSStatusRequestTCP, DNSVersionBindReqTCP: 
|     HTTP/1.1 400 Illegal character CNTL=0x0
|     Content-Type: text/html;charset=iso-8859-1
|     Content-Length: 69
|     Connection: close

2 services unrecognized despite returning data. If you know the service/version, please submit the following fingerprints at https://nmap.org/cgi-bin/submit.cgi?new-service :

Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Device type: general purpose
Running (JUST GUESSING): Microsoft Windows 2019 (89%)
Aggressive OS guesses: Microsoft Windows Server 2019 (89%)
No exact OS matches for host (test conditions non-ideal).
Network Distance: 2 hops
Service Info: Host: FIRE; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled and required
| smb2-time: 
|   date: 2025-09-03T18:56:01
|_  start_date: N/A
|clock-skew: mean: -1s, deviation: 0s, median: -1s

TRACEROUTE (using port 139/tcp)
HOP RTT      ADDRESS
1   72.41 ms 10.8.0.1
2   73.55 ms windcorp.thm0 (10.10.94.25)

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 128.57 seconds


## /etc/hosts

#Attacking_machine 

Add this to /etc/hosts.

MACHINE IP                `windcorp.thm0 fire.windcorp.thm selfservice.windcorp.thm selfservice.dev.windcorp.thm` 


**Next step:** [[Gobuster]]

