# Task 2 – Vulnerability Assessment and Scan Analysis

## 1. Objective

The objective of this assessment was to perform network scanning and vulnerability assessment on the Metasploitable2 target using Nmap and OpenVAS.

The assessment focused on identifying open ports, running services, operating-system information, and security vulnerabilities.

## 2. Target Information

**Target:** Metasploitable2  
**Target IP:** 192.168.56.102  
**Scanner:** Kali Linux  
**Tools:** Nmap and OpenVAS / Greenbone

---

## 3. Nmap Scan Analysis

Nmap was used to identify network services and gather information about the target system.

### Scans Performed

- TCP SYN Scan (`-sS`)
- UDP Scan (`-sU`)
- Service Version Detection (`-sV`)
- Operating System Detection (`-O`)

### Findings

The Nmap scans identified multiple open and filtered ports on the Metasploitable2 system.

Service and version detection provided information about the applications and services running on the target.

OS detection was used to identify the operating-system characteristics of the target.

The detailed Nmap results are available in:

**Nmap_Scan_Report.pdf**

---

## 4. OpenVAS Vulnerability Analysis

OpenVAS / Greenbone was used to perform a vulnerability assessment of the target.

The completed scan identified vulnerabilities across four severity levels.

| Severity | Findings |
|---|---:|
| Critical | 13 |
| High | 9 |
| Medium | 43 |
| Low | 9 |

### Critical Findings

The Critical findings included serious security issues such as:

- MySQL default credentials
- Apache Tomcat AJP Ghostcat
- vsftpd 2.3.4 backdoor
- DistCC remote code execution
- VNC weak password
- Ingreslock backdoor
- PostgreSQL default credentials
- Other unauthenticated remote-access and code-execution issues

These findings represent the highest-priority risks identified during the assessment.

### High Findings

High-severity findings included:

- FTP default credentials
- PHP-CGI remote code execution
- EasyPHP authentication bypass
- HTTP PUT/DELETE enabled
- Java RMI insecure configuration
- rsh/rlogin exposed services
- OpenSSL CCS vulnerability

These findings could allow unauthorized access, code execution, or credential exposure.

### Medium Findings

The Medium category included weaknesses involving:

- Weak TLS/SSH configuration
- Web application vulnerabilities
- XSS and CSRF
- Outdated jQuery
- phpinfo() exposure
- Directory traversal
- Samba vulnerabilities
- Cleartext FTP and Telnet
- Legacy SSL/TLS protocols

These issues should be addressed as part of system hardening.

### Low Findings

Low-severity findings mainly involved:

- ICMP timestamp disclosure
- TCP timestamp disclosure
- Legacy cipher support
- Weak SSH MAC algorithms

These findings generally provide reconnaissance information or indicate weaker security configurations.

---

## 5. Risk Prioritization

The vulnerabilities were prioritized according to their severity and potential impact.

### Priority 1 – Critical

Critical vulnerabilities should be addressed first because they can provide direct remote access, code execution, database compromise, or root-level access.

### Priority 2 – High

High vulnerabilities should be remediated after Critical findings because they may provide significant unauthorized access or exploitation opportunities.

### Priority 3 – Medium

Medium findings should be addressed through patching, configuration hardening, and removal of unnecessary services.

### Priority 4 – Low

Low findings should be addressed during routine security hardening and configuration reviews.

---

## 6. Recommendations

The following security improvements are recommended:

1. Remove or disable unnecessary and vulnerable services.
2. Replace default and weak passwords with strong credentials.
3. Update outdated applications and operating-system components.
4. Disable legacy remote-access protocols such as Telnet, rsh, and rlogin.
5. Use secure protocols and encrypted communication.
6. Harden TLS and SSH configurations.
7. Disable unnecessary HTTP methods such as PUT and DELETE.
8. Reduce the exposed network attack surface.
9. Regularly perform vulnerability scans.
10. Rebuild or decommission intentionally vulnerable systems when they are no longer required for security training.

---

## 7. Conclusion

The Nmap and OpenVAS assessments provided a practical overview of the network services and security vulnerabilities present on the Metasploitable2 target.

Nmap helped identify ports, services, versions, and operating-system information, while OpenVAS provided vulnerability identification and severity classification.

The assessment demonstrates the importance of network reconnaissance, vulnerability scanning, risk prioritization, and security hardening in a controlled cybersecurity lab environment.
