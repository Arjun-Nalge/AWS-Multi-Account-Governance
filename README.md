# Multi-Account AWS Governance using AWS Organizations & SCPs

## 📌 Project Overview

This project implements a centralized governance model across multiple AWS accounts using AWS Organizations and Service Control Policies (SCPs).

In large organizations, different teams (Development, Testing, Production) operate separate AWS accounts. Without governance, this leads to:

* Uncontrolled resource usage
* Security risks
* High operational costs

This project enforces security, compliance, and cost-control policies across all accounts.

---

## 🎯 Objectives

* Create a multi-account AWS structure
* Organize accounts using Organizational Units (OUs)
* Apply Service Control Policies (SCPs)
* Enforce governance rules
* Validate policy restrictions

---

## 🏗️ Architecture

```
Root
├── Dev OU
│   └── Dev Account
├── Test OU
│   └── Test Account
└── Prod OU
    └── Prod Account
```

---

## ⚙️ Technologies Used

* AWS Organizations
* Service Control Policies (SCPs)
* AWS IAM
* AWS CloudTrail

---

## 🚀 Execution Steps

### 1. Create AWS Organization

* Login to Management Account
* Open AWS Organizations
* Create organization with **All Features Enabled**

---

### 2. Create Organizational Units

Create:

* Dev OU
* Test OU
* Prod OU

---

### 3. Create AWS Accounts

Create accounts using unique email aliases:

* [yourname+dev@gmail.com](mailto:yourname+dev@gmail.com)
* [yourname+test@gmail.com](mailto:yourname+test@gmail.com)
* [yourname+prod@gmail.com](mailto:yourname+prod@gmail.com)

---

### 4. Move Accounts into OUs

* Navigate to "Organize Accounts"
* Move each account into respective OU

---

### 5. Configure Service Control Policies

Create and attach SCPs:

* Dev OU → EC2 restriction policy
* Root → CloudTrail protection
* All OUs → Region restriction

---

### 6. Validation

Perform the following tests:

* Launch restricted EC2 instance → Denied
* Stop CloudTrail → Denied
* Use unapproved region → Denied

---

## 🔐 Governance Policies

### 1. EC2 Cost Control

Restricts high-cost instance types in Dev environment.

### 2. CloudTrail Protection

Prevents disabling or deleting logs.

### 3. Region Restriction

Limits usage to approved AWS region.

---

## 🔍 Policy Enforcement Flow

1. User attempts action
2. IAM allows request
3. SCP evaluates request
4. SCP denies if restricted
5. AWS returns Access Denied
6. Event logged in CloudTrail

---

## ⚠️ Risk Mitigation

* Prevents cost overruns
* Ensures continuous logging
* Restricts unauthorized deployments
* Improves security posture

---

## ✅ Benefits

* Centralized governance
* Environment isolation
* Cost optimization
* Compliance enforcement

---

## 📸 Deliverables

* OU structure screenshot
![image alt](https://github.com/Arjun-Nalge/AWS-Multi-Account-Governance/blob/3ca35e9aefcf1e6dc00caf66cdc72e75c570c742/Screenshot%202026-04-25%20225926.png)
* Access denied screenshots
* README documentation

---

## 🧠 Conclusion

This project demonstrates how to enforce governance across multiple AWS accounts using AWS Organizations and SCPs. It ensures security, compliance, and cost control in a scalable cloud environment.
