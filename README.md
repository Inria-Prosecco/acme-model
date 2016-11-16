# A Formal Model for ACME: Analyzing Domain Validation over Insecure Channels

## Authors
Karthikeyan Bhargavan (INRIA Paris), Antoine Delignat-Lavaud (Microsoft Research Cambridge), Nadim Kobeissi (INRIA Paris).

## Abstract
Web traffic encryption has shifted from applying only to highly sensitive websites (such as banks) to a majority of all Web requests. Until recently, one of the main limiting factors for enabling HTTPS is the requirement to obtain a valid certificate from a trusted certification authority, a tedious process that typically involves fees and ad-hoc key generation, certificate request and domain validation procedures. To remove this barrier of entry, the Internet Security Research Group created Let's Encrypt, a new non-profit certificate authority which uses a new protocol called Automatic Certificate Management Environment (ACME) to automate certificate management at all levels (request, validation, issuance, renewal, and revocation) between clients (website operators) and servers (certificate authority nodes). Let's Encrypt's success is measured by its issuance of over 12 million free certificates since its launch in April 2016.

In this paper, we survey the existing process for issuing domain-validated certificates in major certification authorities to build a security model of domain-validated certificate issuance. We then model the ACME protocol in the applied pi-calculus and verify its stated security goals against our threat model of domain validation. We compare the effective security of different domain validation methods and show that ACME can be secure under a stronger threat model than that of traditional CAs. We also uncover weaknesses in some flows of ACME 1.0 and propose verified improvements that have been adopted in the latest protocol draft submitted to the IETF.

## Some of Our Conclusions
* ACME uses DNS/HTTP validation, which are both strictly stronger than domain validation schemes that use email.
* ACME uses public key `keyAuthorization`, which is is strictly stronger than using server nonces.
* ACME can provide stronger guarantees in multi-CA settings, if it uses channel binding and if it includes the CA name in the `keyAuthorization`.
* ACME draft-1 had email-based account recovery, which was dangerous. Be wary of reintroducing email-based tokens in the protocol.

## About this Repository
* `paper.pdf`: The report itself in PDF format.
* `ACMEdraft1.pv`: A symbolic model of the ACME protocol (draft-1) in the applied-pi calculus.
* `ACMEdraft3.pv`: A symbolic model of the ACME protocol (draft-3) in the applied-pi calculus.

## Verifying the Models
Please download [ProVerif](http://prosecco.gforge.inria.fr/personal/bblanche/proverif/) in order to verify the models included in this repository.

## Version Changes
* Version 2 (Nov. 16): Corrected that Let's Encrypt is hosted on Akamai, not CloudFlare. Clarified which ACME draft version Let's Encrypt employs.
* Version 1 (Nov. 15): Initial version.

## Contact
If you have any questions or comments, please send an email to [Nadim Kobeissi](mailto:nadim.kobeissi@inria.fr). Thanks for reading our report!
