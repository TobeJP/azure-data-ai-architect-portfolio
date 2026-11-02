# Lab 006 — Azure Virtual Network Architecture

## 1. Executive Summary

Octageo requires a scalable and governed network foundation for its Azure Data & AI Platform.

This lab designs and deploys a development virtual network with four purpose-based subnets, validates address allocation and demonstrates troubleshooting of overlapping CIDR ranges.

## 2. Business Problem

The organization lacks a standardized Azure network design, creating risks of inconsistent workload placement, overlapping IP ranges and insecure connectivity.

## 3. Requirements

| ID | Requirement |
|---|---|
| NET-01 | Dedicated development virtual network |
| NET-02 | Nonoverlapping IPv4 address ranges |
| NET-03 | Four purpose-based subnets |
| NET-04 | Compliance with Azure governance standards |
| NET-05 | Minimal deployment cost |
| NET-06 | Documented implementation and validation |

## 4. Solution Architecture

- Resource Group: rg-octageo-network-dev-01
- Virtual Network: vnet-octageo-dev-01
- Region: Canada Central
- Address Space: 10.20.0.0/16

### Subnet Design

| Subnet | CIDR | Purpose |
|---|---|---|
| snet-app-dev | 10.20.1.0/24 | Application workloads |
| snet-data-dev | 10.20.2.0/24 | Data workloads |
| snet-private-dev | 10.20.3.0/24 | Private endpoints |
| snet-mgmt-dev | 10.20.4.0/24 | Management workloads |

## 5. Architecture Decisions

**ADR-006-01: Dedicated Networking Resource Group**

A separate resource group was selected to support clear infrastructure ownership and lifecycle management.

**ADR-006-02: Private IPv4 Addressing**

The 10.20.0.0/16 range was selected for development, subject to verification against existing network allocations.

**ADR-006-03: Purpose-Based Subnets**

Four subnets provide organized address allocation for future workloads. Subnet-level traffic isolation is not yet implemented.

**ADR-006-04: Explicit Outbound Connectivity**

Private subnets are preferred. Outbound internet access will be designed explicitly when required by workloads.

## 6. Implementation

Document the Azure Portal steps used to create the resource group, virtual network and subnets.

## 7. Validation Results

| Test | Expected result | Actual result |
|---|---|---|
| VNet deployment | Succeeded | Pending |
| VNet address space | 10.20.0.0/16 | Pending |
| Application subnet | 10.20.1.0/24 | Pending |
| Data subnet | 10.20.2.0/24 | Pending |
| Private subnet | 10.20.3.0/24 | Pending |
| Management subnet | 10.20.4.0/24 | Pending |
| Overlapping subnet test | Rejected | Pending |

## 8. Troubleshooting

### Problem
Attempted subnet creation using an overlapping address range.

### Root Cause
The proposed 10.20.2.128/25 range overlaps the existing 10.20.2.0/24 subnet.

### Resolution
Rejected the overlapping configuration and retained the approved nonoverlapping address plan.

## 9. Evidence

- Resource group configuration
- Virtual network overview
- Address space configuration
- Subnet list
- Overlapping-subnet validation error

## 10. Security and Cost Considerations

- No virtual machines or paid gateways deployed.
- No public IP addresses required.
- Subnet traffic restrictions not yet implemented.
- Network Security Groups will be introduced in the next lab.

## 11. Next Steps

- Create Network Security Groups.
- Define inbound and outbound traffic rules.
- Associate NSGs with appropriate subnets.
- Test rule priority and traffic restrictions.
- Extend the architecture toward private connectivity and enterprise data services.
