# FUTURE_CS_01
Cyber Security Internship Tasks - Future Interns

#  Task 1 - Vulnerability Assessment Report

##  Author
Lemina K  
Cyber Security Intern - Future Interns  

---

##  Objective

The objective of this assessment is to identify security weaknesses in a public website using safe and ethical testing techniques.

This analysis focuses on identifying risks, explaining their impact, and suggesting practical remediation steps.

---

##  Target Website

http://testfire.net/

---

##  Scope

- Public-facing pages only  
- Read-only analysis (no exploitation)  
- Ethical and passive testing  

---

##  Tools Used

- Nmap → Port and service analysis  
- OWASP ZAP → Passive vulnerability scanning  
- Browser DevTools → Header and cookie analysis  

---

#  Analysis & Findings

---

## 📡 1. Nmap Scan

### 🔹 Command Used: nmap -sV testfire.net

### 📸 Screenshot:
<img width="962" height="297" alt="nmap scan" src="https://github.com/user-attachments/assets/d12b7ad7-312a-473c-8a74-484cbd4e7986" />


### 🔹 Command Used: nmap -A testfire.net
<img width="1540" height="777" alt="nmapscan 2" src="https://github.com/user-attachments/assets/597509ef-e0f1-468c-8a83-d4177707360e" />


###  Findings:

**Open HTTP Port (80)**  
- Risk: Medium  
- Data is transmitted without encryption  

**Server Information Disclosure**  
- Risk: Low  
- Server version is visible  

---

##  2. OWASP ZAP Analysis

### 📸 Alerts Overview:
<img width="1782" height="518" alt="zap3" src="https://github.com/user-attachments/assets/4a3513fb-9ac3-4fdb-a3ab-e5c178c5719a" />
<img width="673" height="422" alt="zap4" src="https://github.com/user-attachments/assets/c5f02b02-3337-4938-8b6c-3a3ee1d164cc" />
<img width="1918" height="575" alt="zap6" src="https://github.com/user-attachments/assets/8e6526bc-5d38-4cf6-b8c5-829ed674791d" />


###  Findings:

**Absence of Anti-CSRF Tokens**  
- Risk: Medium  
- Allows unauthorized actions  

**Missing Content Security Policy**  
- Risk: Medium  
- Risk of XSS attacks  

**Missing Anti-clickjacking Header**  
- Risk: Low  
- Vulnerable to clickjacking  

**Cookie Without SameSite Attribute**  
- Risk: Medium  
- Risk of CSRF attacks  

---

##  3. Browser DevTools Analysis

### 📸 Headers:
<img width="1912" height="757" alt="devtool2" src="https://github.com/user-attachments/assets/43739dc6-12f5-4947-a30d-aea9aa5a2d11" />


###  Findings:

**Missing Security Headers**  
- Risk: Medium  
- Missing CSP, X-Frame-Options  

---

### 📸 Cookies:
<img width="562" height="458" alt="devtool3" src="https://github.com/user-attachments/assets/bdca2b6b-81cd-46ad-bde9-9c12e17ae1dd" />


**Insecure Cookie Configuration**  
- Risk: Medium  
- Missing Secure, HttpOnly, SameSite  

---

#  Risk Summary

| Vulnerability | Risk Level |
|--------------|-----------|
| Open HTTP Port | Medium |
| Server Information Disclosure | Low |
| Missing CSP | Medium |
| Missing CSRF Protection | Medium |
| Clickjacking Issue | Low |
| Insecure Cookies | Medium |

---

#  Conclusion

The assessment identified several security weaknesses related to missing protections and configuration issues.

These vulnerabilities could be exploited by attackers if not addressed properly.

Implementing the recommended fixes will improve the security posture of the application.

---

#  Recommendations

- Enforce HTTPS  
- Add security headers  
- Secure cookies properly  
- Hide server information  
- Perform regular security testing  

---


#  Learning Outcome

- Learned vulnerability assessment process  
- Understood real-world security risks  
- Gained hands-on experience with security tools  
