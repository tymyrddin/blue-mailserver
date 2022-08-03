# Transport Layer Security (TLS)

[STARTTLS](tls.md) is a method of upgrading a plain text communication channel to a secure, encrypted communication channel. 
It makes it possible to create a secure, encrypted Simple Mail Transfer Protocol (SMTP) connection between mail servers.

There is a serious issue with STARTTLS — it is vulnerable to Man-in-the-Middle (MITM) attacks. This issue can be 
mitigated by using either DNS-Based Authentication of Named Entities (DANE) for SMTP or SMTP Mail Transfer Agent 
Strict Transport Security (MTA-STS).

With MTA-STS, DNSSEC is not required but is, of course, highly recommended. A valid X.509 certificate is required. 
Self-signed certificates are not allowed to be used in combination with MTA-STS. As mentioned before, DANE allows 
users of self-signed certificates, but a full DNSSEC implementation is required. 

## DNS-based Authentication of Named Entities (DANE)

[DANE](dane.md) is an alternative to Public Key Infrastructure (PKI) Certificate 
Authorities. It complements Domain Name System Security Extensions (DNSSEC), which must be implemented first. 

It is an Internet security protocol to allow X.509 digital certificates, commonly used for Transport Layer Security 
(TLS), to be bound to domain names using Domain Name System Security Extensions (DNSSEC). TLSA resource record is a 
type of DNS record.

## MTA Strict Transport Security (MTA-STS)

[MTA-STS](mta-sts.md) can be seen as a way to implement HTTP Strict Transport Security (HSTS) for SMTP. It is a mechanism to declare 
the ability to support TLS for SMTP and to specify whether sending mail servers must refuse to deliver an email to an 
authoritative receiving mail server that does not offer TLS with a trusted X.509 certificate. 

MTA-STS solves the problem that TLS is entirely optional with SMTP. With MTA-STS, DNSSEC is not required but is, 
of course, highly recommended. A valid X.509 certificate is required. Self-signed certificates are not allowed to be 
used in combination with MTA-STS.