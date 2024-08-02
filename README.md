# Packet Tracer – Subnet an IPv4 Network

## Overview
This project involves designing and implementing a subnetting scheme for a customer's network, configuring network devices, and testing connectivity to ensure all components function as expected.

## Objectives
1. **Design an IPv4 Network Subnetting Scheme**
2. **Configure the Devices**
3. **Test and Troubleshoot the Network**

## Addressing Table
| Device         | Interface | IP Address       | Subnet Mask        | Default Gateway   |
|----------------|-----------|------------------|--------------------|-------------------|
| CustomerRouter | G0/0      | *Assigned*       | *Assigned*         | N/A               |
| CustomerRouter | G0/1      | *Assigned*       | *Assigned*         | N/A               |
| CustomerRouter | S0/1/0    | 209.165.201.2    | 255.255.255.252    | N/A               |
| LAN-A Switch   | VLAN1     | *Assigned*       | *Assigned*         | *Assigned*        |
| LAN-B Switch   | VLAN1     | *Assigned*       | *Assigned*         | *Assigned*        |
| PC-A           | NIC       | *Assigned*       | *Assigned*         | *Assigned*        |
| PC-B           | NIC       | *Assigned*       | *Assigned*         | *Assigned*        |
| ISPRouter      | G0/0      | 209.165.200.225  | 255.255.255.224    | N/A               |
| ISPRouter      | S0/1/0    | 209.165.201.1    | 255.255.255.252    | N/A               |
| ISPSwitch      | VLAN1     | 209.165.200.226  | 255.255.255.224    | 209.165.200.225   |
| ISP Workstation| NIC       | 209.165.200.235  | 255.255.255.224    | 209.165.200.225   |
| ISP Server     | NIC       | 209.165.200.240  | 255.255.255.224    | 209.165.200.225   |

## Configuration Steps

### Subnetting Scheme
- **LAN-A**: Requires at least 50 host addresses.
- **LAN-B**: Needs at least 40 host addresses.
- Two additional subnets reserved for future expansion.
- Subnetting created from a 192.168.0.0/24 network.

### Device Configuration
- **Routers and Switches**: Hostnames set, interfaces configured with IP addresses, subnet masks, and default gateways. Security features such as password encryption and SSH configured.
- **PCs**: IP configuration completed with static IPs, subnet masks, and gateways.

### Testing and Troubleshooting
- **Connectivity Tests**: Successful ping tests from PCs to their respective gateways and between PCs to confirm network functionality.

## Summary of Commands
```command
# Sample commands used for router and switch configurations
Router(config)# hostname CustomerRouter
Router(config)# interface g0/0
Router(config-if)# ip address [IP_ADDRESS] [SUBNET_MASK]
Router(config-if)# no shutdown
Router(config)# enable secret [PASSWORD]
...
Switch(config)# vlan 1
Switch(config-if)# ip address [IP_ADDRESS] [SUBNET_MASK]
Switch(config-if)# no shutdown
Switch(config)# enable secret [PASSWORD]
