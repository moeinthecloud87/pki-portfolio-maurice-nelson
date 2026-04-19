# Lab 01 — Analyze a Live Enterprise Certificate Deployment

## Overview

Briefly describe what this lab was about in your own words. What were you analyzing and why?

## Environment

- Operating System: Windows   
- Terminal Used: GIT BASH/
- OpenSSL Version (openssl version): 1.1.1k
- Target Hostname Chosen: Carefirst.com

## Target
Carefirst Blue Cross Blue Shield
**Hostname analyzed:**
Carefirst.com
**Why I chose this target:**
Major leader in Health Insurance holds millions of patients data.
## Certificate Summary

- Issuer (CA name and type — public CA / internal CA):
-   DigiCert Global
- Validity window (Not Before → Not After):
-   Issued On	Wednesday, February 5, 2026 at 12:00:00 AM
  Expires On	Friday, February 5, 2027 at 6:59:59 PM
- Approximate remaining validity (days):
- Certificate type (DV / OV / EV — and how you determined this):
- Number of SAN entries: 4 Entries 
- Wildcard entries present? If yes, list them and describe what they suggest about the architecture:
There were no Wildcard entries present.
## Chain Analysis

- Number of certificates in the chain: three
- Intermediate CA subject: DigiCert Global G2 TLS RSA SHA256 2020 CA1
- Root CA name: DigiCert Global Root G2
- Is the chain complete (leaf → intermediate → root)? Yes chain is complete
- Any missing or unexpected certificates in the chain? NO

## Termination Analysis

- Where does TLS appear to terminate — application server, load balancer, or CDN edge?
- Evidence supporting this conclusion (server headers, issuer identity, SAN pattern, or other indicators):

## TLS Configuration

- SSL Labs overall grade:A-
- TLS versions supported: 1.2
- Deprecated TLS (1.0 or 1.1) still supported? (yes/no):
- HSTS configured? (yes/no):NO
- OCSP stapling enabled? (yes/no):NO

## CT Log Analysis

- Approximate number of certificates issued for this domain:625
- Is the issuer consistent across recent certificates, or have multiple CAs been used? The Issuer is pretty consistent there are a few differenct CA like Amazon that also are Issuers.
- Any unexpected or unfamiliar issuers? If yes, possible explanation: 
- Certificate validity period pattern (90-day Let's Encrypt / 1–2 year paid CA): from 193 - 312 day Validity period between 11/2025 and 4/2026

## Architecture Assessment

In 2–3 sentences, describe what this certificate deployment tells you about the organization's PKI architecture and operational approach. This is not a grade — it is an observation. Write it the way a PKI engineer would write it in a pre-migration audit.
This Organization uses some of the latest security protocols such as TLS 1.2 and older versions are not permitted. They do not have a lot of SAN hostnames. 
## Key Findings

## Challenges / Troubleshooting

## Artifacts

- enterprise_cert.pem
