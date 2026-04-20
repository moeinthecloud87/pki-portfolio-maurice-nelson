# My PKI Toolkit

**CVI PKI Career Pathway — Phase 1 Foundations**

Completed: [04/2026]

---

## About This Document

[2–3 sentences describing what this document is and why you built it. Write in your own words.]

---

## Core Command-Line Tools

### openssl x509 — [Brief description]

**What it does:**
This defines the format of Certificates (Object, Validity Period, Version, extensions such as a SAN)
**When to use it:**
Use this anytime you want to create and/or verify a detail in a cert
**Example command from my labs:**

```bash
[openssl x509 -in leaf_cert.pem -outform DER -out leaf_cert.der
]
```

**What the output tells you:**
This command takes the .PEM file and turns it into a .DER file 
**Phase 1 source:** Week [4], [Convert Certificate Formats]

### openssl s_client — [Brief description]

**What it does:**
Connects to live Certificates by creating a TLS handshake between my browser an the site 
**When to use it:**
When you want to verify connections, and view certificates
**Example command from my labs:**

```bash
[openssl s_client -connect google.com:443 -showcerts]
```

**What the output tells you:**
This command connects to google.com and retrieves it's leaf certificate
**Phase 1 source:** Week [4], [Convert Certificate formats]

### openssl req — [Brief description]

**What it does:**

**When to use it:**

**Example command from my labs:**

```bash
[real command from your Phase 1 submissions]
```

**What the output tells you:**

**Phase 1 source:** Week [X], [Lab name]

### openssl verify — [Brief description]

**What it does:**

**When to use it:**

**Example command from my labs:**

```bash
[real command from your Phase 1 submissions]
```

**What the output tells you:**

**Phase 1 source:** Week [X], [Lab name]

### openssl ocsp — [Brief description]

**What it does:**

**When to use it:**

**Example command from my labs:**

```bash
[real command from your Phase 1 submissions]
```

**What the output tells you:**

**Phase 1 source:** Week [X], [Lab name]

### openssl pkcs12 — [Brief description]

**What it does:**
Self Signs a Cert or Makes a request for one.
**When to use it:**
When you want to make a Certificate request.
**Example command from my labs:**

```bash
[real command from your Phase 1 submissions]
```

**What the output tells you:**

**Phase 1 source:** Week [X], [Lab name]

[Add any additional openssl subcommands from your lab history]

---

## Network and Inspection Tools

### curl — [Brief description]

**What it does:**
This command allows you to transfer data to and from a server, and check and verify connectivity after changing a configuration.
**When to use it:**

**Example command from my labs:**

```bash
[real command from your Phase 1 submissions]
```

**What the output tells you:**

**Phase 1 source:** Week [X], [Lab name]

[Add any others you used]

---

## Reference and Analysis Services

### SSL Labs SSL Server Test — [Brief description]

**What it does:**
looks at hostnames and shows different information about their certs
**When to use it:**
When looking 
**What to look for in the output:**
Validity dates, different Certificate Authorities, 
**Phase 1 source:** Week [X], [Lab name]

### crt.sh — Certificate Transparency Search — [Brief description]

**What it does:**
Logs hostnames and their subdomains
**When to use it:**
Research domains to make sure 
**What to look for in the output:**
ID, logged at, validity period of the cert, SAN, Mismatching names
**Phase 1 source:** Week [X], [Lab name]

---

## Phase 1 Skills Summary

[3–5 sentences summarizing what Phase 1 built as a whole and how these tools connect to real PKI operational work. Written in your own words.]
