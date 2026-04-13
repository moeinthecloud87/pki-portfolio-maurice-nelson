# Lab 03 — Diagnose a Hostname and SAN Mismatch

## Incident Summary

**Target System:** Staff scheduling portal (simulated via wrong.host.badssl.com)

**Reported Behavior:** Browser security errors after the portal was moved to a new hostname — staff cannot access the scheduling system

**Diagnostic Scope:** PKI Diagnostic Framework — all 4 steps

## Diagnostic Steps

Summarize what you checked at each step. Do not copy the lab instructions — describe what you actually did.

**Step 1 — Retrieve:**
I retrieved a live certificate
**Step 2 — Parse:**
Parsed to validate the expiration date and SAN for this certificate, found difference in hostname causing error
**Step 3 — Validate the Chain:**
Validated the chain to make sure it's not also a Trust chain issue  
**Step 4 — Check Revocation and Trust:**
Made sure to check CRL to make sure this wasn't also a Revocation and trust issue as well.
## Evidence

- Hostname accessed (what the client expected): staff.metrogeneral.org
- Subject CN (what the certificate says):*.badssl.com
- SAN DNS entries (list all):Subject Alternative Name:
                DNS:*.badssl.com, DNS:badssl.com
- Do any SAN entries match the hostname? (yes/no): no
- Verify return code from openssl s_client:
- Does the chain validate independently of the hostname issue? (yes/no):
- OCSP URL present? (yes/no):

## Root Cause

Is this a certificate problem, a chain problem, or a configuration/deployment problem? Explain why the distinction matters.

## Remediation

Step-by-step path to resolve this incident:

1.
2.
3.

### Why a DNS CNAME alias would not fix this

Explain clearly — in terms a non-technical manager could follow — why adding a CNAME from `staff.metrogeneral.org` back to `scheduling.metrogeneral.org` does not resolve the TLS error.
The Certificate that allows access to the website is glued to the original name of the website adding the new name will not work. 
## Key Findings

## Challenges / Troubleshooting
Reading the certificate fields to make sure I'm reading the right section was difficult. Going through a certificate found on the internet to learn about the fields.
## Artifacts

- No certificate files required for this lab
