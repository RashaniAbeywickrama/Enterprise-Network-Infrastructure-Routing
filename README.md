# Enterprise Network Infrastructure & Routing

## Project Overview

This project focuses on designing, configuring, and implementing an enterprise network infrastructure using Cisco Packet Tracer.

The simulated network represents a company with four departments: HR, Finance, IT, and Sales. Each department operates within a separate VLAN to improve network segmentation, organization, and management.

The network also includes an internal server and an external test server to demonstrate internal and external connectivity.

The project covers essential networking technologies, including VLANs, trunking, inter-VLAN routing, DHCP, OSPF, NAT/PAT, and Spanning Tree Protocol (STP).

## Project Objectives

- Design an enterprise network topology using Cisco Packet Tracer.
- Configure VLANs to separate departmental networks.
- Implement IEEE 802.1Q trunking between switches.
- Configure inter-VLAN routing using router-on-a-stick.
- Implement DHCP for automatic IP address allocation.
- Configure OSPF for dynamic routing between routers.
- Implement NAT/PAT for external network connectivity.
- Configure STP to prevent Layer 2 switching loops.
- Perform connectivity testing and network troubleshooting.

## Network Topology

The simulated enterprise network consists of:

| Device | Quantity | Purpose |
|---|---:|---|
| Cisco 2911 Routers | 2 | Internal and edge routing |
| Cisco 2960 Switches | 3 | Departmental connectivity and VLAN management |
| PCs | 8 | Employee devices across four departments |
| Internal Server | 1 | Internal network services |
| External Test Server | 1 | Simulated external connectivity testing |

## VLAN and IP Addressing Plan

| Department | VLAN ID | Network | Default Gateway |
|---|---:|---|---|
| HR | 10 | 192.168.10.0/24 | 192.168.10.1 |
| Finance | 20 | 192.168.20.0/24 | 192.168.20.1 |
| IT | 30 | 192.168.30.0/24 | 192.168.30.1 |
| Sales | 40 | 192.168.40.0/24 | 192.168.40.1 |
| Servers | 50 | 192.168.50.0/24 | 192.168.50.1 |

### Router-to-Router Link

| Device | Interface | IP Address |
|---|---|---|
| R1 | G0/0 | 10.0.0.1/30 |
| R2 | G0/0 | 10.0.0.2/30 |

### External Network

| Device | Interface | IP Address |
|---|---|---|
| R2 | G0/1 | 203.0.113.1/24 |
| External Test Server | Fa0 | 203.0.113.10/24 |

The external test server uses 203.0.113.1 as its default gateway.

## Technologies and Implementations

### 1. VLAN Configuration

Created five VLANs to logically separate the enterprise network into departmental and server networks.

### 2. Trunking

Configured IEEE 802.1Q trunk links between switches to carry traffic from multiple VLANs across the network.

### 3. Inter-VLAN Routing

Implemented router-on-a-stick using subinterfaces on R1 to enable communication between different VLANs.

### 4. DHCP Configuration

Configured DHCP pools on R1 to automatically assign IP addresses, subnet masks, default gateways, and other network settings to client PCs.

### 5. OSPF Dynamic Routing

Configured Open Shortest Path First (OSPF) on both routers to exchange routing information and enable communication between the internal enterprise network and the edge router.

### 6. NAT/PAT

Configured Network Address Translation and Port Address Translation on R2 to allow internal private IP addresses to communicate with the simulated external network.

### 7. Spanning Tree Protocol (STP)

Configured STP with S1 as the primary root bridge to help prevent Layer 2 switching loops in the redundant switched topology.

## Verification and Testing

The following Cisco IOS commands are useful for verifying the network configuration.

### VLAN and Switching Verification

```bash
show vlan brief
show interfaces trunk
show spanning-tree
```

### Router and Routing Verification

```bash
show ip interface brief
show ip route
show ip ospf neighbor
```

### DHCP Verification

```bash
show ip dhcp binding
show ip dhcp pool
```

### NAT/PAT Verification

```bash
show ip nat translations
show ip nat statistics
```

### Connectivity Testing

```bash
ping <destination-ip-address>
```

## Testing Progress

The following results were confirmed during implementation:

| Test | Result |
|---|---|
| DHCP address assignment to all 8 PCs | Successful |
| Internal PC to external test server ping | Successful |
| Other VLAN and routing verification | To be documented after final verification |

## Tools and Technologies

- Cisco Packet Tracer
- Cisco IOS CLI
- IPv4 Addressing and Subnetting
- Virtual LANs (VLANs)
- IEEE 802.1Q Trunking
- Inter-VLAN Routing
- DHCP
- OSPF
- NAT/PAT
- Spanning Tree Protocol (STP)
- Network Troubleshooting

## Learning Outcomes

Through this project, I gained practical experience in:

- Designing and implementing an enterprise network topology.
- Configuring VLANs and trunk links across multiple switches.
- Implementing inter-VLAN routing.
- Configuring DHCP services.
- Understanding and implementing dynamic routing with OSPF.
- Configuring NAT/PAT for external connectivity.
- Implementing STP in a redundant switching environment.
- Using Cisco IOS commands for network verification and troubleshooting.

## Conclusion

This project provided practical experience in designing and configuring a simulated enterprise network using Cisco Packet Tracer.

It strengthened my understanding of enterprise networking concepts, routing and switching technologies, network segmentation, and troubleshooting.
