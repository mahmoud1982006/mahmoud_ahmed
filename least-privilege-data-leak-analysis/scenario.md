# Data Leak Incident Scenario

## Background

An educational technology company developed an application that automatically grades assignments for teachers.

The application processes different types of information collected from educational institutions, instructors, parents, and students.

The company follows the **NIST Cybersecurity Framework (CSF)** and uses security controls to protect organizational information.

---

## Incident

The security team was alerted to a data leak involving confidential internal business plans.

During the investigation, the team discovered that a Customer Success Representative had been given access to a folder containing internal documents related to a new product offering.

The folder included:

* Customer analytics
* Marketing materials
* Internal business information

The representative later needed to share the marketing materials with a business partner during a sales call.

Instead of sharing only the required marketing materials, the representative accidentally shared a link to the **entire folder**.

The business partner received access to the internal documents and subsequently posted the link on social media.

---

## Root Cause

The incident was primarily caused by insufficient implementation of the **Principle of Least Privilege**.

The representative had access to information that was not necessary for their task.

Additionally, the manager had forgotten to remove the representative's access to the folder.

This created an opportunity for an accidental disclosure of sensitive information.

---

## Security Analysis

The incident demonstrates how excessive permissions can increase the risk of data leakage.

The required access should have been limited to the specific marketing materials needed for the business interaction.

Instead, the representative had access to the entire folder.

### Access that was required

```text
Marketing Materials
        ↓
       YES
```

### Access that was unnecessary

```text
Customer Analytics
        ↓
        NO

Internal Business Plans
        ↓
        NO
```

---

## Recommended Controls

### Control 1 — Regular Privilege Reviews

User privileges should be reviewed regularly to identify excessive or outdated permissions.

### Control 2 — Time-Limited Access

Temporary access to sensitive resources should automatically expire after the required period.

---

## Expected Result

Applying these controls would reduce unnecessary access and limit the amount of sensitive information that could be exposed during accidental sharing.

The organization would move from:

```text
Broad Access
     ↓
Higher Exposure
     ↓
Higher Risk
```

to:

```text
Minimum Required Access
     ↓
Reduced Exposure
     ↓
Lower Risk
```

---

## Security Principle

> **Least Privilege:** Users and processes should receive only the access necessary to perform their assigned tasks.

This principle is particularly important when handling sensitive business information, customer data, and other confidential resources.
