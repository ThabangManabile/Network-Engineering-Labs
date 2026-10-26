# Lab 02: Connecting Two Subnets with a Router

## Goal
Connect two separate subnets (`192.168.10.0/24` and `192.168.20.0/24`) using a Cisco router to enable inter-subnet communication via default gateways.

## Topology
- 1 x Cisco Router (R1)
- 2 x Cisco 2960 Switches (SW1, SW2)
- 4 x PCs (PC1, PC2 on LAN A; PC3, PC4 on LAN B)
- GigabitEthernet links used for switch-to-router connections

## Addressing Table
| Device | Interface | IP Address | Subnet Mask | Default Gateway |
|--------|-----------|------------|-------------|-----------------|
| PC1 | NIC | 192.168.10.10 | 255.255.255.0 | 192.168.10.1 |
| PC2 | NIC | 192.168.10.20 | 255.255.255.0 | 192.168.10.1 |
| PC3 | NIC | 192.168.20.10 | 255.255.255.0 | 192.168.20.1 |
| PC4 | NIC | 192.168.20.20 | 255.255.255.0 | 192.168.20.1 |
| R1 | Gig0/0 | 192.168.10.1 | 255.255.255.0 | N/A |
| R1 | Gig0/1 | 192.168.20.1 | 255.255.255.0 | N/A |

## Verification
Ping from PC1 (`192.168.10.10`) to PC3 (`192.168.20.10`) across the router:
