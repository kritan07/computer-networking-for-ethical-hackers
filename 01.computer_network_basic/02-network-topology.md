# Network Topology

> **Network topology** is the arrangement of devices (**nodes**) and connections (**links**) in a computer network.

It shows how computers, servers, and other devices are connected and how data flows between them.

Choosing the right topology is important because it affects:

- **Performance**
- **Cost**
- **Reliability**
- **Security**

---

## 📌 Types of Network Topology

There are two main types of network topology:

1. **Physical Topology**  
   The actual physical layout of cables and devices.

2. **Logical Topology**  
   How data moves across the network, regardless of the physical layout.

> **Note:** Bus, Star, Mesh, Ring, Tree, and Hybrid are physical topologies. Logical topology refers to how data flows in the network, such as **CSMA/CD** in Ethernet or **token passing** in ring networks.

---

## 1. Point-to-Point Topology

**Point-to-Point Topology** is a type of topology that works on the functionality of the sender and receiver.

It is the simplest communication between two nodes, in which one node is the **sender** and the other node is the **receiver**.

Point-to-Point topology provides **high bandwidth** because the connection is dedicated between two devices.

### 📷 Diagram

![Point-to-Point Topology](images/point-point-topology.jpg)

### ✅ Advantages

- Simple and easy to set up
- High data transfer speed because of the dedicated link
- Secure communication through a direct connection
- Low chances of data collision

### ❌ Disadvantages

- Not suitable for large networks
- Expensive if many devices need connection
- Limited scalability
- Failure of the link disconnects communication

---

## 2. Mesh Topology

In a mesh topology, every device is connected to another device via a dedicated channel. These channels are known as links. Mesh topology does not depend on specific protocols; it focuses on direct device-to-device connections.

### 📷 Diagram

![Mesh Topology](images/mesh-topology.jpg)

### 🔢 Formula

Suppose, `N` number of devices are connected with each other in a mesh topology:

- **Ports required per device:** `N - 1`
- **Total ports required:** `N * (N - 1)`
- **Total dedicated links required:** `N * (N - 1) / 2`

**Example:** In the figure above, there are 6 devices connected to each other:
- Ports per device = `5`
- Total ports required = `6 * 5 = 30`
- Total links required = `6 * 5 / 2 = 15`

### ✅ Advantages

- Communication is very fast between the nodes
- Mesh Topology is robust
- Fault is diagnosed easily
- Data is reliable because data is transferred through dedicated channels
- Provides security and privacy

### ❌ Disadvantages

- Installation and configuration are difficult
- The cost of cables is high as bulk wiring is required
- Suitable for a limited number of devices
- The cost of maintenance is high

> **💡 Note:** A common example of mesh topology is the internet backbone, where various internet service providers are connected to each other via dedicated channels. This topology is also used in military communication systems and aircraft navigation systems.

---

## 3. Star Topology

In Star Topology, all the devices are connected to a single hub through a cable. This hub is the central node and all other nodes are connected to the central node. The hub can be passive in nature (not intelligent, like broadcasting devices) or intelligent (known as an active hub). Active hubs have repeaters in them.

### 📷 Diagram

![Star Topology](images/star-topology.jpg)

### 🔢 Formula

If `N` devices are connected to each other in a star topology:

- **Number of cables required:** `N`
- **Total ports required:** `N`

### ✅ Advantages

- Easy to set up
- Each device requires only one port
- Robust — if one link fails, only that link is affected
- Easy fault identification and isolation
- Cost-effective as it uses inexpensive coaxial cable

### ❌ Disadvantages

- If the hub fails, the whole system crashes
- Cost of installation is high
- Performance depends on the hub

> **💡 Note:** A common example of star topology is a local area network (LAN) in an office where all computers are connected to a central hub. This topology is also used in wireless networks where all devices are connected to a wireless access point.

---

## 4. Bus Topology

Bus Topology is a network type in which every computer and network device is connected to a single cable. It is bi-directional and supports multi-point connections.

### 📷 Diagram

![Bus Topology](images/bus-topology.jpg)

### 🔢 Formula

If `N` devices are connected to each other in a bus topology:

- **Backbone cable required:** `1`
- **Drop lines required:** `N`

### ✅ Advantages

- Coaxial or twisted pair cables are used, supporting up to 10 Mbps
- Less cable cost compared to other topologies
- Familiar technology with well-known installation and troubleshooting techniques
- CSMA/CD is the MAC method used in traditional bus Ethernet

### ❌ Disadvantages

- A lot of cabling is still required
- If the common cable fails, the whole system crashes
- Heavy network traffic increases collisions
- Adding new devices slows down the network
- Security is very low

> **💡 Note:** A common example of bus topology is the Ethernet LAN, where all devices are connected to a single coaxial cable or twisted pair cable. This topology is also used in cable television networks.

---

## 5. Ring Topology

In a Ring Topology, devices are connected in a ring with exactly two neighboring devices. Repeaters are used for networks with a large number of nodes to prevent data loss.

### 📷 Diagram

![Ring Topology](images/ring-topology.jpg)

### ⚙️ Operations

- One station acts as a **monitor station** to perform operations
- To transmit data, a station must hold the **token**
- After transmission, the token is released for other stations
- When no station transmits, the token circulates in the ring

### ✅ Advantages

- High-speed data transmission
- Minimum possibility of collision
- Cheap to install and expand

### ❌ Disadvantages

- Failure of a single node can cause the entire network to fail
- Troubleshooting is difficult
- Less secure

> **💡 Note:** Data flows in one direction, but it can be made bidirectional by having two connections between each node — called **Dual Ring Topology**.

---

## 6. Tree Topology

Tree topology is a variation of Star topology. This topology has a hierarchical flow of data.

### 📷 Diagram

![Tree Topology](images/tree-topology.jpg)

### 🔑 Key Features

- Various secondary hubs are connected to the central hub which contains the repeater
- Data flows from top to bottom (central hub → secondary → devices) or bottom to top
- It is a multi-point connection and a non-robust topology — if the backbone fails, the topology crashes
- Protocols like DHCP and SAC (Standard Automatic Configuration) are used

### ✅ Advantages

- Allows more devices to be attached to a single central hub
- Decreases the distance traveled by the signal to reach devices
- Allows the network to be isolated and prioritized
- New devices can be added to the existing network

### ❌ Disadvantages

- If the central hub fails, the entire system fails
- Cost is high because of the cabling
- Adding new devices makes reconfiguration difficult

> **💡 Note:** A common example of a tree topology is the hierarchy in a large organization. The CEO is the root, connected to different departments (child nodes), managers overseeing teams (grandchild nodes), and team members (leaf nodes) at the bottom.

---

## 7. Hybrid Topology

Hybrid Topology is the combination of various types of topologies. It is used when the nodes are free to take any form — they can be individual topologies like Ring or Star, or a combination of various types.

### 📷 Diagram

![Hybrid Topology](images/hybrid-topology.jpg)

### ✅ Advantages

- Very flexible
- The size of the network can be easily expanded by adding new devices

### ❌ Disadvantages

- Challenging to design the architecture
- Hubs used are very expensive
- Infrastructure cost is very high as it requires a lot of cabling and network devices

> **💡 Note:** A common example of a hybrid topology is a university campus network. The network may have a backbone of a star topology, with each building connected through a switch or router. Within each building, there may be a bus or ring topology connecting different rooms and offices.

---

## 🎯 Important Points

Network Topology is important because it defines how devices are connected and how they communicate in the network:

- **Network Performance:** Choosing the appropriate topology helps in running the network easily and increases network performance.
- **Network Reliability:** Some topologies like Star and Mesh are reliable — if one connection fails, they provide alternatives as backup.
- **Network Expansion:** Choosing the correct topology helps in easier expansion by adding more devices without disrupting the existing network.
- **Network Security:** Understanding how devices are connected helps provide better security to the network.
