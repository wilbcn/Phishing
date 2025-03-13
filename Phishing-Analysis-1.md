# 📧 Investigating Phishing Emails: 1

## 📖 Overview
This document provides an overview of the steps taken to investigate a potential phishing email. In this scenario, I have received a real suspicious email, which inspired this project. I created this project to gain increased hands on experience and understanding of using a wide variety of tools for conducting phishing analysis, developing a better understanding of artifact collection, and phishing email diagnosis. Furthermore, to practice writing reports that a real security analyst might write up when investigating suspicious emails.

💡 This project was inspired by my learning in the** [**Blue Team Level 1**](https://www.securityblue.team/blue-team-level-1) course, where I gained a solid introduction into email analysis and artifact collection.

You can find the setup of the secure VM in AWS here -> [EC2 VM](https://github.com/wilbcn/DigitalForensics/blob/main/AWS-SecureVM/README.md)

## 🎯 Goals
- Successfully analyse the suspicious email in a secure environment
- Collect all relevant artifacts and organise them
- Use the collected artifact to carry out the investigation
- Leverage analysis tools for practice
- Document findings and create a final report

---

## Tools used
- Email header analyzer: https://mxtoolbox.com/EmailHeaders.aspx
-
-



## 1. Email overview.
I moved the suspicious email onto my EC2 VM, and opened it using Mozilla Thunderbird. For security/privacy reasons, my email address has been hidden. 

![image](https://github.com/user-attachments/assets/cfccbacc-fb3f-4f98-b81f-ede4dfbe4580)


An initial analysis provides us with several red flags which indicate a potential phishing email.

- Lack of personalised greeting. A legitimate email would address me formally.
- The apparent sender **mendesmend8pif@virgilio.it**. This is highly suspicious sender address.
- The overall body content is not that of a professional service, such as an estate agent advertising an apartment.
- No official company signature.
- The email itself is unsolicited.
- The email asks for me to engage with it in order to find out more information. 

## 2. Collecting Artifacts.
To gather the email artifacts to investigate further into this email, I used the email header analyzer tool from mxtoolbox. I opened the .eml in notepad++, and copied the header into the tool.

✅ DMARC Compliant – The email passed DMARC authentication, meaning the sender’s domain has a DMARC policy in place.
✅ SPF Alignment & SPF Authenticated – The email originated from an authorized mail server, as specified in the domain’s SPF records.
✅ DKIM Alignment – The DKIM signature matches the expected sending domain, which typically confirms the email was not altered in transit.
❌ DKIM Authentication failed suggesting that:

- The DKIM signature may have been forged.
- The signature didn’t match the cryptographic key in DNS.
- The email could have been modified after signing, indicating a possible spoofing attempt.

![image](https://github.com/user-attachments/assets/9332d6af-42f8-44b3-bf02-dbd1f9a60dce)

The tool also provides us with a wide variety of valuable artifacts, under the headers section. 

| **Header Field**       | **Value** |
|------------------------|---------------------------------------------------|
| **Delivered-To**       | *(Hidden Address)* |
| **Return-Path**        | `<mendesmend8pif@virgilio.it>` |
| **Date**              | Thu, 20 Feb 2025 21:39:09 +0100 (CET) |
| **From**              | `mendesmend8pif@virgilio.it` |
| **Subject**           | Lloguer en Carrer Gran de Gràcia - Metro Lesseps Barcelona BBZM18 |
| **Received-SPF**      | `pass (google.com: domain of mendesmend8pif@virgilio.it designates 213.209.9.36 as permitted sender)` |
| **Client IP**         | `213.209.9.36` |
| **X-Originating-IP**  | `2.39.110.75` |

## 3. Investigations.

## **1. Template **

## **1. Template **

## **1. Template **

## **1. Template **

## **1. Template **


