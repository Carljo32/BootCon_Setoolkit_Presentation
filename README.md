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

- Launched SET with `sudo setoolkit`
- Configured Apache and Gmail settings in `set.config`
- Enabled email delivery and web hosting capabilities

### ✉️ Mass Mailer Setup

- Chose: `Mass Mailer Attack > Single Email Address`
- Composed phishing email in HTML:
  ```
  Sender: GitHub IT Support  
  We have detected a suspicious login attempt on your GitHub account.  
  Please visit [malicious link] to prevent further access.
  ```

- The link redirected users to a cloned GitHub login page hosted locally.

### 🌐 Website Cloning & Credential Harvester

- Configured under: `Website Attack Vectors > Credential Harvester > Site Cloner`
- Input GitHub URL and VM IP
- Apache served the fake login page
- Page designed to capture entered credentials

### ▶️ Demo Execution

- Phishing email sent from Gmail to Yahoo Mail
- Apache hosted the cloned login site
- Entire flow executed in minutes

### ⚠️ Limitations

- Gmail sender spoofing not possible using my own personal accounts.
- Google security features affected email delivery
- Demo focused on setup and delivery; no credentials were harvested

---

## 6. Demonstration & Results

- Successfully created and sent a phishing email
- Cloned GitHub login page hosted locally
- Demonstrated how attackers can deceive users through social engineering
- Screenshots and logs documented the full process (see [Appendices](#10-appendices))

---

## 7. Discussion & Analysis

### 💥 Impact

This project illustrated how even novice attackers can deploy phishing campaigns using SET. It also reinforced how critical **end-user education** is to cybersecurity.

### 🌍 Real-World Examples

- Summer 2024: Fake QR codes on parking meters in Redondo and Newport Beach were used to steal payment info.
- Countless modern attacks begin with phishing emails crafted to deceive even trained users.

### 🤔 Challenges

- Inability to spoof email sender due to Gmail restrictions
- No credential data captured for ethical and scope reasons

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
- Screenshot: SET Mass Mailer interface  
- Sample HTML phishing message:
  ```html
  <p>There was a suspicious login detected on your GitHub account.  
  Please visit <a href="http://172.00.000.000" target="_blank" rel="noopener">https://github.com/login</a> immediately to prevent further access.  
  Please act urgently to secure your account.</p>
  ```

- Credential Harvester configuration screenshot  
- Cloned GitHub login page preview  
- SET command-line setup logs  
- [Google Doc Walkthrough (Demo Presentation)](LINK_PLACEHOLDER)  
- [Final Slide Deck](LINK_PLACEHOLDER)

---

## 11. References

- [Social-Engineer Toolkit Documentation – TrustedSec](https://github.com/trustedsec/social-engineer-toolkit)  
- [Kali Linux Documentation](https://www.kali.org/docs/)  
- [OWASP Cheat Sheets](https://cheatsheetseries.owasp.org/)  
- [MITRE ATT&CK: Phishing](https://attack.mitre.org/techniques/T1566/)  
- UCI Cybersecurity Bootcamp Course Materials
