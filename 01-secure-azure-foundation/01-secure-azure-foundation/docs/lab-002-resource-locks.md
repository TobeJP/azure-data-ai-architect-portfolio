# Lab 002 — Azure Resource Deletion Protection

## Business Problem
Octageo's Azure resources are vulnerable to accidental deletion by users with administrative permissions.

## Objective
Implement and validate resource-group deletion protection without preventing normal administrative updates.

## Solution
Apply an Azure CanNotDelete management lock.

## Implementation
- Resource Group: rg-octageo-dev-01
- Lock: lock-octageo-prevent-delete
- Lock Type: CanNotDelete
- Scope: Resource Group

## Validation Tests

| Test | Expected Result | Actual Result |
|---|---|---|
| Apply deletion lock | Lock created | Pending |
| Delete protected test group | Deletion blocked | Pending |
| Update protected resource group tags | Update succeeds | Pending |
| Remove temporary test lock | Lock removed | Pending |
| Delete temporary test group | Deletion succeeds | Pending |

## Architecture Decision
CanNotDelete was selected over ReadOnly because Octageo requires deletion protection while continuing to configure and modify its Azure environment.

## Limitations
Management locks protect control-plane operations, not all data-plane operations. Authorized administrators with lock-management permissions may remove locks. Locks can also interfere with some service lifecycle operations.

## Evidence
Add sanitized screenshots showing the lock configuration, blocked deletion, successful tag update and temporary group cleanup.

## Lessons Learned
Document what was learned about management locks, lock inheritance, control-plane protection and the difference between RBAC and locks.
