# WebScanPro  
## Web Application Security Testing Tool  

**Branch:** Mohammad-Tausif-Branch  
**Batch:** 13  

---

# 📌 Milestone 1  
## Project Initialization, Setup & Target Scanning Module  

Milestone 1 covers the foundation of the WebScanPro project, including environment setup, application exploration, and development of the Target Scanning Module.

---

# 🔹 PART A – Week 1  
## Project Initialization and Environment Setup  

### 1. Introduction  

WebScanPro is a web application security testing tool designed to identify common vulnerabilities such as:

- SQL Injection  
- Cross-Site Scripting (XSS)  
- Broken Authentication  
- Other OWASP Top 10 issues  

The objective of Week 1 was to set up a vulnerable testing environment and explore the target application structure. This forms the foundation for developing automated vulnerability scanning modules.

---

### 2. Project Objectives  

- Understand OWASP Top 10 vulnerabilities  
- Develop automated security testing modules  
- Perform manual and automated testing  
- Generate structured vulnerability reports  
- Document findings with evidence  

For Week 1, the focus was limited to setup and exploration.

---

### 3. Tools & Technologies Used  

- **XAMPP** – Local server (Apache & MySQL)  
- **DVWA (Damn Vulnerable Web Application)** – Target vulnerable app  
- **PHP & MySQL** – Backend technologies  
- **Web Browser** – Application interaction  
- **Git & GitHub** – Version control  

---

### 4. Environment Setup  

#### XAMPP Setup
- Installed on Windows system  
- Apache and MySQL services started successfully  

#### DVWA Configuration
- DVWA placed inside `htdocs`  
- Created MySQL database named `dvwa`  
- Updated configuration file with correct credentials  
- Enabled required PHP settings  
- Database initialized successfully  

Application was accessed successfully using default credentials.

---

### 5. Application Structure Exploration  

The following DVWA modules were explored:

#### 🔹 Brute Force Module
Demonstrates weak authentication and lack of protection mechanisms.

#### 🔹 SQL Injection Module
Shows how improper input validation leads to database vulnerabilities.

#### 🔹 Cross-Site Scripting (XSS) Module
Demonstrates reflected XSS due to improper output sanitization.

Exploration was limited to understanding structure without exploitation.

---

### 6. Results & Observations  

**Results**
- DVWA successfully deployed  
- Vulnerability modules identified  
- Input-based testing surfaces documented  

**Observations**
- Low security level lacks protections  
- Vulnerabilities mainly due to improper input validation  
- DVWA is suitable for automated scanning development  

---

### 7. Week 1 Screenshots  

**XAMPP Control Panel**
![XAMPP](Week1/xampp_control_panel.png)

**DVWA Dashboard**
![DVWA Dashboard](Week1/dvwa_dashboard.png)

**Brute Force Module**
![Brute Force](Week1/bruteforce.png)

**SQL Injection Module**
![SQL Injection](Week1/sql_injection.png)

**XSS Module**
![XSS](Week1/xss_reflected.png)

---

# 🔹 PART B – Week 2  
## Target Scanning Module Implementation  

### 1. Objective  

To develop a Python-based target scanner that automatically identifies:

- Forms  
- Input fields  
- Form actions  
- HTTP methods  

This prepares metadata for automated vulnerability testing.

---

### 2. Technologies Used  

- **Python** – Core implementation  
- **Requests** – Sending HTTP requests  
- **BeautifulSoup** – Parsing HTML  
- **DVWA** – Target application  
- **XAMPP** – Local server  

---

### 3. Scanner Description  

A Python script named `scanner.py` was developed.

The scanner:

- Starts from the DVWA base URL  
- Sends HTTP requests  
- Parses HTML responses  
- Extracts `<form>` elements  
- Extracts input fields (name & type)  
- Stores structured output  
- Recursively crawls internal links  

This module performs discovery only and does not execute attacks.

---

### 4. Target Scanning Process  

1. Scanner starts from `http://localhost/dvwa/`  
2. HTTP request sent to retrieve page content  
3. HTML parsed using BeautifulSoup  
4. Forms and input fields extracted  
5. Data saved in structured format  

---

### 5. Output Generated  

#### output.json
- Structured scan results  
- Contains:
  - Page URL  
  - Form action  
  - HTTP method  
  - Input field names and types  

![Output JSON](Week2/output_json.png)

---

#### output.txt
- Human-readable scan results  
- Lists discovered forms and input fields  

![Output TXT](Week2/output_txt.png)

---

### 6. Scan Result Analysis  

The scanner successfully detected the DVWA login form and extracted:

- `username`
- `password`
- `user_token` (hidden CSRF token)
- `submit` button  

Internal pages require authentication; therefore, only the login page was scanned at this stage.

---

### 7. Execution & Verification  

Scanner executed successfully without errors.

![Scanner Run](Week2/scanner_run.png)

![Python Version](Week2/py_version.png)

---

### 8. Limitations  

- Works in unauthenticated mode  
- Cannot access internal DVWA pages  
- Session handling will be implemented in future milestones  

---

# ✅ Milestone 1 Outcome  

By the end of Milestone 1:

- Vulnerable test environment successfully configured  
- Application structure explored and documented  
- Attack surfaces identified  
- Functional target scanning module implemented  
- Structured metadata generated for automated testing  

Milestone 1 establishes the technical foundation for upcoming modules such as:

- SQL Injection Automation  
- XSS Testing  
- Authentication Testing  
- Report Generation  

---

# 🚀 Next Phase  

Milestone 2 will focus on implementing automated SQL Injection and vulnerability detection logic using the extracted metadata.
