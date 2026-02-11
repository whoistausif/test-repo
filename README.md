<div align="center">

# 🚀 WebScanPro  
### Web Application Security Testing Tool  

</div>

---

# 📌 Milestone 1  
## Project Setup & Target Scanning Module  

This milestone covers the initial setup of the project and development of a basic scanning module.

---

# 🔹 Week 1 – Project Initialization & Setup  

## 🔸 About the Project  

WebScanPro is a tool that will test web applications for common security problems such as:

- SQL Injection  
- Cross-Site Scripting (XSS)  
- Weak Authentication  
- Other common web security issues  

In Week 1, the goal was to set up the environment and understand how the vulnerable application works.

---

## 🔸 Tools Used  

- XAMPP (Local Server – Apache & MySQL)  
- DVWA (Damn Vulnerable Web Application)  
- PHP & MySQL  
- Web Browser  
- Git & GitHub  

---

## 🔸 What I Did in Week 1  

### 1️⃣ Installed and Configured Environment  

- Installed XAMPP  
- Started Apache and MySQL  
- Downloaded DVWA  
- Placed DVWA inside `htdocs`  
- Created a database named `dvwa`  
- Updated configuration settings  
- Initialized the database  

After this, DVWA was successfully running in the browser.

---

## 🔸 Explored Vulnerability Modules  

I explored different DVWA modules to understand how they work:

- **Brute Force Module** – Demonstrates weak login system  
- **SQL Injection Module** – Shows database-related vulnerability  
- **XSS Module** – Shows how malicious scripts can run in browser  

I only explored the structure and inputs. No full exploitation was performed.

---

## 🔸 Week 1 Result  

✔ DVWA successfully installed  
✔ Vulnerability pages identified  
✔ Input fields located  
✔ Environment ready for automation  

---

## 📸 Week 1 Screenshots  

![XAMPP](Week1/xampp_control_panel.png)  
![DVWA Dashboard](Week1/dvwa_dashboard.png)  
![Brute Force](Week1/bruteforce.png)  
![SQL Injection](Week1/sql_injection.png)  
![XSS](Week1/xss_reflected.png)  

---

# 🔹 Week 2 – Target Scanning Module  

## 🔸 Objective  

The goal of Week 2 was to create a Python scanner that automatically finds:

- Forms  
- Input fields  
- Form actions  
- HTTP methods  

This information will be used later for automated vulnerability testing.

---

## 🔸 Technologies Used  

- Python  
- Requests Library  
- BeautifulSoup  
- DVWA  
- XAMPP  

---

## 🔸 About scanner.py  

I created a Python script named `scanner.py`.

This script:

- Starts from DVWA homepage  
- Sends request to the website  
- Reads the HTML content  
- Finds all `<form>` elements  
- Extracts:
  - Form action  
  - Method (GET/POST)  
  - Input names  
  - Input types  
- Saves the results into files  

The scanner does not attack the website.  
It only collects useful information.

---

## 🔸 How the Scanner Works  

1. Starts from `http://localhost/dvwa/`  
2. Sends HTTP request  
3. Parses HTML using BeautifulSoup  
4. Extracts forms and inputs  
5. Saves results in output files  

---

## 🔸 Output Files Generated  

### 📄 output.json  
Contains structured data:
- Page URL  
- Form action  
- Method  
- Input names and types  

![Output JSON](Week2/output_json.png)

---

### 📄 output.txt  
Human-readable scan result  

![Output TXT](Week2/output_txt.png)

---

## 🔸 Scan Results  

The scanner detected the DVWA login form and found:

- username  
- password  
- user_token (hidden field)  
- submit button  

Since DVWA requires login, only the login page was scanned.

---

## 📸 Week 2 Screenshots  

![Scanner Run](Week2/scanner_run.png)  
![Python Version](Week2/py_version.png)  

---

## 🔸 Limitations  

- Scanner does not login yet  
- Internal pages are not accessible  
- Session handling will be added later  

---

# ✅ Milestone 1 Summary  

In Milestone 1:

✔ Local testing environment was set up  
✔ DVWA was configured successfully  
✔ Vulnerability modules were explored  
✔ A working Python scanner was developed  
✔ Forms and input fields were extracted  
✔ Structured output files were generated  

Milestone 1 builds the foundation for developing a complete automated web security testing tool.
