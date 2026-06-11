## CodeAlpha Internship - Phishing Awareness Training & Quiz

This repository contains **TASK 2: Phishing Awareness Training** developed during the **CodeAlpha Cyber Security Internship (Module 1)**. 

Since human error is responsible for over 90% of cyber breaches, this project provides a comprehensive, structured guide to recognizing phishing indicators, understanding social engineering tactics, and an interactive quiz to test user resilience.

---

## 📘 Part 1: Educational Training Module

### 1. What is Phishing?
Phishing is a deceptive technique used by cybercriminals to trick individuals into disclosing sensitive information—such as login credentials, credit card details, or corporate data—by masquerading as a trustworthy entity via digital communication.

### 2. Anatomy of a Phishing Attack (The Red Flags)
To effectively spot a phishing attempt, look for these critical indicators:

* **⚠️ Spoofed Sender Addresses:** The display name says "Your Bank", but the actual domain in the email header is compromised or simulated (e.g., `security@paypa1-update.com` instead of `security@paypal.com`).
* **🚨 Artificial Urgency:** Messages that induce panic, threatening immediate account suspension, legal action, or financial loss if you do not act within a tight deadline (e.g., *"Act within 24 hours"*).
* **🔗 Hyperlink Mismatch (The Hover Trick):** The anchor text says `www.trustedbank.com`, but when you hover your mouse cursor over the link, the actual status bar reveals a malicious destination (e.g., `http://attacker-controlled-site.ru/login`).
* **📦 Suspicious Attachments:** Unsolicited files, especially those with dangerous or double extensions disguised as documents (e.g., `Invoice_2026.pdf.exe`, `Report.zip`, or macro-enabled `.docm`).
* **👤 Generic Greetings:** Bulk phishing often utilizes generic salutations like *"Dear Customer"* or *"Valued Member"* rather than personalizing the email with your actual name.

### 3. Phishing Vectors
1.  **Spear Phishing:** Highly targeted attacks customized with OSINT (Open Source Intelligence) gathered about a specific individual or organization.
2.  **Whaling:** Spear phishing specifically directed at high-profile executives (CEOs, CFOs) to authorize large wire transfers or compromise enterprise-level accounts.
3.  **Smishing (SMS Phishing) & Vishing (Voice Phishing):** Phishing executed through mobile text messages or fraudulent phone calls leveraging social engineering.

---

## 📝 Part 2: Interactive Awareness Quiz

Test your capability to spot social engineering lures below. *(Answer Key with technical explanations is provided at the bottom).*

### 📊 Scenario 1: The Urgent Security Update
You receive an email from **"Microsoft Security Team"** stating that your corporate account has been compromised from an unauthorized location. It requests you to immediately verify your password by clicking a provided button. 
* **Sender Address:** `no-reply@microsoft-security-alert-center.com`
* **Lure:** *"Click here to verify your account immediately or your access will be permanently revoked."*

**What is your response?**
* **A)** Click the button, log in, and verify your credentials to ensure your account stays active.
* **B)** Forward the email to your friends to see if they got it too.
* **C)** Do not click. Inspect the sender domain (`microsoft-security-alert-center.com`), identify it as a fake domain, and report the email to your organization's SOC/IT Security department.

---

### 📊 Scenario 2: The LinkedIn Job Offer
An external recruiter messages you on LinkedIn offering an amazing remote internship opportunity. They ask you to download and review an archive file containing the job requirements named `Internship_Requirements_2026.zip`. When extracted, it contains a file named `Details.pdf.exe`.

**What is your response?**
* **A)** Double-click the file because it has a PDF icon and you need to see the requirements.
* **B)** Recognize that a `.exe` extension signifies an executable application, not a document. Do not execute it, block the user, and report the profile for spreading malware.
* **C)** Run the file, and if nothing opens, assume it was a corrupted file and ask the recruiter to send it again.

---

### 📊 Scenario 3: The Delivery Failure
You receive an SMS (Smishing) from an unknown number claiming to be **"Post Office Updates"** stating that a package cannot be delivered due to an incorrect house number. It asks you to update your address and pay a 1.50 AZN re-delivery fee via `http://az-post-tracking.net/fee`.

**What is your response?**
* **A)** Click the link and enter your credit card info since the fee is very small.
* **B)** Ignore the text message. If expecting a package, navigate to the official tracking website of Azerpost manually using a known safe URL.
* **C)** Reply to the SMS with your full home address and ID details.

---

## 🔑 Part 3: Technical Answer Key & Explanations

### Scenario 1 Correct Answer: **C**
* **Technical Breakdown:** Attackers register lookalike domains (typosquatting) to build trust. Microsoft will never send security alerts from a domain like `microsoft-security-alert-center.com`. Reporting the email allows the security team to block the sender gateway-wide.

### Scenario 2 Correct Answer: **B**
* **Technical Breakdown:** This is a classic malware delivery mechanism. Attackers use double extensions (`.pdf.exe`) relying on the default Windows setting that hides known file extensions, tricks users into running a malicious payload (like a Ransomware or Infostealer).

### Scenario 3 Correct Answer: **B**
* **Technical Breakdown:** Smishing attacks exploit daily conveniences. Official postal services do not use random web domains like `.net` for tracking or payment collection. Clicking the link leads to a credential/credit card harvesting landing page.

---

## 🛠️ Mitigations and Incident Response Workflow
If you suspect or interact with a phishing lure:
1.  **Stop:** Do not enter credentials, authorize MFA prompts, or download payloads.
2.  **Isolate:** If an attachment was executed, disconnect the host machine from the local network (unplug Ethernet / turn off Wi-Fi) to prevent lateral movement.
3.  **Report:** Use the integrated phish reporting button in your mail client or contact the security incident response team immediately. CodeAlpha_Phishing_Awareness_Training
