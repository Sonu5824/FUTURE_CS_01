# Security Testing Report – Task 1 (FUTURE INTERNS)

## 1. Executive Summary
This report documents the findings from security testing on a sample web application (TryHackMe Revenge room).  
The main vulnerability identified was **SQL Injection**.

---

## 2. Scope & Tools Used
- Nmap – Port scanning
- WhatWeb – Technology fingerprinting
- Burp Suite – Manual SQLi testing
- SQLMap – Automated SQLi exploitation

---

## 3. Findings

### Vulnerability: SQL Injection
- **Description:** The application fails to validate user input, allowing attackers to inject malicious SQL queries.
- **Impact:** Attackers can access sensitive database data.
- **Proof of Concept:**
    
    - SQLMap Dump: ![SQLMap Dump]
- **Mitigation:** Use prepared statements and parameterized queries.

---

## 4. Other Tests
- **XSS:** No vulnerability found
- **Authentication Flaws:** No vulnerability found

---

## 5. Conclusion
SQL Injection was successfully identified and exploited. Recommendations have been provided to mitigate the issue.


Scope: “Web application available at target IP (controlled lab). Testing window: <30-08-2025>; methods limited to web traffic only.”

Assumptions & Rules of Engagement: “Testing performed in an isolated, educational environment. No production systems.”

Environment & Tool Versions: “Parrot attacker VM; Burp Suite Community; sqlmap 1.7+; nmap 7.94+.”

Clear result statement: “Confirmed SQL Injection; no XSS found; no auth flaws found after testing.”

Mitigation (SQLi): Parameterized queries/prepared statements, ORM parameter binding, strict input validation, least-privileged DB account.

Appendix – Commands (copy/paste friendly)

nmap -sV -p- <TARGET_IP> -oN nmap.txt
whatweb http://<TARGET_IP> -v > whatweb.txt
gobuster dir -u http://<TARGET_IP> -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -o gobuster.txt
sqlmap -u "http://<TARGET_IP>/vuln.php?id=1" --batch --dbs


