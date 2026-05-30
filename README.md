# aws-iam-labs# AWS IAM Lab 1: Creating an EC2 Read-Only User with a Custom IAM Policy

## Project Overview

This lab demonstrates how to implement the Principle of Least Privilege in AWS Identity and Access Management (IAM). A custom IAM policy was created to allow a user to view EC2 resources while preventing them from launching or terminating EC2 instances.

---

## Objective

The objective of this lab was to:

* Create an IAM user named `ec2-auditor`
* Create a custom IAM policy
* Allow EC2 read-only access using `ec2:Describe*`
* Prevent instance creation using `ec2:RunInstances`
* Prevent instance termination using `ec2:TerminateInstances`
* Validate the permissions by logging in as the IAM user

---

## Architecture

AWS Account
│
├── IAM User (ec2-auditor)
│
└── Custom IAM Policy
├── Allow: ec2:Describe*
├── Deny: ec2:RunInstances
└── Deny: ec2:TerminateInstances

---

## Services Used

* AWS IAM
* Amazon EC2

---

## Implementation Steps

### Step 1: Create IAM User

1. Open AWS Console
2. Navigate to IAM
3. Select Users
4. Click Create User
5. User Name: ec2-auditor
6. Enable AWS Management Console access
7. Create password

Result:
IAM user successfully created.

---

### Step 2: Create Custom Policy

Navigate to:

IAM → Policies → Create Policy

Policy JSON:

{
"Version": "2012-10-17",
"Statement": [
{
"Sid": "AllowEC2DescribeActions",
"Effect": "Allow",
"Action": [
"ec2:Describe*"
],
"Resource": "*"
},
{
"Sid": "DenyInstanceCreateAndDelete",
"Effect": "Deny",
"Action": [
"ec2:RunInstances",
"ec2:TerminateInstances"
],
"Resource": "*"
}
]
}

Policy Name:
EC2ReadOnlyCustomPolicy

Result:
Policy created successfully.

---

### Step 3: Attach Policy to User

1. Open IAM Users
2. Select ec2-auditor
3. Add Permissions
4. Attach Existing Policy
5. Select EC2ReadOnlyCustomPolicy

Result:
Policy attached successfully.

---

### Step 4: Test User Access

Login using the IAM user credentials.

Testing Performed:

Test 1:
Action: View EC2 Dashboard
Expected Result: Allowed
Actual Result: Allowed

Test 2:
Action: View Running Instances
Expected Result: Allowed
Actual Result: Allowed

Test 3:
Action: Launch New EC2 Instance
Expected Result: Denied
Actual Result: Access Denied

Test 4:
Action: Terminate Existing Instance
Expected Result: Denied
Actual Result: Access Denied

---

## Validation Results

| Test Case          | Expected | Actual | Status |
| ------------------ | -------- | ------ | ------ |
| View EC2 Dashboard | Allow    | Allow  | Pass   |
| View Instances     | Allow    | Allow  | Pass   |
| Launch Instance    | Deny     | Deny   | Pass   |
| Terminate Instance | Deny     | Deny   | Pass   |

---

## Screenshots

Screenshot 1:
IAM User Creation

Screenshot 2:
Custom Policy JSON

Screenshot 3:
Policy Attached to User

Screenshot 4:
Successful EC2 Dashboard Access

Screenshot 5:
Access Denied While Launching Instance

Screenshot 6:
Access Denied While Terminating Instance

---

## Key IAM Concepts Learned

### Principle of Least Privilege

Users should receive only the permissions required to perform their job responsibilities.

### Explicit Deny

An explicit Deny always overrides an Allow statement in IAM policy evaluation.

### Resource Visibility

The user can view EC2 resources through Describe actions without being able to modify them.

---

## Challenges Faced

* Understanding IAM policy syntax
* Identifying required EC2 actions
* Testing permissions using a separate IAM user

---

## Best Practices Implemented

* Used custom policy instead of AdministratorAccess
* Followed least privilege principle
* Avoided sharing root account credentials
* Tested permissions before production use

---

## Conclusion

This lab successfully demonstrated how to create a custom IAM policy that provides EC2 read-only access while preventing instance creation and termination. The implementation improved understanding of IAM users, custom policies, explicit deny statements, and AWS security best practices.
