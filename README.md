# AWS IAM Groups-Based Access Control Lab

## Overview

This lab demonstrates how to implement Role-Based Access Control (RBAC) in AWS Identity and Access Management (IAM) using IAM Groups. Instead of assigning permissions directly to individual users, permissions are managed through groups, making access control more scalable and easier to maintain.

## Objective

The goal of this lab was to:

* Create IAM groups with specific permission sets.
* Assign users to groups based on their responsibilities.
* Validate access permissions through user testing.
* Implement a basic RBAC model using AWS IAM.

---

## Architecture

### IAM Groups

| Group Name | Permission Policy   |
| ---------- | ------------------- |
| Developers | AmazonEC2FullAccess |
| Auditors   | ReadOnlyAccess      |

### IAM Users

| User   | Group      |
| ------ | ---------- |
| dev1   | Developers |
| dev2   | Developers |
| audit1 | Auditors   |

---

## Implementation Steps

### Step 1: Create IAM Groups

#### Developers Group

Created an IAM group named **Developers** and attached the following AWS managed policy:

* AmazonEC2FullAccess

This policy grants full administrative access to Amazon EC2 resources.

#### Auditors Group

Created an IAM group named **Auditors** and attached the following AWS managed policy:

* ReadOnlyAccess

This policy provides read-only access across AWS services.

---

### Step 2: Create IAM Users

Created the following IAM users:

* dev1
* dev2
* audit1

Each user was configured with appropriate login credentials for testing purposes.

---

### Step 3: Assign Users to Groups

Added users to their respective groups:

#### Developers Group

* dev1
* dev2

#### Auditors Group

* audit1

By assigning permissions through groups, individual user permission management is minimized.

---

## Verification and Testing

### Test Case 1: Developer Access

**User:** dev1

**Expected Result:**

* Can launch EC2 instances.
* Can stop/start EC2 instances.
* Can manage EC2 resources.

**Actual Result:**

* Successfully launched an EC2 instance.
* Full EC2 management access confirmed.

**Status:** Passed

---

### Test Case 2: Auditor Access

**User:** audit1

**Expected Result:**

* Can view AWS resources.
* Cannot create, modify, or delete resources.

**Actual Result:**

* Successfully viewed AWS resources.
* Access denied when attempting administrative actions.

**Status:** Passed

---

## Security Best Practices Demonstrated

* Principle of Least Privilege
* Group-Based Permission Management
* Role-Based Access Control (RBAC)
* Centralized Access Administration
* Reduced Permission Duplication

---

## Benefits of IAM Groups

1. Simplified permission management.
2. Easier onboarding and offboarding of users.
3. Consistent access control across teams.
4. Reduced risk of permission misconfiguration.
5. Scalable security administration.

---

## Skills Practiced

* AWS IAM
* IAM Groups
* User Management
* AWS Managed Policies
* Access Control
* Role-Based Access Control (RBAC)
* Cloud Security Fundamentals

---

## Outcome

Successfully implemented an IAM Groups-based access control model in AWS. Permissions were managed through groups rather than direct user assignments, demonstrating a scalable and secure approach to identity and access management.

### Final Validation

✅ Developers group members can manage EC2 resources.

✅ Auditors group members have read-only access.

✅ RBAC model successfully implemented using IAM Groups.
