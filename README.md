# IAM Identity Lifecycle Lab

## Objective
Demonstrate joiner, mover, and leaver identity lifecycle using Microsoft Entra ID with authentication, MFA enforcement, and audit logging.

## Environment
- Microsoft Entra ID (Free Tenant)
- Windows Desktop
- Browser-based administration

## Status
Project in progress. Sections updated sequentially as steps are completed.

## Joiner (New User Onboarding)

- Created new user accounts in Entra ID
- Assigned users to security groups to represent role-based access
- Completed first-time sign-in and password reset
- Enrolled users in MFA as required by Security Defaults
- Verified successful authentication events in sign-in logs
  
**Outcome:** User authenticated successfully with MFA and received group-based access.
  
![User Created](screenshots/joiner/user-created.png)
![Group Membership](screenshots/joiner/group-membership.png)
![MFA Enrollment](screenshots/joiner/mfa-enrollment.png)
![Successful Sign-In](screenshots/joiner/sign-in-success.png)
