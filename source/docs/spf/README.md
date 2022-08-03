# Sender Policy Framework (SPF)

[SPF](spf.md) is a method for email authentication and is designed to detect fraudulent mail servers. 
SPF allows the recipient’s mail server to check that an authorized mail server sent the email.

It is an open standard specifying a technical method to prevent sender address forgery. 
In plain language, it is a method of informing servers whether a specific mail server is authorised to send an email 
for a particular domain. With that, it can detect whether an email address is authentic or fake, before allowing it 
to pass into an inbox. An SPF record increases the likelihood that emails sent by valid addresses are delivered. 
Without it, genuine email could be categorised as spam. It also protects against malicious emails sent through your 
domain by spammers.

* A email provider publishes SPF records in the Domain Name System (DNS). These records list which IP addresses are authorised to send email on behalf of their domains.
* In an SPF check, email providers verify the SPF record by looking up the domain name listed in the return path address in the DNS. If the IP address sending email on behalf of the "return path" domain is not listed the record, the message fails authentication.
* SPF records must be kept updated.
* If a message fails SPF check, that doesn’t mean it will always be blocked.
* Breaks when a message is forwarded.
* Does not protect against spoofing of the visible "From" address in messages.