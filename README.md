# IAM Identity Lifecycle Lab

## Objective
Demonstrate joiner, mover, and leaver identity lifecycle using Microsoft Entra ID with authentication, MFA enforcement, and audit logging.

## Environment
- Microsoft Entra ID (Free Tenant)
- Windows Desktop
- Browser-based administration
  
## Skills Demonstrated
- Microsoft Entra ID (Azure AD): users, groups, authentication
- Group-based access (RBAC concept)
- MFA via Security Defaults
- Audit Logs & Sign-in Logs validation
- Identity lifecycle: Joiner / Mover / Leaver

## How to Reproduce (High Level)
1. Create a user in Entra ID
2. Assign user to a security group (role-based access simulation)
3. Sign in as the user and complete MFA enrollment
4. Validate authentication in Sign-in Logs
5. Modify access by changing group membership and validate in Audit Logs
6. Offboard: block sign-in → remove group memberships → delete user
7. Confirm access denial + log evidence
   
## Status
Project completed.

## Joiner (New User Onboarding)
- Created new user account(s) in Entra ID
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
- Removed all group memberships
- Deleted user account
- Attempted sign-in to confirm access denial
- Verified actions in audit and sign-in logs

**Outcome:** User access fully revoked with auditable evidence.

![Blocked Sign-In](screenshots/leaver/sign-in-blocked.png)
![Group Removed](screenshots/leaver/group-removed.png)
![User Disabled](screenshots/leaver/user-disabled.png)
![User Deleted](screenshots/leaver/user-deleted.png)
![Failed Sign-in](screenshots/leaver/failed-sign-in.png)

## Logging & Audit Review

- Reviewed Entra ID audit logs for lifecycle events
- Verified authentication and MFA enforcement
- Confirmed audit visibility for all actions

![Audit User Created Logs](screenshots/logs/audit-user-created.png)
![Audit MFA](screenshots/logs/audit-mfa.png)
![Sign-In Logs](screenshots/logs/sign-in-log.png)
![Audit User Disabled](screenshots/logs/audit-user-disabled.png)
![Audit User Disabled Logs](screenshots/logs/audit-user-deleted.png)

## Limitations / Next Iteration
- Used Security Defaults (MFA). Next: Conditional Access policy + per-group MFA.
- Next: automate joiner/mover/leaver with PowerShell or Graph API.
- Next: add PIM (Privileged Identity Management) scenario / role assignment.
