---

#🔐 Password Strength Analyzer – Evaluating Password Security Levels

#🎯 Project Overview

This project demonstrates the implementation and use of a Password Strength Analyzer that evaluates the strength of a given password based on predefined criteria. The goal is to promote awareness around password hygiene and simulate how weak credentials can be detected in cybersecurity systems.

---

## 🧰 Tools & Environment

Component	Specification

Operating System	Windows 10/11 or Linux
Development Tools	Python 3.x, VS Code / IDLE
Libraries Used	re, string, getpass
Optional	Web-based GUI using Tkinter (future scope)

---

## ⚙ Lab Setup Instructions

1. Ensure Python 3.x is installed on your system.
2. Create a Python file password_analyzer.py.
3. Run the script via terminal or IDE to input and analyze passwords.


---

## 🔍 Scanning workflowo

The analyzer checks a password against multiple criteria:

✅ Minimum length of 8 characters
✅ Contains both uppercase and lowercase letters
✅ Includes numbers
✅ Includes special characters
✅ Not found in common passwords list (if provided)


Each criterion contributes to a score and final strength category.

---

🧪 Sample Python Script

import re
import string

def check_strength(password):
    score = 0
    criteria = {
        'length': len(password) >= 8,
        'upper': re.search(r'[A-Z]', password),
        'lower': re.search(r'[a-z]', password),
        'digit': re.search(r'[0-9]', password),
        'special': re.search(r'[' + re.escape(string.punctuation) + ']', password)
    }

    for key, passed in criteria.items():
        if passed:
            score += 1

    if score == 5:
        strength = "🟢 Strong"
    elif score >= 3:
        strength = "🟡 Moderate"
    else:
        strength = "🔴 Weak"

    return strength, criteria

# Demo
if _name_ == "_main_":
    password = input("Enter password to analyze: ")
    strength, checks = check_strength(password)

    print(f"\nPassword Strength: {strength}")
    for criterion, passed in checks.items():
        print(f"{criterion.capitalize():<10}: {'✔' if passed else '❌'}")


---

## 📸 Sample Output

Enter password to analyze: P@ssw0rd2025

Password Strength: 🟢 Strong
Length    : ✔
Upper     : ✔
Lower     : ✔
Digit     : ✔
Special   : ✔

---

## 🧾 Scan Results Summary

✅ Criteria Evaluated:

Minimum Length ≥ 8
Contains Uppercase Letter
Contains Lowercase Letter
Contains Digit
Contains Special Character

---

## 📋 Summary Table

The following table highlights the results of analyzing different types of passwords using the tool. Each password is checked against five core strength criteria.


| Password      | Length | Upper | Lower | Digit | Special | Strength    | Notes                          |
|---------------|--------|-------|-------|-------|---------|-------------|--------------------------------|
| 123456        | ❌    | ❌    | ❌   | ✔     | ❌      | 🔴 Weak     | Too short, only numbers        |
| password      | ✔     | ❌    | ✔    | ❌    | ❌      | 🔴 Weak     | No uppercase, digits, or symbols |
| Password1     | ✔     | ✔     | ✔    | ✔     | ❌      | 🟡 Moderate | No special characters          |
| P@ssw0rd      | ✔     | ✔     | ✔    | ✔     | ✔       | 🟢 Strong   | Meets all criteria             |
| Admin!2025    | ✔     | ✔     | ✔    | ✔     | ✔       | 🟢 Strong   | Well-balanced and secure       |
| letmein       | ❌    | ❌    | ✔    | ❌    | ❌      | 🔴 Weak     | Common and insecure            |
| Sun@Rise89    | ✔     | ✔     | ✔    | ✔     | ✔       | 🟢 Strong   | Strong password                |

---

## 📈 Strength Distribution (Sample Set)

Strength Level	Count

🟢 Strong	3
🟡 Moderate	1
🔴 Weak	3

---

> 🔐 Observation: Most weak passwords failed multiple criteria. Strong passwords consistently included uppercase, lowercase, numbers, and special characters while being 8+ characters long.


## 📊 Comparison Summary

Password	       Strength	        Notes

123456	          🔴 Weak	       Too short, numeric only
Password1         🟡 Moderate	   No special characters
P@ssw0rd2025      🟢 Strong	       Meets all criteria

---

## 🚧 Challenges & Resolutions

Challenge	Resolution

Detecting special characters	Used string.punctuation with regex
Input masking (secure entry)	Can use getpass module in CLI version
Overly basic rules	Future enhancement: entropy calculation

---

## 📘 Key Takeaways

Learned how to implement password strength validation using Python.
Understood the importance of combining character sets for stronger passwords.
Gained hands-on experience with regex and basic input sanitization.

---

## 🚀 Future Enhancements

[ ] Add GUI interface using Tkinter or Flask
[ ] Integrate with a database to check against known breached passwords
[ ] Use entropy-based strength calculations (zxcvbn-style)
[ ] Export password strength reports for bulk testing

---

## 🙏 Acknowledgment

Special thanks to [Biswadeb Mukherjee](https://github.com/official-biswadeb941) for technical guidance and strategic input throughout this lab simulation. His expertise in offensive security, enumeration tactics, and adversarial tooling played a vital role in this project’s successful execution.

---

## 🗂 Project Snapshot

Field	Description

Status	✅ Completed
Version	1.0
Completion Date	21 July 2025
Domain	Cybersecurity – Authentication & Hygiene
Primary Tools	Python, Regex, CLI
Objective Achieved	Accurately assessed password strength
Next Phase	GUI and entropy-based analysis

---

## 📎 References & Resources

📘 OWASP Password Guidelines
🔗 Python re Module Docs
📓 HaveIBeenPwned Passwords

---

## 📁 Directory Structure

password-strength-analyzer/
├── password_analyzer.py
├── README.md
├── sample_outputs/
│   └── result_demo.txt


## 👤 Author

*DEBASMITA BHAKTA*
> 💡 "Cybersecurity isn't just a skill—it's a mindset."

🔗 Let's Connect

💻 GitHub: https://github.com/debasmita-bhakta, 
   Linkdin : www.linkedin.com/in/debasmita-bhakta-4753a7376

📧 Email: debasmita04bhakta@gmail.com

🧠 Interests: Cybersecurity, Ethical Hacking, Python Automation, Digital Forensics

---
