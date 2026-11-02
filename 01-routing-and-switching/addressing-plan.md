# Addressing Plan: Lab 01

Every router-to-router link uses a /30. The link number matches the third octet, so an address tells you which link it is on.

## Links

| # | Link | Subnet | Side A | Side B |
|---|------|--------|--------|--------|
| L1 | SW1 Gi0/1 to R1 Gi0/0 | 10.0.1.0/30 | SW1 .1 | R1 .2 |
| L2 | SW1 Gi0/0 to R2 Gi0/0 | 10.0.2.0/30 | SW1 .1 | R2 .2 |
| L3 | R1 Gi0/1 to ISP Gi0/0 | 10.0.3.0/30 | R1 .1 | ISP .2 |
| L4 | R2 Gi0/1 to ISP Gi0/1 | 10.0.4.0/30 | R2 .1 | ISP .2 |
| L5 | ISP Gi0/2 to R3 Gi0/0 | 10.0.5.0/30 | ISP .1 | R3 .2 |
| L6 | ISP Gi0/3 to R4 Gi0/1 | 10.0.6.0/30 | ISP .1 | R4 .2 |
| L7 | R3 Gi0/1 to SW2 Gi0/0 | 10.0.7.0/30 | R3 .1 | SW2 .2 |
| L8 | R4 Gi0/0 to SW2 Gi0/1 | 10.0.8.0/30 | R4 .1 | SW2 .2 |
| WAN | ISP Gi0/4 to Internet | 203.0.0.0/24 | ISP .2 | Cloud .1 |

## LANs

| LAN | Subnet | Gateway | Host |
|-----|--------|---------|------|
| Site A | 192.168.1.0/24 | SW1 Gi0/2, .1 | PC1 .10 |
| Site B | 192.168.2.0/24 | SW2 Gi0/2, .1 | PC2 .10 |

## Loopbacks (planned, for OSPF router IDs)

| Device | Loopback0 |
|--------|-----------|
| SW1 | 10.255.0.1/32 |
| R1 | 10.255.0.2/32 |
| R2 | 10.255.0.3/32 |
| ISP | 10.255.0.4/32 |
| R3 | 10.255.0.5/32 |
| R4 | 10.255.0.6/32 |
| SW2 | 10.255.0.7/32 |
