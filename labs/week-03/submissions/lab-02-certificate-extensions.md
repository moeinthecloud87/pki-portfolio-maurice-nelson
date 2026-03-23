
# Lab 02 — Investigate Certificate Extensions

## Overview
Briefly describe what this lab was about in your own words.
What PKI concept were you investigating?

---

## Environment
- OS:
- Terminal used (Mac Terminal / Git Bash / WSL):
- OpenSSL version (`openssl version`):

---

## Extensions Found

### Subject Alternative Name (SAN)
Paste the value from your output:
DNS:*.google.com, DNS:*.appengine.google.com, DNS:*.bdn.dev, DNS:*.origin-test.bdn.dev, DNS:*.cloud.google.com, DNS:*.crowdsource.google.com, DNS:*.datacompute.google.com, DNS:*.google.ca
### Key Usage
Paste the value from your output:critical
                Digital Signature

### Extended Key Usage (EKU)
Paste the value from your output:
               
TLS Web Server Authentication
### Basic Constraints
Paste the value from your output:
 critical CA:FALSE                

---

## Observations

1. What domains appear in the SAN field? Some Domains that appear are DNS:*.google.com, DNS:*.appengine.google.com, DNS:*.bdn.dev, DNS:*.origin-test.bdn.dev
2. What is this certificate authorized to do based on Key Usage? The certificate is only authorized to create digital signatures using it's Private Key and blocks the Public Key from being able to Sign Digital Signatures.
3. What does the EKU field tell you about this certificate's purpose? It validates and creates a pairing with webservers
4. Is this a CA certificate? How can you tell?
5. Why does SAN matter more than the Subject CN field in modern TLS? SAN is the modern way to validate Domains while CN are not in use in modern web browsers.

