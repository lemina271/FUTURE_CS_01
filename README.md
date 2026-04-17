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
<img width="962" height="297" alt="nmap scan" src="https://github.com/user-attachments/assets/65674acc-333a-4e36-946f-13c2f377db21" />


### 🔹 Command Used: nmap -A testfire.net
<img width="1540" height="777" alt="nmapscan 2" src="https://github.com/user-attachments/assets/41f7696d-4eda-4095-a567-a5302f2ddca6" />


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
<img width="1782" height="518" alt="zap3" src="https://github.com/user-attachments/assets/a8b23f86-4b95-4bb1-ac60-9a1196734f67" />
<img width="673" height="422" alt="zap4" src="https://github.com/user-attachments/assets/749cf207-9c5a-4a54-a601-670ebc154ce6" />
<img width="1917" height="552" alt="zap5" src="https://github.com/user-attachments/assets/a310fef7-3645-4cce-bebf-18ea5fae191e" />


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
<img width="1912" height="757" alt="devtool2" src="https://github.com/user-attachments/assets/36ec1c42-27db-4702-aeb8-cb73dfa75521" />


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
