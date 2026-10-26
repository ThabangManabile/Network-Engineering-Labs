# Lab 01: Two PCs and One Switch

## Goal
Connect two PCs through a switch and confirm they can communicate.

## Topology
- 1 x Cisco 2960-24TT switch (SW1)
- 2 x PCs (PC1 on Fa0/1, PC2 on Fa0/2)
- Copper straight-through cables

## Addressing
| Device | IP address | Subnet mask |
|--------|-----------|-------------|
| PC1 | 192.168.1.10 | 255.255.255.0 |
| PC2 | 192.168.1.20 | 255.255.255.0 |

## Verification
Ping from PC1 to PC2 succeeded with 0% loss:

```
C:\>ping 192.168.1.20
Reply from 192.168.1.20: bytes=32 time<1ms TTL=128
Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
```

The switch learned both MAC addresses dynamically:

```
SW1#show mac address-table
Vlan  Mac Address       Type     Ports
1     0040.0b92.8d81    DYNAMIC  Fa0/1
1     00e0.a367.1c46    DYNAMIC  Fa0/2
```

## What I learned
- Devices on the same network talk directly through a switch, with no router needed.
- TTL stays at 128 because the packet never crosses a router.
- A switch builds its MAC address table by watching traffic.
