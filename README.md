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

## Mover (Role / Access Change)
- Removed user from original security group
- Assigned user to a new security group representing a role change
- Validated updated group membership
- Confirmed changes recorded in audit logs

**Outcome:** Access updated without recreating the user account.

![Group Before](screenshots/mover/group-before.png)
![Group After](screenshots/mover/group-after.png)
![Group Change Log](screenshots/logs/audit-group-change.png)

## Leaver (Offboarding)
- Blocked user sign-in
- Reset credentials
- Removed all group memberships
- Deleted user account
- Attempted sign-in to confirm access denial
- Verified actions in audit and sign-in logs

**Outcome:** User access fully revoked with auditable evidence.

![Blocked Sign-In](screenshots/leaver/sign-in-blocked.png)
![Group Removed](screenshots/leaver/group-removed.png)
![User Deleted](screenshots/leaver/user-deleted.png)
![Failed Sign-in](screenshots/leaver/failed-sign-in.png)
