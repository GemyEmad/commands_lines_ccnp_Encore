# Cisco Networking Commands - README.md

This README.md file summarizes key Cisco switching and routing commands relevant to the CCNA and CCNP Encor courses. It covers Layer 2 switching configurations (e.g., VLANs, trunking, STP) and Layer 3 routing configurations (e.g., static routes, OSPF, EIGRP, BGP), with examples and additional notes for practical application.

---

## Switching Commands

Switching commands are used to configure and manage Layer 2 features, such as VLANs, trunking, and Spanning Tree Protocol (STP). These are essential for managing network switches in both CCNA and CCNP Encor.

### VLAN Configuration

- **`vlan <number>`**  
  Creates a VLAN.  
  *Example:* `vlan 10`  
  *(CCNA & CCNP Encor)*

- **`name <vlan_name>`**  
  Assigns a name to the VLAN.  
  *Example:* `name SALES`  
  *(CCNA & CCNP Encor)*

- **`interface vlan <number>`**  
  Enters interface configuration mode for a VLAN to create a Switched Virtual Interface (SVI).  
  *Example:* `interface vlan 10`  
  *(CCNA & CCNP Encor)*

### Port Configuration

- **`switchport mode access`**  
  Sets the port to access mode for connecting end devices.  
  *(CCNA & CCNP Encor)*

- **`switchport access vlan <number>`**  
  Assigns the port to a specific VLAN.  
  *Example:* `switchport access vlan 10`  
  *(CCNA & CCNP Encor)*

- **`switchport mode trunk`**  
  Sets the port to trunk mode to carry multiple VLANs.  
  *(CCNA & CCNP Encor)*

- **`switchport trunk allowed vlan <list>`**  
  Specifies which VLANs are allowed on the trunk.  
  *Example:* `switchport trunk allowed vlan 10,20`  
  *(CCNA & CCNP Encor)*

### Spanning Tree Protocol (STP)

- **`spanning-tree mode <mode>`**  
  Sets the STP mode (e.g., `pvst`, `rapid-pvst`, `mst`).  
  *Example:* `spanning-tree mode rapid-pvst`  
  *(CCNA & CCNP Encor)*

- **`spanning-tree vlan <vlan_id> root primary`**  
  Configures the switch as the root bridge for a specific VLAN.  
  *Example:* `spanning-tree vlan 10 root primary`  
  *(CCNA & CCNP Encor)*

- **`spanning-tree vlan <vlan_id> priority <priority>`**  
  Manually sets the bridge priority for a VLAN.  
  *Example:* `spanning-tree vlan 10 priority 4096`  
  *(CCNA & CCNP Encor)*

---

## Routing Commands

Routing commands are used to configure and manage Layer 3 routing, including static routes and dynamic protocols like OSPF, EIGRP, and BGP. These are foundational in CCNA and expanded upon in CCNP Encor.

### General Routing Commands

- **`ip route <network> <mask> <next_hop>`**  
  Configures a static route.  
  *Example:* `ip route 192.168.1.0 255.255.255.0 10.0.0.2`  
  *(CCNA & CCNP Encor)*

- **`show ip route`**  
  Displays the routing table.  
  *(CCNA & CCNP Encor)*

- **`show ip protocols`**  
  Shows information about active routing protocols.  
  *(CCNA & CCNP Encor)*

### OSPF (Open Shortest Path First)

- **`router ospf <process_id>`**  
  Enables OSPF with a process ID.  
  *Example:* `router ospf 1`  
  *(CCNA & CCNP Encor)*

- **`network <network> <wildcard> area <area>`**  
  Advertises a network in a specific OSPF area.  
  *Example:* `network 10.0.0.0 0.255.255.255 area 0`  
  *(CCNA & CCNP Encor)*

- **`area <area> authentication`**  
  Enables authentication for an OSPF area.  
  *Example:* `area 0 authentication`  
  *(CCNP Encor)*

- **`interface <interface> ip ospf <process_id> area <area>`**  
  Directly assigns an interface to an OSPF area.  
  *Example:* `interface GigabitEthernet0/0 ip ospf 1 area 0`  
  *(CCNP Encor)*

### EIGRP (Enhanced Interior Gateway Routing Protocol)

- **`router eigrp <as_number>`**  
  Enables EIGRP with an autonomous system number.  
  *Example:* `router eigrp 100`  
  *(CCNA & CCNP Encor)*

- **`network <network> <wildcard>`**  
  Advertises a network in EIGRP.  
  *Example:* `network 10.0.0.0 0.255.255.255`  
  *(CCNA & CCNP Encor)*

- **`eigrp router-id <id>`**  
  Sets the EIGRP router ID.  
  *Example:* `eigrp router-id 1.1.1.1`  
  *(CCNP Encor)*

- **`variance <value>`**  
  Adjusts load-balancing behavior in EIGRP.  
  *Example:* `variance 2`  
  *(CCNP Encor)*

### BGP (Border Gateway Protocol)

- **`router bgp <as_number>`**  
  Enables BGP with an autonomous system number.  
  *Example:* `router bgp 65001`  
  *(CCNP Encor)*

- **`neighbor <ip> remote-as <as_number>`**  
  Defines a BGP neighbor.  
  *Example:* `neighbor 192.168.1.2 remote-as 65002`  
  *(CCNP Encor)*

- **`network <network> mask <mask>`**  
  Advertises a network in BGP.  
  *Example:* `network 10.0.0.0 mask 255.255.255.0`  
  *(CCNP Encor)*

- **`aggregate-address <network> <mask>`**  
  Configures route aggregation in BGP.  
  *Example:* `aggregate-address 10.0.0.0 255.255.0.0`  
  *(CCNP Encor)*

---

## Additional Notes

- **Scope:** This list covers key commands for CCNA and CCNP Encor but is not exhaustive. Additional commands may be required depending on specific topics or lab scenarios.
- **Practice:** Hands-on practice (e.g., using Cisco Packet Tracer or real devices) is essential to master these commands.
- **Configuration Mode:** Many commands require entering the appropriate mode, such as `configure terminal` for global configuration.
- **CCNA vs. CCNP Encor:** CCNA focuses on basic switching and routing (e.g., VLANs, static routes, OSPF, EIGRP), while CCNP Encor introduces advanced topics (e.g., BGP, OSPF authentication, EIGRP variance).

---

This README.md serves as a concise reference guide for configuring Cisco switches and routers, tailored to the needs of CCNA and CCNP Encor students.
