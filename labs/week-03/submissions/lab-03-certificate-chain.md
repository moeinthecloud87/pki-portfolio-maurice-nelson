
# Lab 03 — Verify a Certificate Chain

## Overview
Briefly describe what this lab was about in your own words.
What PKI concept were you investigating?

---

## Environment
- OS:
- Terminal used (Mac Terminal / Git Bash / WSL):
- OpenSSL version (`openssl version`):
- Website used: github.com

---

## Chain Verification Result
Paste the output of your `openssl verify` command:

---

## Certificate Roles

| Certificate  | Role                        | Key Indicator                    |
|--------------|-----------------------------|----------------------------------|
| root.pem     |                             |    Key Usage: critical
                Digital Signature, Certificate Sign, CRL Sign
            X509v3 Basic Constraints: critical
                CA:TRUE
                               |
| intermediate.pem |                         |  CA:TRUE, pathlen:0                                |
| server.pem   | Leaf Certificate            |  CA:FALSE
                                |

---

## Observations

1. Did the chain verify successfully? What did the output say? Yes the out put said server.pem OK
2. How did you identify the root CA? By the CN field ENtrust Root Certification Authority
3. How did you identify the intermediate CA? Point to Root Authority (in this case higher authority??)
4. What field confirms whether a certificate can issue other certificates? The Key Usage Field
5. Why does removing the intermediate certificate break the chain? Because Browser certificates only trust from the ROOT if the Intermediate CA is missing to confirm the signature from the ROOT CA the trust chain is broken.

