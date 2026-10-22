# Lab 005 — Azure Cost Management and FinOps

## Business Problem
Octageo needs visibility into Azure spending and early warning of unexpected costs before expanding its data and AI workloads.

## Objectives
- Establish a monthly Azure budget.
- Configure spending alerts.
- Analyze costs by service and resource group.
- Investigate tag-based cost allocation.
- Define an operational cost-control process.

## Solution Design
- Scope: Azure subscription
- Budget: budget-octageo-monthly
- Reset period: Monthly
- Budget amount: [Enter actual amount and currency]
- Alert thresholds: 50%, 80%, 100%
- Alert recipient: [Configured — do not publish personal email]

## Baseline Cost Analysis
- Reporting period:
- Total recorded cost:
- Highest-cost service:
- Highest-cost resource group:
- Unexpected charges:

## Validation Results

| Test | Expected Result | Actual Result |
|---|---|---|
| Monthly budget created | Budget appears in Azure Portal | Pending |
| 50% alert configured | Saved successfully | Pending |
| 80% alert configured | Saved successfully | Pending |
| 100% alert configured | Saved successfully | Pending |
| Cost analysis reviewed | Spending breakdown visible | Pending |
| Tag-based allocation investigated | Limitations documented | Pending |

## Architecture Decisions
- Use subscription-level budgets to monitor total spending.
- Apply consistent cost-allocation tags to chargeable resources.
- Review costs after each hands-on lab.
- Use resource cleanup to reduce unnecessary charges.
- Treat budgets as alerts, not spending caps.

## Evidence
Add sanitized screenshots of:
1. Monthly budget configuration
2. Alert thresholds
3. Cost analysis by service
4. Cost analysis by resource group

## Lessons Learned
Document the differences between cost monitoring, budgeting, tagging, forecasting and automated cost controls.

## Future Improvements
- Resource-level tagging enforcement
- Azure Policy tag inheritance
- Automated resource shutdown
- Cost reporting dashboard
- Infrastructure-as-code deployment of budgets
