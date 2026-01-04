# Assignment 3 – Website Cloning & SMB Vulnerability Scanning Labs

## Overview

This repository documents two practical cybersecurity labs completed as part of Assignment 3 with **parocyber**:

1. **Website Cloning Lab** – Reproduction of the website cloning exercise demonstrated duringa a session with parocyber.
2. **SMB Vulnerability Scanning Lab** – Reproduction of the SMB enumeration and vulnerability scanning exercise using **Enum4Linux** from Sunday’s session.

Both labs were conducted strictly in an **educational and ethical context**, using authorized targets for learning and testing purposes only.

---

## Lab 1: Website Cloning Lab

### Objective

The objective of this lab was to understand how website cloning tools work, how web content can be mirrored locally, and to recognize the **security implications and ethical considerations** associated with website cloning.

This exercise was performed **for educational purposes only**, on a permitted target, without credential harvesting or malicious deployment.

---

### Tools Used

* Kali Linux Virtual environment
* Website cloning tool demonstrated in class (e.g., `httrack` / `wget`)
* Web browser (for local testing)

---

### Target Setup

* Target website: **Authorized test website**
* Environment: VM Kali Linux machine
* Network: Controlled lab environment

---

### Commands Used

Example command used to clone a website:

```bash
httrack http://target-website.com -O cloned-site
```

Alternative command 
```bash
wget --mirror --convert-links --adjust-extension --page-requisites --no-parent http://target-website.com
```

---

### Process Summary

1. The cloning tool was launched from the Kali Linux terminal.
2. The target URL was specified.
3. Website files (HTML, CSS, JavaScript, images) were downloaded locally.
4. The cloned website was opened in a browser to verify functionality.
5. No login pages were exploited and no credentials were captured.

---

### Findings & Observations

* Static websites clone more accurately than dynamic sites.
* Server-side functionality (e.g., login authentication, databases) does not clone.
* Improper protections can allow attackers to replicate branding for phishing.
* Website cloning highlights the importance of:

  * HTTPS
  * Anti-phishing controls
  * Security awareness

---

### Ethical Considerations

Website cloning can be abused for phishing and impersonation.
This lab was conducted **strictly for learning and defensive awareness**, emphasizing:

* Authorization
* Legal boundaries
* Responsible security testing

---

### Screenshots include

* Tool execution
* Cloning progress
* Local website preview


---

## Lab 2: SMB Vulnerability Scanning Using Enum4Linux

### Objective

The objective of this lab was to identify **SMB-related information disclosures and weaknesses** using Enum4Linux, and to understand how misconfigured SMB services can expose sensitive system details.

---

### Tools Used

* Kali Linux
* Enum4Linux
* Metasploitable 
---

### Target Setup

* Target IP address: `192.168.X.X`
* SMB service enabled on the target
* Network: Isolated lab environment

---

### Commands Used

Basic SMB enumeration:

```bash
enum4linux 192.168.X.X
```

Verbose scan:

```bash
enum4linux -a 192.168.X.X
```

User enumeration:

```bash
enum4linux -U 192.168.X.X
```

Share enumeration:

```bash
enum4linux -S 192.168.X.X
```

---

### Process Summary

1. Target system was confirmed to be reachable.
2. Enum4Linux was executed against the SMB service.
3. Enumeration results were collected and analyzed.
4. Information disclosure risks were identified.

---

### Findings

The scan revealed the following (depending on target configuration):

* List of valid system users
* SMB shares and access permissions
* Operating system information
* Workgroup/domain name
* Anonymous login availability 

---

### Security Implications

* Anonymous SMB access can expose sensitive information.
* User enumeration aids brute-force and lateral movement attacks.
* Proper SMB hardening is critical:

  * Disable null sessions
  * Restrict anonymous access
  * Enforce strong authentication
  * Use firewall rules

---

### Screenshots include

* Enum4Linux command execution
* Enumeration output

---

## Conclusion

These labs provided practical insight into:

* How attackers replicate web content
* How SMB services can leak system information
* Why ethical boundaries and authorization are essential in cybersecurity testing

Both exercises reinforced the importance of **secure configurations, awareness, and responsible testing practices**.

---

## Disclaimer

All activities documented in this repository were performed **solely for educational purposes** in a controlled lab environment on authorized systems.
No illegal or unauthorized testing was conducted.
