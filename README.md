# In the CCNP Encor course, you'll encounter a variety of commands for both switching and routing, primarily using Cisco IOS. Below is a breakdown of some key command-line instructions you should be familiar with for configuring and managing switching and routing. Note that this is not an exhaustive list but focuses on commonly used commands covered in the course.

Switching Commands
Switching commands are essential for configuring and managing Layer 2 networks, including VLANs, trunking, and Spanning Tree Protocol (STP).

## VLAN Configuration
vlan <number>
## Creates a VLAN (e.g., vlan 10).
name <vlan_name>
## Assigns a name to the VLAN (e.g., name SALES).
## interface vlan <number>
# Enters interface configuration mode for a VLAN, typically for creating a Switched Virtual Interface (SVI) (e.g., interface vlan 10).
## Port Configuration
switchport mode access
## Sets the port to access mode for connecting end devices.
switchport access vlan <number>
## Assigns the port to a specific VLAN (e.g., switchport access vlan 10).
switchport mode trunk
## Sets the port to trunk mode for carrying multiple VLANs.
switchport trunk allowed vlan <list>
# Specifies which VLANs are allowed on the trunk (e.g., switchport trunk allowed vlan 10,20).
## Spanning Tree Protocol (STP)
spanning-tree mode <mode>
## Sets the STP mode (e.g., spanning-tree mode rapid-pvst for Rapid Per-VLAN Spanning Tree).
spanning-tree vlan <vlan_id> root primary
## Configures the switch as the root bridge for a specific VLAN (e.g., spanning-tree vlan 10 root primary).
spanning-tree vlan <vlan_id> priority <priority>
Manually sets the bridge priority for a VLAN (e.g., spanning-tree vlan 10 priority 4096).
# Routing Commands
# Routing commands are crucial for configuring and managing Layer 3 routing protocols like OSPF, EIGRP, and BGP, as well as static routing.

## General Routing Commands
ip route <network> <mask> <next_hop>
## Configures a static route (e.g., ip route 192.168.1.0 255.255.255.0 10.0.0.2).
show ip route
## Displays the routing table.
show ip protocols
Shows information about active routing protocols.
## OSPF (Open Shortest Path First)
router ospf <process_id>
## Enables OSPF with a process ID (e.g., router ospf 1).
network <network> <wildcard> area <area>
## Advertises a network in a specific OSPF area (e.g., network 10.0.0.0 0.255.255.255 area 0).
area <area> authentication
## Enables authentication for an OSPF area (e.g., area 0 authentication).
interface <interface> ip ospf <process_id> area <area>
## Directly assigns an interface to an OSPF area (e.g., interface GigabitEthernet0/0 ip ospf 1 area 0).
## EIGRP (Enhanced Interior Gateway Routing Protocol)
router eigrp <as_number>
## Enables EIGRP with an autonomous system number (e.g., router eigrp 100).
network <network> <wildcard>
## Advertises a network in EIGRP (e.g., network 10.0.0.0 0.255.255.255).
eigrp router-id <id>
## Sets the EIGRP router ID (e.g., eigrp router-id 1.1.1.1).
variance <value>
## Adjusts load-balancing behavior in EIGRP (e.g., variance 2).
## BGP (Border Gateway Protocol)
router bgp <as_number>
## Enables BGP with an autonomous system number (e.g., router bgp 65001).
neighbor <ip> remote-as <as_number>
## Defines a BGP neighbor (e.g., neighbor 192.168.1.2 remote-as 65002).
network <network> mask <mask>
## Advertises a network in BGP (e.g., network 10.0.0.0 mask 255.255.255.0).
aggregate-address <network> <mask>
## Configures route aggregation in BGP (e.g., aggregate-address 10.0.0.0 255.255.0.0).
# Important Notes
# Not Exhaustive: This list highlights key commands commonly emphasized in the CCNP Encor course. The full scope of commands may vary depending on specific topics or lab scenarios.
# Practice Required: To master these commands, practice them in a lab environment like Cisco Packet Tracer or real hardware.
# Context Matters: Many commands require additional parameters or context (e.g., entering the correct configuration mode with configure terminal).
