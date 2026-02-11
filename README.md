# 🚀 WebScanPro  
## 🔐 Web Application Security Testing Tool  

---

# 📌 Milestone 1  
## Week 1 – Project Initialization & Setup  
## Week 2 – Target Scanning Module  

---

# 🔹 Week 1 - Project Initialization and Setup  

## 1️⃣ Introduction  

WebScanPro is a web application security testing tool designed to identify common vulnerabilities in web applications, such as SQL Injection, Cross-Site Scripting (XSS), broken authentication, and other OWASP Top 10 issues.  

The purpose of this project is to develop a structured and automated approach to web application security testing. During Week 1, the focus was on understanding the project scope, setting up a vulnerable test environment, and exploring the target application to identify potential testing surfaces.  

This initial phase forms the foundation for developing automated vulnerability scanning modules in later stages of the project.

---

## 2️⃣ Project Objectives  

The primary objectives of the WebScanPro project are:

- To understand common web application vulnerabilities as defined by OWASP Top 10  
- To develop modules for detecting different types of security vulnerabilities  
- To perform both manual and automated security testing  
- To generate structured security reports with mitigation suggestions  
- To prepare detailed documentation and presentation of findings and results  

For Week 1, the objective was limited to project initialization, environment setup, and application exploration.

---

## 3️⃣ Project Planning  

The project was planned using a week-wise milestone-based approach. Each week focuses on a specific module of the WebScanPro tool.

### Week 1 Plan:
- Define project goals and scope  
- Select tools and technologies  
- Set up a vulnerable web application locally  
- Explore application structure and functionality  

This phased planning ensures a clear progression from understanding vulnerabilities to automating their detection and reporting.

---

## 4️⃣ Tools and Technology Selection  

The following tools and technologies were selected for the project:

- **XAMPP** – Used as a local server environment (Apache & MySQL)  
- **DVWA (Damn Vulnerable Web Application)** – Used as an intentionally vulnerable application for testing  
- **PHP & MySQL** – Backend technologies used by DVWA  
- **Web Browser** – For accessing and interacting with the application  
- **Git & GitHub** – For version control and documentation tracking  

These tools were chosen because they are widely used, open-source, and suitable for learning and testing web application security concepts.

---

## 5️⃣ Environment Setup (Findings – Part 1)  

### XAMPP Setup  
XAMPP was installed on a Windows system to provide a local testing environment. Apache and MySQL services were successfully started to support the DVWA application.

### DVWA Configuration  
The DVWA application was downloaded and placed inside the htdocs directory of XAMPP. A dedicated MySQL database named dvwa was created using phpMyAdmin. Configuration files were updated with correct database credentials, and required PHP settings were enabled.

### Successful Deployment  
The DVWA database was initialized using the setup interface, and the application was accessed successfully via the browser. Login using default credentials confirmed that the setup was completed correctly.

This step validated that the testing environment was ready for further security analysis.

---

## 6️⃣ Application Structure Exploration  

After successful deployment, the structure of the DVWA application was explored to understand its components and vulnerability modules.

### 🔹 Brute Force Module  
This module contains a login interface designed to demonstrate weak authentication mechanisms. It represents scenarios where applications lack proper protections such as rate limiting and account lockout.

### 🔹 SQL Injection Module  
The SQL Injection module provides input fields that interact directly with backend database queries. It highlights how improper input handling can lead to database-related vulnerabilities.

### 🔹 Cross-Site Scripting (XSS) Module  
The Reflected XSS module reflects user input back to the browser. This module demonstrates how malicious scripts can be executed if user input is not properly sanitized.

The exploration was limited to understanding the structure and inputs without performing exploitation.

---

## 7️⃣ Results and Observations  

### Results
- DVWA was successfully installed and configured on a local server  
- Multiple vulnerability modules were identified and accessed  
- Input-based testing surfaces were clearly documented  

### Observations
- The application intentionally lacks security controls at low security levels  
- Most vulnerabilities arise due to improper input validation  
- DVWA provides a suitable environment for mapping vulnerabilities to automated scanning logic  

These observations will guide the development of WebScanPro’s automated testing modules.

---

## 8️⃣ Screenshots and Evidence  

Screenshots were captured to provide visual evidence of the work performed.

**XAMPP Control Panel showing running services**


**DVWA home dashboard**


**Brute Force module interface**


**SQL Injection module interface**


**XSS (Reflected) module interface**


---

## 9️⃣ Conclusion (Week 1 Summary)  

Week 1 successfully completed the project initialization phase. The project goals and plan were defined, tools were selected, and DVWA was configured as a testing platform. The application structure and vulnerability modules were explored, and findings were documented with screenshots.

---

# 🔹 Week 2 – Target Scanning Module  

## 1️⃣ Objective of Week 2  

The objective of Week 2 was to develop a target scanning module that can automatically analyze a web application and identify attack entry points such as forms and input fields.

This module prepares the groundwork for automated vulnerability testing in later stages.

---

## 2️⃣ Tools & Technologies Used  

- **Python** – For implementing the scanner logic  
- **Requests Library** – To send HTTP requests to the target application  
- **BeautifulSoup** – To parse HTML and extract interactive elements  
- **DVWA (Damn Vulnerable Web Application)** – Target application  
- **XAMPP** – Local server environment  
- **Git & GitHub** – Version control and submission  

---

## 3️⃣ Description of the Target Scanner  

The scanner is a Python-based crawler that starts from a target URL and performs the following tasks:

- Sends HTTP requests to the target web application  
- Parses HTML responses  
- Identifies web forms and input fields  
- Extracts metadata required for automated testing  

This scanner does not perform attacks; it only discovers potential entry points.

---

## 4️⃣ Scanner Implementation  

A Python script named `scanner.py` was developed.  

It uses the BeautifulSoup library to analyze the HTML structure of the DVWA login page.

Key functionalities:

- Detects `<form>` elements  
- Extracts form attributes (action, method)  
- Extracts all `<input>` fields including:
  - Text inputs  
  - Password fields  
  - Submit buttons  
  - Hidden CSRF tokens  

---

## 5️⃣ Target Scanning Process (Step-by-Step)  

1. The scanner starts from the DVWA base URL (http://localhost/dvwa/)  
2. An HTTP request is sent to retrieve the page content  
3. The HTML response is parsed using BeautifulSoup  
4. Forms and input fields are extracted from the page  
5. Extracted data is structured and saved for later testing  

---

## 6️⃣ Output Generated  

### 6.1 output.json  

- Contains structured scan results  
- Stores:
  - Page URL  
  - Form action  
  - HTTP method  
  - Input field names and types  
- Used for automation in future testing modules  



---

### 6.2 output.txt  

- Human-readable version of scan results  
- Clearly lists discovered forms and input fields  



---

## 7️⃣ Scan Result Analysis  

The scanner successfully detected the DVWA login form and extracted the following input fields:

- username  
- password  
- user_token (hidden CSRF token)  
- submit button  

DVWA internal pages require authentication; therefore, only the login page was scanned at this stage, which is expected behavior.

---

## 8️⃣ Execution & Verification  

The scanner was executed successfully using the Python launcher.  
The execution generated output files without errors.




---

## 9️⃣ Limitations  

- The scanner currently works in an unauthenticated mode  
- Internal DVWA pages are not accessible without login  
- Advanced crawling with session handling will be implemented in future phases  

---

## 🔟 Outcome of Week 2  

- A functional target scanning module was implemented  
- Entry points such as forms and input fields were successfully identified  
- Extracted metadata is ready to be used in Week 3: Automated SQL Injection Module  

---

## 1️⃣1️⃣ Conclusion  

Week 2 successfully established the foundation for automated security testing by implementing a scanner that identifies and records attack surfaces within the target web application.
