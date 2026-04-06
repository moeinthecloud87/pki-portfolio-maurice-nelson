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
-----BEGIN CERTIFICATE-----
MIIDbDCCAlQCAQEwDQYJKoZIhvcNAQELBQAwfDEjMCEGA1UECgwaQ3liZXJWaXNp
b25hcmllcyBJbnN0aXR1dGUxGzAZBgNVBAsMElBLSSBDYXJlZXIgUGF0aHdheTEL
MAkGA1UEBhMCVVMxEzARBgNVBAgMCkNhbGlmb3JuaWExFjAUBgNVBAcMDVNhbiBG
cmFuY2lzY28wHhcNMjYwNDA2MDAyMjMwWhcNMjcwNDA2MDAyMjMwWjB8MSMwIQYD
VQQKDBpDeWJlclZpc2lvbmFyaWVzIEluc3RpdHV0ZTEbMBkGA1UECwwSUEtJIENh
cmVlciBQYXRod2F5MQswCQYDVQQGEwJVUzETMBEGA1UECAwKQ2FsaWZvcm5pYTEW
MBQGA1UEBwwNU2FuIEZyYW5jaXNjbzCCASIwDQYJKoZIhvcNAQEBBQADggEPADCC
AQoCggEBALQExyqPDwS4w489cAgylxCIWXInmDvcsV3O4h8xPRK47Zp18Z2331UF
2NfAZ7Z5q5nFZiPqMMm8pkm/zuhqfYj59kvyY4JFXoXD7CubhkUH3pWlZD4AjdVL
S+8hkIcCkkp5OOl+2B3lsdk9FvjbBbBCSwzo2ApLgcWAIYGY28GuiuEV6iJx7FwQ
qTwn6rwITKxqWsQ6zNCDmnfFSD4IyoiND9sfS+YZ2Wzwpm9cC8EloYfvFCohn7LH
c7Tp0oBV4k5ODgFl1y38+wqDy5jEp4bww+BHSdq8/vLCYHcZRox8mqfREcopORS3


-----BEGIN CERTIFICATE REQUEST-----
MIICwTCCAakCAQAwfDEjMCEGA1UECgwaQ3liZXJWaXNpb25hcmllcyBJbnN0aXR1
dGUxGzAZBgNVBAsMElBLSSBDYXJlZXIgUGF0aHdheTELMAkGA1UEBhMCVVMxEzAR
BgNVBAgMCkNhbGlmb3JuaWExFjAUBgNVBAcMDVNhbiBGcmFuY2lzY28wggEiMA0G
CSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC0BMcqjw8EuMOPPXAIMpcQiFlyJ5g7
3LFdzuIfMT0SuO2adfGdt99VBdjXwGe2eauZxWYj6jDJvKZJv87oan2I+fZL8mOC
RV6Fw+wrm4ZFB96VpWQ+AI3VS0vvIZCHApJKeTjpftgd5bHZPRb42wWwQksM6NgK
S4HFgCGBmNvBrorhFeoicexcEKk8J+q8CEysalrEOszQg5p3xUg+CMqIjQ/bH0vm
Gdls8KZvXAvBJaGH7xQqIZ+yx3O06dKAVeJOTg4BZdct/PsKg8uYxKeG8MPgR0na
vP7ywmB3GUaMfJqn0RHKKTkUt3VkFAQZ+kbtd7KQTfW5mIJaUVc0yTkzAgMBAAGg
ADANBgkqhkiG9w0BAQsFAAOCAQEANUBJCuvGW01kAL427mw0PJjPj12vQeOEQY0l
X2nMXOhN35trkqsRbWpCo2h4bC412ILVZBDhVtdf5DtfRcaXYlYOc/iZVfDtG3ss
UdqIfzfAEU4XlZZ2VWddfiKpO3ZDecosITfUJRFREJge+IL7PM28hF40BD4+LhGj
9141IJgGBafPhdvAOy//oZZ21m+fueWrv9BEuU76W/4dkdgTrAbz7RLOSmLIygIs
FireaIP+hVZ/ZvTWA+x7aEIKq/UHBvMY7KAALreM/U6eZxkxRzerv30URvxOwpxr
m3P8f/2cIQOymZkitYy/1wGIzpBsG8M5XJudUo+lkJSfOpG9BA==
-----END CERTIFICATE REQUEST-----

dWQUBBn6Ru13spBN9bmYglpRVzTJOTMCAwEAATANBgkqhkiG9w0BAQsFAAOCAQEA
YXruSY4Dgo86yPoDuDMglchu1tpwjtrLXWNDsMWvTnW5oijUKr6A5ql2UaO71BKK
ww8eDTfsGsuwROl9QKA1J70EU/b60W0iygkCd63XJu3kPtmnMsT9480PErMePAul
qsx5ENRYo1k1fRt2DUN8l33/LOl+sC94n8GUtTgXwppMHVhqxmbKwBrIW1vMDN5b
fq38dJD3+zmrCgoP/ha+24DVapdD1PPwgzSchpbPmbJdm2+N7nfiKbJNisq6K6RQ
vbOKe9km9caHdAThx6wbe/zDs06h5eJeBhAGUxoIvk9ZnZsuf8wsTZDVtWudl1Nc
kEzLlYGXQvmkwOY0cM07CQ==
-----END CERTIFICATE-----
