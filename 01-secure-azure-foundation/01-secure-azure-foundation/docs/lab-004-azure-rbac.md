# Lab 004 — Azure RBAC and Least-Privilege Access

## Business Problem
Octageo requires controlled access to Azure infrastructure without granting unnecessary administrative permissions.

## Requirements
- Restrict access to authorized engineering team members.
- Allow infrastructure visibility.
- Prevent unauthorized resource changes.
- Restrict access management to authorized administrators.

## Architecture Decision
Implement group-based Azure RBAC using a Microsoft Entra security group and the built-in Reader role at resource-group scope.

## Implementation
- Resource Group: rg-octageo-dev-01
- Security Group: sg-octageo-data-readers
- Azure Role: Reader
- Scope: Resource Group

## Validation

| Test | Expected | Actual |
|---|---|---|
| Reader assignment exists | Pass | Pending |
| Test identity can view resources | Allowed | Pending |
| Test identity can modify tags | Denied | Pending |
| Test identity can create resources | Denied | Pending |
| Test identity can assign RBAC roles | Denied | Pending |

## Security Considerations
- Azure RBAC permissions are additive.
- Roles assigned at higher scopes may be inherited.
- Reader does not automatically provide data-plane access.
- Resource locks and Azure Policy remain separate governance controls.

## Evidence
- Existing role assignments
- Entra security group
- Reader role assignment
- Access validation results

## Lessons Learned
Document the difference between authentication and authorization, group-based access, role definitions, role assignments, scope and effective permissions.
