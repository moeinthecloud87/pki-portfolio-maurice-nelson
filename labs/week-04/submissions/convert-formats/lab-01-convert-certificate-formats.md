# Lab 01 — Convert Certificate Formats

## Overview
This lab is about the Creation and conversion of Certificate formats

## Environment
- Operating System: Windows  
- Terminal Used: GITBash/Openssl
- OpenSSL Version (openssl version):

## Steps Performed
Summarize the key steps you performed. Do not copy the lab instructions — describe what you actually did.

1.Created a Certification in the .PEM format
2.Converted the same cert into the .DER format
3.Used same cert to convert to the PFX format adding a password due to it also needing a Private Key as well for security.
4.Observed the differences in how the files are being displayed in each format.
5.

## Results
- What did the PEM file look like compared to the DER file?
 The PEM file was fully readable and the DER file had some parts that were readable but mostly random characters.
- What happened when you opened the .der file in a text editor?
  The file was mostly random characters with some parts being readable slos unlike the PEM file there was no Begin or End Certificate lines.
- What did the diff output show after converting PEM → DER → PEM?
  It showed Identical information as the original.
- What information was displayed when you verified the PFX?
  Once verified it asked for a password then displayed key security information such as sha256 and certificate information such as AES-256-CBC
## Key Findings

## Explanation
- Why does a PFX require a password?
  PFX requires a password because it not only holds your data, certificate, but also the private key, and the format is used to transport data from one end to another. 
- In what real-world scenario would you choose PEM vs DER vs PFX?
  If I was using linux but then needed that key in JAVA I would use .PEM to DER and If I needed to send that key to another system I would use PFX to Contain the keys and certificate.
- Why is it important never to commit private key files to GitHub?
Because Private Keys are like a master lock to your whole Digital Identity. Uploading this a bad actor could take the key and Impersonate the user stealing files, deleting keys and other things which can cause financial and business headaches.
## Challenges / Troubleshooting

## Artifacts
- leaf_cert.pem, leaf_cert.der, leaf_cert_restored.pem, test_cert.pem, test_bundle.pfx
