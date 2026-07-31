# 🔐 Least Privilege & Data Leak Analysis

## 📌 Project Overview

This project analyzes a data leakage incident caused by improper access permissions and the lack of effective implementation of the **Principle of Least Privilege**.

The analysis is based on a cybersecurity scenario involving an educational technology company that handles sensitive information from educational institutions, instructors, parents, and students.

The objective of this project is to:

* Identify the security issues that contributed to the data leak.
* Analyze the effectiveness of existing access controls.
* Apply the **Principle of Least Privilege**.
* Reference **NIST SP 800-53 AC-6 (Least Privilege)**.
* Recommend security control enhancements.
* Explain how the recommendations can reduce the likelihood of future data leaks.

---

## 🏢 Scenario

An educational technology company developed an application that automatically grades assignments for teachers.

The application handles different types of information collected from:

* Educational institutions
* Instructors
* Parents
* Students

The company experienced a **data leak involving confidential internal business plans**.

An investigation discovered that an employee accidentally shared confidential documents with an external business partner.

### Incident

A Customer Success Representative was given access to a folder containing internal documents related to a new product offering.

The folder contained:

* Customer analytics
* Marketing materials
* Internal business information

The representative only intended to share the marketing materials with a business partner during a sales call.

However, instead of sharing the specific marketing material, the representative shared a link to the **entire folder**.

The business partner gained access to the internal documents and later posted the link on social media, resulting in a data leak.

---

## 🔎 Security Issue

The primary security issue was the failure to properly implement the **Principle of Least Privilege**.

The representative had access to more information than was necessary for their task.

The incident can be summarized as:

```text
Excessive Access
       ↓
Unnecessary Folder Permissions
       ↓
Accidental Sharing of Entire Folder
       ↓
External Access to Confidential Data
       ↓
Data Leak
```

Another contributing factor was that the manager **forgot to remove the representative's access** to the folder after it was no longer required.

---

## 🛡️ Security Control

### Principle of Least Privilege

The Principle of Least Privilege requires users, processes, and systems to receive only the minimum level of access necessary to perform their assigned tasks.

In this scenario, the representative needed access to the **marketing materials**, but did not need access to the entire folder containing customer analytics and other internal documents.

Applying least privilege would reduce the potential impact of accidental sharing.

---

## 📚 NIST SP 800-53 AC-6

**NIST SP 800-53 AC-6 — Least Privilege** focuses on restricting access to information and system resources to the minimum necessary for users or processes to perform their assigned tasks.

The control supports organizations in reducing unnecessary privileges and limiting the potential impact of unauthorized or accidental access.

Relevant improvements include:

* Reviewing user privileges regularly.
* Limiting access based on business requirements.
* Removing unnecessary privileges.
* Using time-limited access where appropriate.

---

## 💡 Recommended Improvements

### 1. Regularly Audit User Privileges

Organizations should periodically review user permissions to identify and remove unnecessary access.

Regular privilege reviews could have identified that the Customer Success Representative still had access to the entire internal folder.

**Expected benefit:**

* Reduces excessive permissions.
* Supports least privilege.
* Detects outdated access.
* Reduces the attack and exposure surface.

---

### 2. Automatically Revoke Temporary Access

Access to sensitive information should be automatically revoked after a predefined period when the access is temporary.

For example, access granted to an employee for a specific project or business meeting could automatically expire after the required period.

**Expected benefit:**

* Prevents forgotten permissions.
* Reduces the duration of exposure.
* Limits accidental data disclosure.
* Reduces the risk associated with stale permissions.

---

## 🎯 Security Impact

Implementing these controls would reduce the likelihood and potential impact of similar incidents.

Instead of providing access to an entire folder, users should receive access only to the specific information required for their responsibilities.

For example:

```text
Customer Success Representative
            │
            ├── Marketing Materials ✅
            │
            ├── Customer Analytics ❌
            │
            └── Internal Business Plans ❌
```

This approach limits what a user can access and what they can accidentally expose to external parties.

---

## 🔐 Security Principles Demonstrated

This project demonstrates practical understanding of:

* Least Privilege
* Access Control
* Authorization
* Data Protection
* Information Privacy
* User Privilege Management
* Data Leakage Prevention
* Security Control Assessment
* Risk Reduction
* NIST SP 800-53
* NIST AC-6

---

## 🧰 Framework / References

* **NIST Special Publication 800-53**
* **AC-6 — Least Privilege**
* Access Control principles
* Information privacy and data protection concepts

---

## 📂 Project Structure

```text
least-privilege-data-leak-analysis/
│
├── README.md
├── scenario.md

```

---

## 🎓 Learning Outcome

This project demonstrates how access-control weaknesses can contribute to real-world data leakage.

The main lesson is that granting users access to more information than they need increases the risk of accidental or unauthorized disclosure.

Effective implementation of **Least Privilege**, combined with regular privilege reviews and time-limited access, can significantly reduce this risk.

---

## 👨‍💻 Author

**Mahmoud Ahmed Fathy**

Computer Science Student | Cybersecurity Enthusiast


