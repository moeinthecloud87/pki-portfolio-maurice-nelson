# Lab 01 — Environment Verification & VM Connectivity Check

**Maurice Nelson:**  
**5-25-2026:**  
**Phase:** 2 | **Week:** 9  
**Submission Path:** labs/week-09/lab-01-environment-verification.md

---

## Step 1 — VM Startup & Login

VMs started in correct order (DC01 → PKI-SRV01): Yes / No

Login credentials table:

| VM         | Account Used        | Login Successful? |
|------------|---------------------|-------------------|
| DC01       | CORP\pki.admin      |      Yes          |
| PKI-SRV01  | CORP\pki.admin      |       Y            |
| Root-CA    | .\Administrator     |       Y            |

Notes / issues encountered:
(paste here)

---

## Step 2 — VM Connectivity Test

Command: `Test-Connection -ComputerName DC01 -Count 2`

Output:
```
(paste here)
```

DC01 responded successfully: Yes / No Yes

---

## Step 3 — CertSvc Service Status

Command: `Get-Service -Name CertSvc`

Output:
```
(paste here)
```

Status confirmed as Running: Yes / No

---

## Step 4 — certsrv.msc Console Verification

- CVI Issuing CA 1 visible: Yes / No
- Console icon status (green/red):
- Nodes visible: (list here)

---

## Step 5 — CertLog Folder Contents

Command: `Get-ChildItem "C:\Windows\System32\CertLog"`

Output:
```
(paste here)
```

---

## Reflection

- One thing that went well:
- One thing that was confusing or unexpected:
