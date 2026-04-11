# Lab 02 — Diagnose a Broken Certificate Chain

## Incident Summary

**Target System:** Radiology imaging platform (simulated via incomplete-chain.badssl.com)

**Reported Behavior:** TLS failure after certificate renewal — vendor says certificate looks fine, connection still failing

**Diagnostic Scope:** PKI Diagnostic Framework — all 4 steps

## Diagnostic Steps

Summarize what you checked at each step. Do not copy the lab instructions — describe what you actually did.

**Step 1 — Retrieve:**
I retrieved the live Certificate and looked for what the server sent back.
**Step 2 — Parse:**
I then Parsed the certifcate to check and see if the cert was expired or who issued and signed it. 
**Step 3 — Validate the Chain:**
Once I verified the cert was indeed not expired I checked to see if the Cert chain was intact. I found that the leaf cert wasn't able to be verified from the Intermediate Cert.
**Step 4 — Check Revocation and Trust:**
I checked for revocation and got return code 21 unable to verify first certificate.
## Evidence

- Leaf certificate Subject:
- Issuer CN (the missing intermediate):
- Number of certificates the server sent: *.badssl.com
- Verify return code from openssl s_client: 
- openssl verify error before adding intermediate: error 20 at 0 depth lookup: unable to get local issuer certificate
- openssl verify result after adding intermediate with -untrusted: 
- Is the root CA trusted by your system? (yes/no):OK

## Root Cause

Is this a certificate problem or a server configuration problem? Explain the distinction clearly — this matters for how the fix is communicated to the team.

## Remediation

Step-by-step path to resolve this incident:

1. Find where I can get a replacement Intermediate Cert that the leaf cert trusts
2. Add Intermediate Cert into Chain 
3. Verify that Chain is now working 

## Key Findings

## Challenges / Troubleshooting

## Artifacts

- leaf_cert.pem, issuer_cert.pem
