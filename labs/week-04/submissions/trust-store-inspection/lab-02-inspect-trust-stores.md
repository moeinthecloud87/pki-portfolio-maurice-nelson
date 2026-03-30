# Lab 02 — Inspect Your Trust Store

## Overview
Briefly describe what this lab was about in your own words. What PKI concept or system behavior were you investigating?

## Environment
- Operating System:Windows
- Terminal Used:GITBash/Powershell
- OpenSSL Version (openssl version):

## Steps Performed
1.Ran the command certmgr.msc
2.Clicked on Trusted Root
3.Looked at bottom of screen and shows how many ROOT CAs are on the system
4.

## Results
- How many trusted root CAs did you find on your system?
  There are 75 trusted Root CAs 
- Name at least one specific root CA you inspected. Include its Subject and expiration date.
  I looked at the Sectigo Root CA It's Subject = CN Sectigo Public server authentication root E46 O = Sectigo Limited C= GB and it's expiration is Valid to 3/21/2046 at 7:59 PM
- What did the verify return code output tell you?
It told me the Common Names of the the trusted root CAs
## Key Findings

## Explanation
- Why does your browser trust a certificate from a website you have never visited before?
  Browsers come with Pre Assigned Root CAs, the website will validate that the Root CA is signed by one of the Root CA's and create a Trust Chain
  
- What would happen if an enterprise's internal root CA was NOT in the trust store?
  I believe if a application or user wanted to get info from that source they wouldn't be able to because the internal CA wouldn't be there to validate the incoming request
- What surprised you about how many roots are pre-installed on your system?
that some have been around since 1999 even though they are now expired.
## Challenges / Troubleshooting

## Artifacts
- root_cas.pem (macOS) or equivalent, screenshots stored in assets/screenshots/week-04/
