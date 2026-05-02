# OSPF Multi-Router Network (Enterprise Branch Scenario)

## Scenario

A company has a headquarters (HQ) and two branch offices (Branch A and Branch B). The goal is to implement dynamic routing so that all networks can communicate automatically without manually configuring static routes.

## Objectives

* Configure OSPF (Open Shortest Path First) on multiple routers
* Establish neighbor adjacencies between routers
* Enable full connectivity between all networks
* Verify routing table propagation using OSPF

## Implementation

### Network Design

* R1 (HQ) connected to R2 (Branch A) and R3 (Branch B)
* Separate LAN networks for each branch

### Configuration Steps

* Assigned IP addresses to all router interfaces
* Enabled OSPF process on all routers
* Advertised networks using OSPF network statements
* Placed all routers in **Area 0 (Backbone Area)**

## Verification

The following commands were used to verify OSPF operation:

* `show ip ospf neighbor` → Confirmed neighbor adjacency
* `show ip route` → Verified routes learned via OSPF (marked as “O”)

### Expected Result

* All routers successfully formed OSPF neighbor relationships
* Each router learned remote networks dynamically
* End-to-end connectivity between Branch A and Branch B was successful

## Troubleshooting Scenario

### Problem

Devices in Branch A could not communicate with Branch B

### Investigation

* Ping test failed
* Checked routing table → Missing OSPF routes
* Verified OSPF neighbors → No adjacency formed

### Cause

* Incorrect OSPF network statement prevented neighbor formation

### Solution

* Corrected the OSPF network command on the affected router

### Result

* OSPF adjacency successfully established
* Routes propagated correctly
* Connectivity restored between branches

## Key Learnings

* OSPF dynamically shares routes between routers
* Neighbor adjacency is required before routes are exchanged
* Incorrect network statements can break OSPF operation
* Verification commands are essential for troubleshooting

## Real-World Application

OSPF is widely used in enterprise networks to enable scalable and efficient routing between multiple sites such as headquarters and branch offices. It reduces manual configuration and adapts automatically to network changes.

## Key Skills Demonstrated

OSPF | Dynamic Routing | Network Troubleshooting | Cisco CLI | Routing Verification
