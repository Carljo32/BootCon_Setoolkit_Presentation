# PHISHING SIMULATION USING SET (Social-Engineer Toolkit)
##### UCI's Cybersecurity Final Boot Camp Project #4

**Author:** Carl Johnson  
**Date:** December 2024  
**Affiliation:** UCI Cybersecurity Bootcamp  
**Project 4:** Bootcon Final Presentation

---

## 📑 Table of Contents

1. [Executive Summary](#1-executive-summary)  
2. [Introduction](#2-introduction)  
3. [Background / Research Context](#3-background--research-context)  
4. [Tools, Technologies & Environment Used](#4-tools-technologies--environment-used)  
5. [Methodology](#5-methodology)  
6. [Demonstration & Results](#6-demonstration--results)  
7. [Discussion & Analysis](#7-discussion--analysis)  
8. [Mitigation Strategies](#8-mitigation-strategies)  
9. [Conclusion](#9-conclusion)  
10. [Appendices](#10-appendices)  
11. [References](#11-references)

---

## 1. Executive Summary

The goal of this final bootcamp project was to select, simulate, and present a cybersecurity concept in a mock “conference” setting. I chose to focus on social engineering, a critical attack vector that targets human behavior rather than technical vulnerabilities.

To demonstrate this, I used the **Social-Engineer Toolkit (SET)** to simulate a phishing attack. The simulation showed how easily attackers can craft deceptive emails that redirect victims to cloned login pages designed to steal credentials.

This hands-on experience emphasized how vulnerable users can be when trust is exploited and reinforced the importance of layered security—combining technical controls with proactive user education.

### 🔑 Key Takeaways

- Even the strongest security infrastructure can be compromised by social engineering.
- Tools like SET enable attackers to quickly execute phishing attacks.
- Ongoing training and layered defense are essential for prevention.

### 🎯 Expected Outcomes

- Raise awareness of phishing techniques among non-technical users.
- Demonstrate the value of layered defenses (technical and human).
- Gain hands-on experience using SET.
- Document insights to support future awareness training or red team exercises.

---

## 2. Introduction

### 📌 Problem Statement

Despite advanced technical defenses, **humans remain the weakest link** in cybersecurity. Phishing attacks continue to succeed because they exploit user behavior rather than system flaws.

### 🎯 Objective

To demonstrate how phishing emails can be crafted and distributed using SET, simulating a real-world social engineering attack.

### 🌐 Scope & Relevance

Social engineering plays a role in an estimated **98% of cyberattacks**. Understanding and preventing these attacks is vital across all industries.

### 👥 Target Audience

- Cybersecurity students and educators  
- Professionals in training  
- Non-technical stakeholders looking to understand social engineering risks

---

## 3. Background / Research Context

The **Social-Engineer Toolkit (SET)** is an open-source penetration testing framework that simulates a range of social engineering attacks—phishing, credential harvesting, and more.

Tools like **BeEF** and **Metasploit** also contain modules that rely on social engineering, reinforcing the relevance of this topic.

A personal experience that inspired this project occurred when I helped an elderly client avoid falling for an “IRS gift card scam.” This event sparked my interest in how attackers exploit human psychology and how those tactics can be mitigated.

### 🔐 Security Principles Addressed

- **Network Security:** Credential harvesting bypasses authentication.
- **Cryptography:** Strong encryption is irrelevant if credentials are stolen.
- **Defense in Depth:** Security requires technical, procedural, and human controls.

---

## 4. Tools, Technologies & Environment Used

| Category         | Details |
|------------------|---------|
| OS               | Kali Linux (VMware Workstation) |
| Main Tool        | Social-Engineer Toolkit (SET) |
| Web Hosting      | Apache Server (enabled via SET config) |
| Email Services   | Gmail (sender), Yahoo Mail (receiver) |
| Targeted Site    | `https://github.com/login` |
| Environment      | Ethical use on personal devices in a private network |

---

## 5. Methodology

### 🔧 Planning & Configuration
  Using sudo privileges, I launched the Social-Engineer Toolkit (SET) via sudo setoolkit and configured both my Gmail account settings and the Apache server parameters         within the set.config files to support email delivery and web hosting.

- Launched SET with `sudo setoolkit`
- Configured Apache and Gmail settings in `set.config`
- Enabled email delivery and web hosting capabilities


### ✉️ Mass Mailer Setup
  From SET’s main menu, I selected the Mass Mailer Attack and opted for the Single Email Address option, appropriate for my isolated testing environment (though a full         mailing list can be used in real-world scenarios). I composed a phishing email using HTML to embed a hyperlink with the message:

- Chose: `Mass Mailer Attack > Single Email Address`
- Composed phishing email in HTML:
  ```
  Sender: GitHub IT Support  
  There was a suspicious login detected on your GitHub account.  
  Please visit [malicious link] to prevent further access.
  Please act urgently to secure your account.
  ```
   ```html
  <p>There was a suspicious login detected on your GitHub account.  
  Please visit <a href="http://172.00.000.000" target="_blank" rel="noopener">https://github.com/login</a> immediately to prevent further access.  
  Please act urgently to secure your account.</p>
  ```

- The link redirected users to a cloned GitHub login page hosted locally.

### 🌐 Website Cloning & Credential Harvester
  To enable credential harvesting, I configured SET’s Credential Harvester module under Website Attack Vectors > Site Cloner. This required inputting the legitimate GitHub     URL and my VM’s IP address, as the Apache server would serve the cloned login page. Once configured, the attack vector was ready to capture input data from unsuspecting      users.

- Configured under: `Website Attack Vectors > Credential Harvester > Site Cloner`
- Input GitHub URL and VM IP
- Apache served the fake login page
- Page designed to capture entered credentials

### ▶️ Demo Execution
  The simulation demonstrated how attackers can easily replicate legitimate login pages and send phishing emails to harvest user credentials. During the live demo, I           configured and sent the phishing email from my Gmail account to my Yahoo email, completing the process within minutes.

- Phishing email sent from Gmail to Yahoo Mail
- Apache hosted the cloned login site
- Entire flow executed in minutes

### ⚠️ Limitations
  A few limitations were present during the project. First, using personal email accounts restricted sender spoofing, so the phishing message did not convincingly appear to    come from a trusted IT source (GitHub IT Support). Additionally, the demo stopped short of capturing actual credentials, as the focus was on demonstrating the setup and      attack flow, not full exploitation.

- Gmail sender spoofing not possible using my own personal accounts.
- Google security features affected email delivery
- Demo focused on setup and delivery; no credentials were harvested

---

## 6. Demonstration & Results
  SET enabled the rapid creation and distribution of a phishing email. A cloned site convincingly mimicked GitHub’s login page. Though credentials were not harvested, the      demonstration showed how attackers can trick users into divulging login information.
  Screenshots and command logs (see Appendix) documents steps from configuration through email delivery and site cloning.

- Successfully created and sent a phishing email
- Cloned GitHub login page hosted locally
- Demonstrated how attackers can deceive users through social engineering
- Screenshots and logs documented the full process (see [Appendices](#10-appendices))

---

## 7. Discussion & Analysis

### 💥 Impact

  Social engineering attacks can bypass even the most advanced defenses by exploiting trust. The ease of deploying such attacks with SET underscores how critical user          awareness is to an organization’s security.

### 🌍 Real-World Examples

  In Summer 2024, attackers placed fake QR codes on parking meters in Redondo Beach and Newport Beach to steal payment information, an example of social engineering aimed at   malicious intent. 
-	Additional examples: [RELATED EVENTS OF PHISHING SCAMS](https://www.bluevoyant.com/knowledge-center/8-devastating-phishing-attack-examples-and-prevention-tips)



### 🤔 Challenges

  Ultimately, spoofing sender identity within my Gmail was not possible and credentials were not captured. Google security automatic settings also played a roll in this.

### 🧠 Lessons Learned

Hands-on simulations provided critical insight into attacker tactics and highlighted how easily malicious content can be created and distributed. This reinforced why **proactive education is vital** in modern cybersecurity.

---

## 8. Mitigation Strategies

- **User Awareness Training:** Help staff recognize phishing indicators  
- **Multi-Factor Authentication (MFA):** Prevent unauthorized access  
- **Zero Trust Security Model:** Verify everything, trust nothing  
- **Anomaly Detection & Analytics:** Spot and react to abnormal activity  
- **Incident Response Plans:** Contain and mitigate attacks quickly  
- **Physical Security:** Lock down access to key systems

---

## 9. Conclusion

This simulation using SET showcased the simplicity and danger of phishing attacks. Social engineering remains one of the most effective methods of breaching security, primarily because it exploits human trust.

Through hands-on testing and ethical simulation, this project strengthened my understanding of how attackers think and operate—and underscored the importance of combining technical tools with behavioral defenses.

Cybersecurity isn’t just about systems—it’s about people.

---

## 10. Appendices

- `set.config` file (modified)  
 ![image](https://github.com/user-attachments/assets/e43f121c-4e2a-4ae0-b3b9-27c929e66c88)


- Screenshot: SET Mass Mailer interface

  ![image](https://github.com/user-attachments/assets/ee986df6-891a-4fd3-bbcc-81a3a67894ad)

  
- Sample HTML phishing message:
  ```html
  <p>There was a suspicious login detected on your GitHub account.  
  Please visit <a href="http://172.00.000.000" target="_blank" rel="noopener">https://github.com/login</a> immediately to prevent further access.  
  Please act urgently to secure your account.</p>
  ```

  <img width="468" alt="image" src="https://github.com/user-attachments/assets/f2e1020b-48da-4958-ad7a-c345816ba93d" />

- Credential Harvester configuration screenshot

  <img width="390" alt="image" src="https://github.com/user-attachments/assets/971f6c8f-cf32-4380-9e65-516716e0dded" />

- Phising Email result

  <img width="468" alt="image" src="https://github.com/user-attachments/assets/fe2bded9-beec-4d48-a6d0-d9d94ea390b5" />
 
- [Google Doc Walkthrough (Demo Presentation)](https://tinyurl.com/t6j2ycku)  
- [Final Presentation Deliverable Slide](https://tinyurl.com/pyhtn83f)

---

## 11. References

- [Social-Engineer Toolkit Documentation – TrustedSec](https://github.com/trustedsec/social-engineer-toolkit)  
- [Kali Linux Documentation](https://www.kali.org/docs/)
- [StationX SET Demo](https://www.stationx.net/social-engineer-toolkit/)
- [OWASP Cheat Sheets](https://cheatsheetseries.owasp.org/)  
- [MITRE ATT&CK: Phishing](https://attack.mitre.org/techniques/T1566/)  
- UCI Cybersecurity Bootcamp Course Materials
