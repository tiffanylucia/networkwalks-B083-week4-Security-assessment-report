# networkwalks-B083-week4-Security-assessment-report
Security assessment report
# Milestone 1: Security Assessment Report
**Target:** Mediroza General Hospital (`https://medirozahospital.com/`)  
**Scope:** Reconnaissance, Entry Point Identification, Authentication Analysis, and Access Control Evaluation  

## 1. Executive Summary
This report outlines the findings and reconnaissance phase of the security assessment conducted against the Mediroza General Hospital web application running **Mediroza CMS 1.4.2** on a **LiteSpeed** web server. The primary objective of Milestone 1 was to map the attack surface, identify exposed entry points, analyze authentication mechanisms, and assess input handling weaknesses to gain unauthorized access to restricted patient reports.

## 2. Reconnaissance & Asset Discovery
Initial active and passive reconnaissance successfully mapped the application's directory structure and exposed administrative artifacts:
* **Server Stack Identification:** The target runs on LiteSpeed Web Server with PHP/8.2.33.
* **Exposed Backup Artifacts:** Enumeration of legacy and unlinked directories revealed an active directory listing (Autoindex) under `/old/`, containing an outdated database backup file: `mediroza_db_backup_2019.sql`.
* **Portal Discovery:** Two primary restricted portals were identified:
  * **Patient Portal:** Located at `/patient/` (containing `portal.php`, `login.php`, `download.php`, and an exposed `error_log`).
  * **Staff Portal:** Located at `/staff/login.php`.

## 3. Analysis of Authentication Mechanisms
The application implements session-based authentication protecting restricted resources:
* **Redirect Logic:** Accessing protected resources results in an HTTP `302 Found` redirect to `login.php`, accompanied by the generation of a `PHPSESSID` cookie.
* **Header Bypass Testing:** Attempts to bypass authentication controls using simulated local IP headers (`X-Forwarded-For: 127.0.0.1`) were unsuccessful.

## 4. Deliverables & Verification
* **Milestone Status:** Completed. All reconnaissance goals, entry point identifications, and authentication behavioral analyses have been thoroughly documented.
  "C:\Users\Tiffany Lucia\OneDrive\Desktop\Security Assessment Report 1.pdf"
