# Lab 02 – DHCP per VLAN on Cisco Catalyst 3560 v2

## Objective
Implement DHCP services for multiple VLANs on a Layer-3 Cisco switch while preserving existing inter-VLAN routing and access control policies.

## Hardware Used
- Cisco Catalyst 3560 v2 (Layer-3 switch)
- End devices (PCs / laptops)

## VLAN and IP Design

| VLAN | Name  | Subnet |
|------|------|--------|
| 10 | STAFF | 192.168.10.0/24 |
| 20 | ADMIN | 192.168.20.0/24 |
| 30 | GUEST | 192.168.30.0/24 |

Default gateways are provided by Switch Virtual Interfaces (SVIs).

## DHCP Design

Each VLAN is served by a dedicated DHCP pool on the switch. Infrastructure IP ranges are excluded to prevent conflicts with static addressing.

## Notes
- Existing inter-VLAN routing and ACLs from Lab 01 are preserved
- DHCP functionality is validated without weakening guest access restrictions
- During testing, it was observed that SVIs require at least one active Layer‑2 port in the VLAN to be fully reachable. A behaviour confirmed and resolved by ensuring VLAN 30 had an active access port
 
## Verification & Outcome
- DHCP successfully assigns IP addresses per VLAN
- Default gateways delivered via SVIs
- Inter-VLAN routing preserved
- Guest access restrictions remain enforced
- DHCP bindings verified on the switch
