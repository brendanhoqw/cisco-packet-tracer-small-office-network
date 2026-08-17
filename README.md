# Cisco Packet Tracer Small Office Network

## Project Overview

This project simulates a small-office network using Cisco Packet Tracer. It was created to practice fundamental networking concepts relevant to entry-level IT support, including IPv4 addressing, subnetting, DHCP, DNS, VLANs, trunking, default gateways, and connectivity troubleshooting.

The project contains two completed Packet Tracer labs:

1. A routed small-office network with DHCP and internal DNS.
2. A departmental VLAN network with inter-VLAN routing.

## Technologies Used

- Cisco Packet Tracer
- Cisco 2911 Router
- Cisco Catalyst 2960 Switch
- IPv4 and `/24` subnetting
- DHCP
- DNS and HTTP services
- VLANs and 802.1Q trunking
- Router-on-a-stick
- ICMP ping and traceroute

## Lab 1: DHCP and Internal DNS

The first lab contains two networks connected through a Cisco 2911 router:

| Network | Router Gateway | Address Allocation |
|---|---|---|
| `192.168.10.0/24` | `192.168.10.1` | DHCP |
| `192.168.20.0/24` | `192.168.20.1` | DHCP |

### Configuration Completed

- Connected PCs to Cisco 2960 switches.
- Configured router interfaces for both networks.
- Created DHCP pools for automatic IP configuration.
- Excluded addresses `.1` through `.99` from DHCP allocation.
- Configured a Server-PT device with the static address `192.168.10.2`.
- Created the internal DNS record `intranet.office.local`.
- Enabled HTTP service on the internal server.
- Verified hostname resolution and website access from the second network.
- Tested connectivity using `ping` and `tracert`.

## Lab 2: VLANs and Inter-VLAN Routing

The second lab separates IT and Finance devices using VLANs on one physical switch:

| Department | VLAN | Network | Default Gateway |
|---|---:|---|---|
| IT | 10 | `192.168.10.0/24` | `192.168.10.1` |
| Finance | 20 | `192.168.20.0/24` | `192.168.20.1` |

### Device Addressing

| Device | IP Address | VLAN |
|---|---|---:|
| IT-PC1 | `192.168.10.11` | 10 |
| IT-PC2 | `192.168.10.12` | 10 |
| FIN-PC1 | `192.168.20.21` | 20 |
| FIN-PC2 | `192.168.20.22` | 20 |

### Configuration Completed

- Created VLAN 10 and named it `IT`.
- Created VLAN 20 and named it `FINANCE`.
- Assigned switch access ports to their respective VLANs.
- Configured the switch-to-router connection as an 802.1Q trunk.
- Configured router subinterface `G0/0.10` as the IT gateway.
- Configured router subinterface `G0/0.20` as the Finance gateway.
- Enabled inter-VLAN routing using a router-on-a-stick design.
- Verified communication within each VLAN and between VLANs.

## Troubleshooting Practised

- Identified incorrect IP address and subnet configurations.
- Tested the effect of an incorrect default gateway.
- Diagnosed inactive router interfaces using interface status checks.
- Used `no shutdown` to enable an administratively disabled interface.
- Distinguished physical link problems from IP configuration problems.
- Verified VLAN membership, trunk operation, and router subinterface status.
- Used `ping` and `tracert` to follow traffic across different networks.

## Key Lessons

- Devices in the same subnet can communicate directly through a switch.
- Devices in different subnets send traffic to a default gatewa
