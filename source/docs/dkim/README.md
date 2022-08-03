# Domain Keys Identified Mail (DKIM)

[DKIM](dkim.md) is a method for detecting forged sender addresses in emails, a common technique 
used in phishing attacks.

It lets official mail servers add a signature to headers of outgoing email and identifies a domain’s public key so 
other mail servers can verify the signature. As with SPF, DKIM helps keep mail from being considered spam. 
It also lets mail servers detect when mail has been tampered with in transit.

* Senders choose which elements of the email are to be included in the DKIM signing process: The whole message (header and body) or one or more fields of the email header. These elements must remain unchanged in transit, or the DKIM signature will fail authentication.
* The sender configures the mailserver to automatically create a hash of the parts of the email that are to be signed. 
* The email provider receiving the email sees that it has a DKIM signature (and which "domain/selector" combination signed the encryption). It will run a DNS query to find the public key for that "domain/selector" combination. 
* A keypair match enables the email provider to decrypt the DKIM signature back to the original hash string. The receiving email provider takes the elements of the email signed by DKIM, generates its own hash of these elements, and compares that hash with the decrypted hash from the signature.
* Depending on the implementation, DKIM can also ensure that a message has not been modified or tampered with in transit.
* It is complex and has not been adopted widely. => No DKIM signature does not mean an email is fake. 
* The DKIM domain is not visible to end users and one needs to have a bit of a techie to make it visible and understand it. It is over many heads. Woosh!
* DKIM does not prevent spoofing of the visible header "From:" domain.
* [These configuration notes are](dkim.md) for debian 9 (will probably also work on buster)

[Rspamd](rspamd.md) is an e-mail filter system, which replaces Amavis and Spamassassin. It also is capable of signing outbound 
e-mails with DKIM keys. The status of Rspamd can be monitored via a simple web interface.