# Lab 003 — Enforcing Azure Governance with Azure Policy

## Business Problem
Resource groups can be created without mandatory governance tags.

## Objective
Prevent deployment of resource groups missing Environment tags.

## Architecture Decision
Use Azure Policy with a built-in Deny policy.

## Implementation
- Scope: Azure subscription
- Policy: Require a tag on resource groups
- Assignment: octageo-require-environment-tag
- Parameter: Environment
- Effect: Deny

## Test Results
| Test | Expected | Actual |
|------|----------|--------|
| Missing tag | Denied | |
| Environment=Dev | Allowed | |
| Compliance evaluation | Visible | |

## Evidence
- Policy assignment screenshot
- Compliance results
- Denied deployment screenshot
- Successful deployment screenshot

## Lessons Learned
- Azure Policy versus RBAC
- Policy definitions versus assignments
- Audit versus Deny
- Subscription versus resource group scope
- Safe policy rollout
