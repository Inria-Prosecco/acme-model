# A Formal Model for ACME: Analyzing Domain Validation over Insecure Channels

## Abstract
Web traffic encryption has shifted from applying only to highly sensitive websites (such as banks) to a majority of all Web requests. Until recently, one of the main limiting factors for enabling HTTPS is the requirement to obtain a valid certificate from a trusted certification authority, a tedious process that typically involves fees and ad-hoc key generation, certificate request and domain validation procedures. To remove this barrier of entry, the Internet Security Research Group created Let's Encrypt, a new non-profit certificate authority which uses a new protocol called Automatic Certificate Management Environment (ACME) to automate certificate management at all levels (request, validation, issuance, renewal, and revocation) between clients (website operators) and servers (certificate authority nodes). Let's Encrypt's success is measured by its issuance of over 12 million free certificates since its launch in April 2016.

In this paper, we survey the existing process for issuing domain-validated certificates in major certification authorities to build a security model of domain-validated certificate issuance. We then model the ACME protocol in the applied pi-calculus and verify its stated security goals against our threat model of domain validation. We compare the effective security of different domain validation methods and show that ACME can be secure under a stronger threat model than that of traditional CAs. We also uncover weaknesses in some flows of ACME 1.0 and propose verified improvements that have been adopted in the latest protocol draft submitted to the IETF.

## About this Repository
This repository contains a research report by Karthikeyan Bhargavan, Antoine Delignat-Lavaud and Nadim Kobeissi. Here are the components:

* `paper.pdf`: The report itself in PDF format.
* `ACMEdraft1.pv`: A symbolic model of the ACME protocol (draft-1) in the applied-pi calculus.
* `ACMEdraft3.pv`: A symbolic model of the ACME protocol (draft-3) in the applied-pi calculus.

## Verifying the Models
Please download [ProVerif](http://prosecco.gforge.inria.fr/personal/bblanche/proverif/) in order to verify the models included in this repository.

## Contact
If you have any questions or comments, please send an email to [Nadim Kobeissi](mailto:nadim.kobeissi@inria.fr). Thanks for reading our report!
