# Network Troubleshooting Lab (Multi-Issue Scenario)

## Scenario

A network consisting of VLAN's and three LANs connected via three routers is experiencing connectivity issues. Users are unable to communicate across networks.

## Objective

* Identify and resolve multiple network issues
* Restore full end-to-end connectivity
* Apply systematic troubleshooting methodology

## Initial Configuration

* Configured IP addressing on all devices
* Established routing between routers
* Verified initial connectivity (working state)

## Issues Introduced

1. Incorrect default gateway on PC10
2. Invalid IP address on PC1
3. Shutdown interface G0/1 on R1
4. VLAN 10 is not allowed in a trunk in SW2
5. Missing subinterfaces for VLAN 30 in R1
6. Missing route on R1 and R3

## Troubleshooting Process

### Step 1: Connectivity Test

* Ping from PC10 to PC11 failed
* Ping from PC1 of VLAN 10 to PC9 of VLAN 20 failed

### Step 2: Check PC Configuration

* Found incorrect IP address and default gateway
* Fixed gateway and IP configuration

### Step 3: Check VLAN assignments

* Found vlan misassignment using `show vlan interface brief`
* Assigned PC on its proper VLAN using `switchport access vlan [vlan number]`

### Step 4: VLAN Subinterfaces in a Router

* Verify subinterface existence using the command `show ip interface brief` on R1
* Check Encapsulation to ensure that the missing subinterface is configured with the correct 802.1Q tag using the command `show running-config interface [subinterface]`

### Step 5: Check Router Interfaces

* Discovered interface was shutdown
* Enabled interface using `no shutdown`

### Step 6: Check Routing

* Missing route on R1 and R3
* Added correct route configuration using OSPF

## Result

* Successful end-to-end connectivity restored
* Ping between PC10 and PC11 successful
* Ping between PC1 of VLAN 10 and PC9 of VLAN 20 successful
* Full Inter-VLAN routing and end-to-end connectivity are enabled, allowing devices in different VLANs to communicate across the entire network topology

## Key Learnings

* Systematic troubleshooting is critical in network environments
* Multiple issues can exist simultaneously
* Layer-by-layer analysis helps isolate problems efficiently

## Real-World Application

Network engineers frequently encounter multiple simultaneous issues in production environments. This lab simulates real-world troubleshooting scenarios requiring structured problem-solving and verification.

## Key Skills Demonstrated

Troubleshooting | Network Diagnostics | Inter-VLAN Routing | Routing | Layered Analysis | Cisco CLI
