# Lab 01 — Diagnose an Expired Certificate

## Incident Summary

**Target System:** portal.metrogeneral.org (simulated via expired.badssl.com)

**Reported Behavior:** TLS failure — patients seeing security warnings when accessing the appointment portal

**Diagnostic Scope:** PKI Diagnostic Framework — all 4 steps

## Diagnostic Steps

Summarize what you checked at each step. Do not copy the lab instructions — describe what you actually did.

**Step 1 — Retrieve:**
I used the command openssl s_client to Retrieve a live certificate. It returned a certificate, but no OpenSSL error was reported when using the command.
**Step 2 — Parse:**
Parsed the Certificate by using the command openssl x509 -in expired_cert.pem -text -noout and reading it. I checked the Not Before/After dates which were Not Before Apr 9 12 a.m. 2015 and not after Apr 12 11:59 2015. The cert is currently out of it's vailidity period. The subject is *.badssl.com and the issuer is COMODO RSA Domain Validation Secure.
**Step 3 — Validate the Chain:**
I checked for Chain Validation to rule out Chain errors. There are three Certificates a leaf, Intermediate, and Root which the chain does terminate at.
**Step 4 — Check Revocation and Trust:**
Checked if the Cert had been Revoked. There was a ocsp url presented after using the command openssl x509 -in expired_cert.pem -noout -text | grep -A1 "OCSP"
 OCSP - URI:http://ocsp.comodoca.com

## Evidence

- Not Before date:Apr  9 00:00:00 2015 GMT
- Not After date:Apr 12 23:59:59 2015 GMT
- Days since expiration:
- Subject (entity the certificate was issued to):*.badssl.com
- Issuer:COMODO RSA Domain Validation Secure
- Chain status (complete / incomplete):Yes
- OCSP URL present? (yes/no):Yes

## Root Cause

What caused the TLS failure? Be specific — is this a certificate problem, a chain problem, or a configuration problem?
The TLS failure was caused by the Expiration of the certificate.
## Remediation

Step-by-step path to resolve this incident:

1.Create new Certificate
2.Send Certificate for Signing with the CA
3.Deploy new Certificate with updated Expiration Values.

## Key Findings

## Challenges / Troubleshooting

## Artifacts

- expired_cert.pem
