
A **PFX file** (also known as **PKCS #12** or `.p12`) is a binary file format commonly used to store:

- A **private key**
- The associated **public key certificate**
- Optionally, the full **certificate chain** (intermediate and root CA certificates)

### Common Uses

- **SSL/TLS certificates** → for web servers (Apache, Nginx, IIS, Tomcat, etc.)
- **Code signing** → storing developer signing certificates
- **Email encryption/signing** (S/MIME)
- **Client authentication** → VPNs, APIs, or enterprise apps
### Characteristics

- **Password protected** → PFX files are encrypted with a password.
- **Portable** → Can be exported and imported across systems (e.g., Windows, Linux, macOS).

---

## Certificate cert.pfx

#Attacking_machine 
- Download `cert.pfx`.
## crackpkcs12

`crackpkcs12` is a tool that can be used to **brute-force or wordlist attack the password** of a `.pfx` / `.p12` (PKCS#12) file.

It’s usually installed as part of the **John the Ripper Jumbo** suite, and it works by taking the PFX file and trying password candidates until it finds the correct one.

### Installing

On Kali Linux:

```
wget https://github.com/crackpkcs12/crackpkcs12/archive/refs/heads/master.zip
unzip master.zip
cd crackpkcs12
./configure
make
cd scr
sudo cp crackpkcs12 /usr/local/bin/
```

## Running

#Attacking_machine 

```
crackpkcs12 -d /usr/share/wordlists/rockyou.txt cert.pfx 
```

![[Certificate-20250904202832731.webp]]


### Testing password

```
openssl pkcs12 -in cert.pfx -info -nodes
```

MAC: sha256, Iteration 2000
MAC length: 32, salt length: 20
PKCS7 Data
Shrouded Keybag: PBES2, PBKDF2, AES-256-CBC, Iteration 2000, PRF hmacWithSHA256
Bag Attributes
    Microsoft Local Key set: <No Values>
    localKeyID: 01 00 00 00 
    friendlyName: te-4b942170-a078-48b3-80cb-e73333376b73
    Microsoft CSP Name: Microsoft Software Key Storage Provider
Key Attributes
    X509v3 Key Usage: 90 
-----BEGIN PRIVATE KEY-----
MIIEvgIBADANBgkqhkiG9w0BAQEFAASCBKgwggSkAgEAAoIBAQC/3TRp/R/qfzQX
QnpT2MyBzBCujOuReaLTZ6xbVcCwelae64xAMg3oC2JiYNygURfP8214sjtPo+6y
pDpJeosG6tOdHxUic8PdB5rqXE5c2O416qpkoeFRpeLBJqq0AH4bM+Q216/DeN4S
P31JP8bWrBj1dx6x96pHYniRD7xTnIoskM8HE5LHf5IeMoSustOTrqWuUSLhq2v4
/9xxcDlMGRkWRiGLdh0pMOdh4/Z8yuq86qnDzZ6eIcAYnY3wkls16nzqmzyCIhGJ
4FRRyUX9YKnhzfeniLWKhXEkhgmPp/S2MaHL0bEHuXr061S61wgbT8WHEvZ1Dzoy
accfR0TtAgMBAAECggEBAJNKtlpHwKC9VrgkiNSlsxpSFtxpws7DmoTBKkhT5MGW
qbkHC3yc8KAbXUQ5KCbLGoTCVGA8M9xH9Y+fFEAkm2aMEDinDAqO5OZiWENi6aXN
w9IQfQ8UV23e891kWdgmKKmphKG1o3Fk8NcBdqUtGPDk3aRT9nSZtVdn+Tcj5Wgp
iHiwGnWtjZV2C4VS5J/PBdWyXNHB3qsJUiGUnOYkrCQJgTOllau5mp9S7DNbz/IY
ziMBjv4VkHJyt8rSBRV1lzN4Ypo+tVeO6MOfwbse6kAqjOx0VJz3ktpG6VQfTFs1
UtkPvys9yQAb8EcTn2cDLnLzkodZq4jxFqgdm2SvvOECgYEA4N79nnYWsojfBtuO
k6MUuMI1afgyzp6erWtSo//PCy/uTiUL6KLUS0l4u0Qoq2GbSHPmqCQJEcvjieAb
IGsnr+D1mX5Z9Kq9Q4uk274QCNXNt0k7M7+//rQxNJVw8LLXsZVqBR2OEWczAm/D
d/14eApAVk9ChPXDmlkGcDOHP5MCgYEA2myCMwUfNxiMbiNtTeHLQnuKzjD50E8O
4B8A4Qi45mxUSUR6NJZUCgC0KksJjd/qEPIHSxmotvOv7tW/XXxTXJnfuya49VbS
lkteFaWXGZUMeEeP3qSENPnGZgXb+/LTsQByK0I0im4Qv0B3AKEGXaQzwcutgL+r
NEHRZAQ9OX8CgYApP/6aMONdAMqYwXHYF1RXyBhwRf1b9bD58vQH7YcXcEVwxE74
79Wtsd6Zy5kCRzdrBQfM1D9tqk8lHZ0cR0vScZvb+leaEDAD0fv961GZrU69Touz
pHsdyAQ2tysunEAA7X2zToafHqU2zzW2LyMIMik3K/bx2Pt2ttn9fxZSTQKBgE22
L3ihiOKcXFJPTnNYM24a8F699BOWHS/GOBTYepiY0EAlGemd1pace31UpziQAwI2
ajvhDDLTbrPl3qkPM8WNhZlbhJDdbB1HAVloSeMzMXWV2G0ZUWRbvafMy+DPG1wt
UXFso67gzBqPgAd8QvyMEFIR+lAFYY89H5ebHoFXAoGBAMZwew71UsZ9PVZ2xcxW
iIt7OSxbx4VnrDr3HCZ5NjVYdJrjDAFZrEA84/Mo1aXH/K4Fpq1lmTNIfQxPacG2
FRIKyIa9JdSaVUI1pBP5w6bsVOC4WiL1EQU3+2ImdFPm9ZRf1Y1uPuUzxe8EeebI
y+tQYYpi8HTqt2yzZ01n6C+0
-----END PRIVATE KEY-----
PKCS7 Encrypted data: PBES2, PBKDF2, AES-256-CBC, Iteration 2000, PRF hmacWithSHA256
Certificate bag
Bag Attributes
    localKeyID: 01 00 00 00 
subject=CN=fire.windcorp.thm
issuer=CN=fire.windcorp.thm
-----BEGIN CERTIFICATE-----
MIIDajCCAlKgAwIBAgIQUI2QvXTCj7RCVdv6XlGMvjANBgkqhkiG9w0BAQsFADAc
MRowGAYDVQQDDBFmaXJlLndpbmRjb3JwLnRobTAeFw0yMDA1MjkwMzMxMDhaFw0y
ODA1MjkwMzQxMDNaMBwxGjAYBgNVBAMMEWZpcmUud2luZGNvcnAudGhtMIIBIjAN
BgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAv900af0f6n80F0J6U9jMgcwQrozr
kXmi02esW1XAsHpWnuuMQDIN6AtiYmDcoFEXz/NteLI7T6PusqQ6SXqLBurTnR8V
InPD3Qea6lxOXNjuNeqqZKHhUaXiwSaqtAB+GzPkNtevw3jeEj99ST/G1qwY9Xce
sfeqR2J4kQ+8U5yKLJDPBxOSx3+SHjKErrLTk66lrlEi4atr+P/ccXA5TBkZFkYh
i3YdKTDnYeP2fMrqvOqpw82eniHAGJ2N8JJbNep86ps8giIRieBUUclF/WCp4c33
p4i1ioVxJIYJj6f0tjGhy9GxB7l69OtUutcIG0/FhxL2dQ86MmnHH0dE7QIDAQAB
o4GnMIGkMA4GA1UdDwEB/wQEAwIFoDAdBgNVHSUEFjAUBggrBgEFBQcDAgYIKwYB
BQUHAwEwVAYDVR0RBE0wS4IRZmlyZS53aW5kY29ycC50aG2CGHNlbGZzZXJ2aWNl
LndpbmRjb3JwLnRobYIcc2VsZnNlcnZpY2UuZGV2LndpbmRjb3JwLnRobTAdBgNV
HQ4EFgQUIZvYlCIhAOFLRutycf6U2H6LhqIwDQYJKoZIhvcNAQELBQADggEBAKVC
ZS6HOuSODERi/glj3rPJaHCStxHPEg69txOIDaM9fX4WBfmSjn+EzlrHLdeRS22h
nTPirvuT+5nn6xbUrq9J6RCTZJD+uFc9wZl7Viw3hJcWbsO8DTQAshuZ5YJ574pG
HjyoVDOfYhy8/8ThvYf1H8/OaIpG4UIo0vY9qeBQBOPZdbdVjWNerkFmXVq+MMVf
pAt+FffQE/48kTCppuSKeM5ZMgHP1/zhZqyJ3npljVDlgppjvh1loSYB+reMkhwK
2gpGJNwxLyFDhTMLaj0pzFL9okqs5ovEWEj8p96hEE6Xxl4ZApv6mxTs9j2oY6+P
MTUqFyYKchFUeYlgf7k=
-----END CERTIFICATE-----
