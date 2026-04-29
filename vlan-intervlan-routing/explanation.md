# VLAN Segmentation & Inter-VLAN Routing (Enterprise Scenario)

## Scenario
A company needs to segment its departments (HR, IT, Sales) using VLANs while allowing communication between them.

## Objectives
- Configure VLANs for each department
- Enable inter-VLAN communication
- Ensure proper network segmentation

## Implementation
- Created VLAN 10 (HR), VLAN 20 (IT), VLAN 30 (Sales)
- Assigned switch ports to respective VLANs
- Configured trunking between switch and router
- Implemented router-on-a-stick for inter-VLAN routing

## Verification
- Successful ping between devices in different VLANs
- Verified trunk using: `show interfaces trunk`
- Verified VLANs using: `show vlan brief`

## Troubleshooting Scenario
Issue: Devices in different VLANs could not communicate  
Cause: Incorrect encapsulation on router subinterface  
Fix: Corrected encapsulation to dot1Q  

## Result
All VLANs can communicate successfully while maintaining segmentation.

## Key Skills Demonstrated
VLAN | Trunking | Inter-VLAN Routing | Troubleshooting | Cisco CLI