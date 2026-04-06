# Lab 01 — Generate a CSR

## Overview
This lab is about creating a CSR, a step in the process of having a CA sign and Verify a cert.

## Environment
- Operating System: Windows 11
- Terminal Used: OpenSSL/GIT BASH
- OpenSSL Version (openssl version): 3.6.1

## Steps Performed
Summarize the key steps you performed. Do not copy the lab instructions — describe what you actually did.
1.Created folder for key and CSR
2.Ran openssl command to request a new CSR
3.entered subject fields for the new Certificate
4.Verified the CSR was made using openssl req -text -noout -verify which showed the information in a readable format.


## Results
- What Subject fields did you include in your CSR, and what does each field communicate to a CA?
-     The Organization Organizational Unit Country State and Locality
- What output did `openssl req -text` show when you inspected your CSR?
-     It showed the certificate request withe Public key and Publick key info including the type of Encryption 
- How did the CSR differ from the signed certificate when you compared them?
-     One showed the differnce like the Expiration date and Serial Number
- What did the diff output show when you compared the public key in the CSR vs the signed cert?

## Key Findings

## Explanation
- Why must the private key never leave the requestor's machine — even when submitting a CSR to a CA?
-     A bad actor can grab the key and impersonate a persons identity and gain access to files, and other types of data. 
- What is the difference between a CSR and a signed certificate?
-     A CSR is sent over to a CA for verification and signing and a Signed Certificate is already self signed or signed by a CA.
- In what real-world scenario would self-signing be appropriate vs submitting to a trusted CA?
-     

## Challenges / Troubleshooting
Running a openssl command in GITBASH led to error of not being able to see the CSR. I learned this is a POSIX path conversion, this means
GIT is seeing the command as a the beginning of Windows Path not an OpenSSL command. Once I added a an extra forward slash // basically telling GITBASH this is not a windows command.
## Artifacts
- test_csr.pem, test_cert.pem
