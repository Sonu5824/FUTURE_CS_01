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

