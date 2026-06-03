# AWS IAM Lab 6: Password Policy and Security Audit

## Overview

This lab demonstrates how to strengthen AWS account security by configuring a strong IAM password policy and performing a security audit using the IAM Credential Report. The exercise helps identify security risks such as weak passwords, inactive users, and missing Multi-Factor Authentication (MFA).

## Objective

The goal of this lab was to:

* Configure a secure account password policy.
* Enforce password complexity requirements.
* Generate and analyze an IAM Credential Report.
* Identify security issues related to user credentials.
* Review MFA adoption and account usage.

---

## Password Policy Configuration

The following password policy was configured for the AWS account:

| Setting                    | Value         |
| -------------------------- | ------------- |
| Minimum Password Length    | 12 Characters |
| Require Uppercase Letters  | Enabled       |
| Require Lowercase Letters  | Enabled       |
| Require Numbers            | Enabled       |
| Require Special Characters | Enabled       |

### Security Purpose

This configuration helps protect AWS accounts from:

* Weak password attacks
* Brute-force attempts
* Credential stuffing attacks
* Unauthorized account access

---

## Implementation Steps

### Step 1: Configure IAM Password Policy

1. Logged in to the AWS Management Console.
2. Opened the IAM service.
3. Navigated to **Account Settings**.
4. Selected **Change Password Policy**.
5. Configured the following settings:

   * Minimum password length: 12 characters
   * Require uppercase letters
   * Require lowercase letters
   * Require numbers
   * Require special characters
6. Saved the policy.

**Result:** Strong password policy successfully enforced.

---

### Step 2: Generate IAM Credential Report

1. Opened the IAM Console.
2. Selected **Credential Report**.
3. Clicked **Generate Report**.
4. Downloaded the generated CSV report.

**Result:** IAM Credential Report successfully generated.

---

## Credential Report Review

The credential report was analyzed to identify potential security concerns.

### Password Age Review

**Objective:**

Identify users with old passwords that may require rotation.

**Findings:**

* Reviewed password age information for all IAM users.
* Verified compliance with password management policies.

---

### Unused User Review

**Objective:**

Identify inactive IAM users.

**Findings:**

* Checked user login activity.
* Identified users that had not recently accessed the AWS account.
* Evaluated whether inactive accounts should be disabled or removed.

---

### MFA Status Review

**Objective:**

Verify Multi-Factor Authentication adoption.

**Findings:**

* Reviewed MFA status for all IAM users.
* Identified users without MFA enabled.
* Recommended MFA activation for improved security.

---

## Verification and Testing

### Test Case 1: Password Policy Enforcement

**Expected Result:**

Passwords that do not meet complexity requirements should be rejected.

**Actual Result:**

Passwords failing complexity requirements were denied.

**Status:** Passed ✅

---

### Test Case 2: Credential Report Generation

**Expected Result:**

Credential report should be generated and downloadable.

**Actual Result:**

Credential report successfully generated and downloaded.

**Status:** Passed ✅

---

### Test Case 3: Security Audit Review

**Expected Result:**

Credential report should provide visibility into:

* Password age
* User activity
* MFA status

**Actual Result:**

Successfully reviewed all required security indicators.

**Status:** Passed ✅

---

## Security Best Practices Demonstrated

* Strong Password Policy Enforcement
* IAM Security Auditing
* Credential Management
* Multi-Factor Authentication (MFA)
* Compliance Monitoring
* Principle of Least Privilege Awareness
* Continuous Security Review

---

## Benefits of Credential Reports

1. Improved visibility into IAM user security posture.
2. Easier compliance and audit preparation.
3. Identification of inactive users.
4. Detection of weak security configurations.
5. Support for proactive security management.

---

## Skills Practiced

* AWS IAM
* Password Policy Management
* IAM Credential Reports
* Security Auditing
* MFA Verification
* Compliance Monitoring
* Cloud Security Fundamentals

---

## Outcome

Successfully enhanced AWS account security by enforcing a strong password policy and conducting a credential audit using IAM Credential Reports. The audit process helped identify password management practices, inactive users, and MFA adoption status.

### Final Validation

✅ Strong password policy configured successfully.

✅ IAM Credential Report generated and analyzed.

✅ Password age reviewed.

✅ Unused users identified.

✅ MFA status verified.

✅ IAM security audit completed successfully.
