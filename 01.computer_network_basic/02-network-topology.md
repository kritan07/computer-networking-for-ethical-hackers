# Network Topology

> **Network topology** is the arrangement of devices (**nodes**) and connections (**links**) in a computer network.

It describes **how devices are connected** and, in a logical topology, **how data travels between them**.

Choosing the right topology is important because it affects:

- **Performance**
- **Cost**
- **Reliability**
- **Scalability**
- **Security**
- **Ease of maintenance**

---

## 📌 Types of Network Topology

Network topology can be classified into two main categories:

### 1. Physical Topology

**Physical topology** describes the actual physical arrangement of network devices, cables, switches, routers, and other components.

Common physical topologies include:

- Point-to-Point
- Bus
- Star
- Ring
- Mesh
- Tree
- Hybrid

### 2. Logical Topology

**Logical topology** describes **how data flows through a network**, regardless of the physical arrangement of devices.

Examples include:

- **Ethernet** — traditional shared-media Ethernet used **CSMA/CD**
- **Token-passing networks** — use a token to control access to the network

> **💡 Important:** A network can have one physical topology and a different logical topology.

---

# 1. Point-to-Point Topology

**Point-to-Point (P2P) topology** is the simplest type of network topology. It provides a **direct connection between two devices**.

One device communicates directly with the other through a dedicated link.

### 📷 Diagram

![Point-to-Point Topology](images/point-point-topology.jpg)

### 🔑 Key Features

- Connects exactly **two devices**
- Uses a **dedicated communication link**
- Provides direct communication
- Commonly used for **dedicated links and WAN connections**

### Advantages

- Simple to install and configure
- High performance because the connection is dedicated
- Low chance of collisions
- Easy to troubleshoot
- Good privacy compared with shared links

### Limitations

- Connects only two devices
- Not suitable for large networks by itself
- Adding more devices requires additional links
- Failure of the link interrupts communication

---

# 2. Mesh Topology

In a **Mesh topology**, devices are connected through multiple links.

In a **Full Mesh**, every device has a dedicated connection to every other device.

A **Partial Mesh** connects only some devices directly, reducing cost while still providing redundancy.

### 📷 Diagram

![Mesh Topology](images/mesh-topology.jpg)

## 🔢 Full Mesh Formula

If `N` devices are connected in a full mesh:

- **Links per device:** `N - 1`
- **Total links:** `N × (N - 1) / 2`
- **Total interfaces/ports:** `N × (N - 1)`

### Example

If there are **6 devices**:

- Links per device = `6 - 1 = 5`
- Total links = `6 × 5 / 2 = 15`
- Total interfaces = `6 × 5 = 30`

### Advantages

- Very high reliability
- Multiple paths are available
- Failure of one link does not necessarily stop communication
- Faults can be easier to isolate
- Provides excellent redundancy
- Suitable for critical networks

### Limitations

- Expensive to install
- Requires a large amount of cabling
- Configuration can be complex
- Maintenance becomes difficult as the network grows
- Full mesh is impractical for very large networks

> **💡 Example:** Partial-mesh designs are commonly used in network backbones and environments where redundancy is important.

---

# 3. Star Topology

In a **Star topology**, all devices are connected to a **central networking device**, such as a switch or, in older networks, a hub.

The central device manages communication between connected devices.

### 📷 Diagram

![Star Topology](images/star-topology.jpg)

## 🔢 Formula

If `N` devices are connected to a central device:

- **Links required:** `N`
- **Central device ports required:** `N`

### 🔑 Key Features

- All devices connect to a central device
- Each device has its own connection to the center
- Very common in modern **LANs**

### Advantages

- Easy to install and manage
- Easy to identify and isolate faults
- Failure of one cable usually affects only one device
- Easy to add or remove devices
- Good performance with modern switches
- Easy to expand

### Limitations

- Failure of the central switch can affect the entire network
- Requires more cable than a bus topology
- Requires a central networking device
- Installation cost can be higher than a simple bus network

> **💡 Example:** Most modern office and home Ethernet networks use a **star topology**, with devices connected to a central switch or router.

---

# 4. Bus Topology

In a **Bus topology**, all devices share a **single main communication cable**, known as the **backbone**.

Devices communicate over the same shared medium.

### 📷 Diagram

![Bus Topology](images/bus-topology.jpg)

## 🔢 Structure

For a traditional bus network with `N` devices:

- **Main backbone cable:** `1`
- **Connections to the backbone:** Approximately `N`

### 🔑 Key Features

- Uses a shared backbone
- All devices share the same communication medium
- Traditional bus Ethernet requires **terminators**
- Traditional shared Ethernet used **CSMA/CD**

### Advantages

- Requires less cable than many other topologies
- Simple design
- Relatively inexpensive for small networks
- Easy to understand

### Limitations

- Failure of the backbone can affect the entire network
- Performance decreases as traffic increases
- Collisions can occur on shared-media Ethernet
- Troubleshooting can be difficult
- Limited scalability
- Difficult to expand compared with modern switched networks
- Security is weaker because devices share the same medium

> **💡 Note:** Bus topology was common in older Ethernet networks using coaxial cable. Modern Ethernet LANs generally use **star or extended-star topologies** with switches.

---

# 5. Ring Topology

In a **Ring topology**, each device is connected to **two neighboring devices**, forming a closed loop.

Data travels around the ring according to the network's communication method.

### 📷 Diagram

![Ring Topology](images/ring-topology.jpg)

## ⚙️ How It Works

In traditional **token-passing networks**:

1. A special frame called a **token** circulates around the ring.
2. A device must obtain the token before transmitting.
3. The device sends its data.
4. After transmission, the token continues around the ring.
5. Other devices get an opportunity to transmit.

### 🔄 Direction of Data

A ring can operate:

- **Unidirectionally** — data travels in one direction
- **Bidirectionally** — data can travel in both directions

A **Dual Ring** uses two separate rings to provide two paths.

### Advantages

- Predictable access to the network
- Low chance of collisions in token-based systems
- Can provide consistent performance
- Organized data transmission

### Limitations

- Failure of a device or link can disrupt a traditional ring
- Troubleshooting can be difficult
- Adding or removing devices may interrupt the network
- Less common in modern LANs

> **💡 Note:** Modern networks often use redundant designs instead of a simple physical ring.

---

# 6. Tree Topology

**Tree topology** is a hierarchical network structure that combines characteristics of **star and bus topologies**.

Devices are organized into multiple levels, creating a structure similar to a tree.

### 📷 Diagram

![Tree Topology](images/tree-topology.jpg)

## 🌳 Structure

A typical tree topology contains:

- **Root/Core device**
- **Distribution devices**
- **Access devices**
- **End devices**

Data can travel between higher and lower levels of the hierarchy.

### 🔑 Key Features

- Hierarchical structure
- Easy to divide a large network into sections
- Supports network expansion
- Common in large organizational networks

> **⚠️ Note:** Protocols such as **DHCP** are not defining features of tree topology. Tree topology describes the **network structure**, while protocols define how communication works.

### Advantages

- Supports many devices
- Easy to organize large networks
- Network sections can be managed independently
- Easier to expand than a simple bus network
- Provides structured network management

### Limitations

- Failure of an important upper-level device or link can affect many devices
- Requires more cables and networking equipment
- Configuration can become complex
- Installation and maintenance can be expensive

> **💡 Example:** A large organization may use a hierarchical structure where a core network connects distribution switches, which connect access switches and end devices.

---

# 7. Hybrid Topology

**Hybrid topology** is a combination of **two or more different network topologies**.

For example, a network might combine:

- Star + Bus
- Star + Ring
- Star + Mesh

### 📷 Diagram

![Hybrid Topology](images/hybrid-topology.jpg)

### 🔑 Key Features

- Combines multiple topology types
- Flexible network design
- Suitable for large and complex networks
- Can be designed according to specific requirements

### Advantages

- Highly flexible
- Easy to expand
- Can be designed according to network requirements
- Can combine the advantages of different topologies
- Suitable for large organizations

### Limitations

- More expensive to design and install
- Network architecture can be complex
- Requires more networking equipment
- Troubleshooting can be difficult
- Maintenance costs can be high

> **💡 Example:** A university campus may use a combination of **star and mesh designs**, with different buildings connected using different network structures.

---

# 📊 Network Topology Comparison

| Topology | Main Structure | Reliability | Cost | Scalability |
|---|---|---|---|---|
| **Point-to-Point** | Two devices directly connected | High | Low | Low |
| **Bus** | Shared backbone | Low | Low | Low |
| **Star** | Devices connected to a central device | High | Medium | High |
| **Ring** | Devices form a closed loop | Medium | Medium | Medium |
| **Mesh** | Multiple connections between devices | Very High | High | Low–Medium |
| **Tree** | Hierarchical structure | Medium–High | Medium–High | High |
| **Hybrid** | Combination of topologies | Depends on design | High | Very High |

---

# 🎯 Why Is Network Topology Important?

Network topology determines **how devices are connected and how communication is organized**.

## 1. 🚀 Network Performance

Topology affects:

- Data transfer speed
- Network congestion
- Latency
- Overall network efficiency

## 2. 🛡️ Network Reliability

Some topologies provide redundancy.

For example, **Mesh topology** can provide multiple paths, so a single link failure does not necessarily stop communication.

## 3. 📈 Network Scalability

A suitable topology makes it easier to:

- Add new devices
- Expand the network
- Connect new departments or locations
- Upgrade network infrastructure

## 4. 💰 Cost

Topology affects the amount of:

- Cable required
- Networking equipment required
- Installation work
- Maintenance required

## 5. 🔒 Network Security

The network structure can affect how devices communicate and how security controls are implemented.

For example, a properly designed switched network can provide better control and segmentation than a shared-medium network.

## 6. 🔧 Troubleshooting & Maintenance

A well-designed topology makes it easier to:

- Find failed devices
- Locate damaged links
- Isolate network problems
- Maintain the network

---

# 🧠 Quick Revision

| Topology | Remember It As |
|---|---|
| **Point-to-Point** | 🔗 Two devices directly connected |
| **Bus** | 🚌 One shared backbone |
| **Star** | ⭐ Everything connects to the center |
| **Ring** | 🔄 Devices form a loop |
| **Mesh** | 🕸️ Multiple connections between devices |
| **Tree** | 🌳 Hierarchical structure |
| **Hybrid** | 🔀 Combination of topologies |

---

## 📌 Key Takeaway

> **Network topology defines how devices are connected and how communication is organized.**

Understanding topology helps you understand:

**Devices → Connections → Data Flow → Performance → Reliability → Security**
