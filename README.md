<div align="center">

# 🚀 WEBCANPRO – WEB APPLICATION SECURITY TESTING TOOL 🚀  
### 🔐 BATCH 13 | CAPSTONE PROJECT  

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![Security](https://img.shields.io/badge/Focus-Web%20Security-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Milestone-1%20Completed-success?style=for-the-badge)

</div>

---

# 📌 MILESTONE 1  
## ⚙️ Project Setup & Target Scanning Module  

This milestone includes environment setup, manual vulnerability testing, and development of the first scanning module.

---

# 🛠️ WEEK 1 – PROJECT INITIALIZATION & SETUP  

## 🔍 About the Project  

WebScanPro is a security tool that checks web applications for common problems like:

- 💉 SQL Injection  
- ⚡ Cross-Site Scripting (XSS)  
- 🔐 Weak Login Systems  
- 🛡️ Other common web security issues  

The goal of Week 1 was to prepare the environment and understand how the vulnerable application works.

---

## 🧰 Tools Used  

- 🖥️ XAMPP (Apache & MySQL)  
- 🌐 DVWA (Damn Vulnerable Web Application)  
- 🗄️ PHP & MySQL  
- 🌍 Web Browser  
- 🗂️ Git & GitHub  

---

## ⚙️ Environment Setup  

✔ Installed XAMPP  
✔ Started Apache & MySQL  
✔ Installed DVWA  
✔ Created `dvwa` database  
✔ Configured files  
✔ Successfully launched application  

---

## 🧪 Manual SQL Injection Testing  

During exploration, I manually tested SQL Injection using:
```
' OR '1'='1
```

This was done to check how the application handles unsafe input.

### 💉 Manual SQL Injection Screenshot
![Manual SQL Injection Test](Week-1/screenshots/manual-sql-injection-test.png)

---

## 📸 Week 1 Screenshots  

### 🖥️ XAMPP Running
![XAMPP Running](Week-1/screenshots/xampp-running.png)

### 🏠 DVWA Dashboard
![DVWA Dashboard](Week-1/screenshots/dvwa-dashboard.png)

### 🔐 Brute Force Module
![Brute Force Page](Week-1/screenshots/dvwa-bruteforce-page.png)

### 💉 SQL Injection Module
![SQL Injection Page](Week-1/screenshots/dvwa-sql-injection-page.png)

### ⚡ XSS Module
![XSS Reflected Page](Week-1/screenshots/dvwa-xss-reflected-page.png)

---

# 🤖 WEEK 2 – TARGET SCANNING MODULE  

## 🎯 Objective  

Create a Python scanner that automatically detects:

- 📝 Forms  
- ⌨️ Input fields  
- 🔁 HTTP methods  
- 🎯 Form actions  

---

## 🧠 scanner.py Overview  

The `scanner.py` script:

- Starts from DVWA homepage  
- Sends HTTP requests  
- Parses HTML using BeautifulSoup  
- Detects `<form>` elements  
- Extracts input names and types  
- Saves structured results  

⚠️ It does NOT attack the website — it only collects metadata.

---

## 🔄 How It Works  

1. Load `http://localhost/dvwa/`  
2. Send request  
3. Parse HTML  
4. Extract forms & inputs  
5. Save results  

---

## 📄 Output Files  

### 📊 output.json
Stores structured scan data.

![Output JSON](Week-2/screenshots/output_json.png)

---

### 📄 output.txt
Readable scan results:

```
=== Discovered URLs ===
=== Forms & Input Fields ===
{'page': 'http://localhost/dvwa/
', 'action': 'login.php', 'method': 'post', 'inputs': [...]}
```

---

## 📸 Week 2 Screenshots  

### ▶ Scanner Execution
![Scanner Run](Week-2/screenshots/scanner_run.png)

### 🐍 Python Version
![Python Version](Week-2/screenshots/py_version.png)

---

# ⚠️ Limitations  

- Scanner does not handle login session  
- Internal pages cannot be scanned yet  
- Advanced session handling will be added later  

---

# ✅ MILESTONE 1 COMPLETED  

✔ Local testing environment configured  
✔ DVWA successfully deployed  
✔ Manual SQL injection tested  
✔ Python scanning module implemented  
✔ Forms & input fields extracted  
✔ Structured outputs generated  

---

<div align="center">

## 🚀 Foundation Built for Advanced Web Security Automation 🚀

</div>
