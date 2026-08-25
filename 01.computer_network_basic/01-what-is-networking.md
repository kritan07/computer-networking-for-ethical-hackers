# Introduction to Computer Networking: The Ethical Hacker's Foundation

---

**Computer networking** is the process of connecting computers, servers, and other devices so they can communicate and exchange data with each other. It allows devices to share resources such as **files, applications, printers, and Internet connections**.

Networks can range from a small **personal network** to a massive global network such as the **Internet**.

Understanding computer networking is a fundamental skill for **IT professionals, system administrators, network engineers, cloud engineers, and cybersecurity professionals**. 

For an **ethical hacker**, networking is your **battlefield**. You cannot defend or test what you do not understand. Before you can find vulnerabilities, you must understand:

- **Where the data lives** (LANs, servers).
- **How data travels** (WANs, the Internet).
- **Where the boundaries are** (Where does one network end and another begin?).

---

<p align="center">
  <img src="../images/computer_networking01.png" alt="Computer Networking" width="100%">
</p>

---

## Network Types Based on Size

Computer networks are commonly classified based on their **geographical coverage and size**.

The four major types of networks are:

| Type | Full Form | Coverage | Hacker's Interest Level |
|------|-----------|----------|-------------------------|
| **PAN** | Personal Area Network | Personal space | Low (Physical proximity needed) |
| **LAN** | Local Area Network | Home, office, building | **High** (The primary target) |
| **MAN** | Metropolitan Area Network | City or metropolitan area | Medium (ISP/Backbone focus) |
| **WAN** | Wide Area Network | Country or worldwide | High (The Internet itself) |

---

# 1. PAN — Personal Area Network

## Definition

A **Personal Area Network (PAN)** is a small network used to connect personal devices within a short range, usually around an individual.

PAN allows devices such as **smartphones, laptops, smartwatches, wireless headphones, and tablets** to communicate and share data.

## How PAN Works

PAN commonly uses technologies such as:

- **Bluetooth**
- **USB**
- **Wi-Fi** (Wi-Fi Direct)
- **Infrared** (obsolete)

These technologies allow personal devices to communicate over a short distance (typically up to 10 meters).

<p align="center">
  <img src="../images/pan.jpg" alt="PAN Network Diagram" width="100%">
</p>

## Example

When you connect your **smartphone to wireless earbuds using Bluetooth**, you are creating a simple PAN.

Another example is connecting a smartphone to a laptop using Bluetooth to transfer files.

## Key Characteristics

- Covers a **very small area** (a few meters).
- Usually centered around **one person**.
- Uses technologies such as **Bluetooth and USB**.
- Designed for **personal devices**.
- Usually has a short communication range.

### 🧠 Hacker's Mindset

> **Why a hacker cares:** PANs are **personal** and require **physical proximity** to attack. An ethical hacker usually does not target PANs during a remote penetration test. However, PANs are a major concern for **physical security testing** and **social engineering**.
>
> **Key Concern:** Bluetooth vulnerabilities (like **BlueBorne** or **KNOB** attacks) can allow an attacker to take over a smartphone just by being nearby. For an ethical hacker, PANs represent a **"bridge"** from the personal world to the corporate world—if an employee connects their compromised personal phone (PAN) to the office Wi-Fi (LAN), the attacker can "jump" networks.

---

# 2. LAN — Local Area Network

## Definition

A **Local Area Network (LAN)** is a computer network that connects multiple devices within a **limited geographical area**, such as a home, office, school, computer lab, or building.

The main purpose of a LAN is to allow connected devices to **communicate and share resources**.

## How LAN Works

In a LAN, devices can be connected using **Ethernet cables or Wi-Fi**.

Network devices such as **switches, routers, and wireless access points** help manage communication between connected devices.

<p align="center">
  <img src="../images/lan.webp" alt="LAN Network Diagram" width="100%">
</p>

## Example

A company may have multiple computers, printers, servers, and other devices connected to the same LAN.

Employees can access shared files, communicate with servers, and use shared printers through the network.

## Key Characteristics

- Covers a **small geographical area** (building, office, campus).
- Provides **high-speed communication** (1 Gbps to 10 Gbps and beyond).
- Uses **Ethernet or Wi-Fi**.
- Allows **resource sharing** (files, printers, applications).
- Usually managed by a **single organization or individual**.
- Offers **low latency** (fast response times).

### 🧠 Hacker's Mindset

> **Why a hacker cares:** The LAN is the **primary target** for ethical hackers. This is where the "crown jewels" live—file servers, databases, domain controllers, and employee workstations.
>
> **Key Concerns:**
> 1.  **Internal Sniffing:** Because LANs use broadcast protocols (like ARP), an attacker who gains access to a LAN can often see and intercept traffic between other devices.
> 2.  **Weak Segmentation:** Many LANs are "flat"—meaning once you are inside, you can reach almost every other device. This is a huge security risk.
> 3.  **Wi-Fi as an Entry Point:** Wireless LANs (WLANs) broadcast signals outside the building. An attacker can attempt to crack Wi-Fi passwords from the parking lot to gain entry to the LAN.
>
> **The Hacker's Goal:** A successful LAN compromise means **lateral movement**—the ability to jump from one computer to another until the attacker reaches the most valuable systems (like the Domain Controller).

---

# 3. MAN — Metropolitan Area Network

## Definition

A **Metropolitan Area Network (MAN)** is a computer network designed to connect multiple **LANs (Local Area Networks)** across a **city or metropolitan area**.

A MAN is **larger than a LAN but smaller than a WAN**.

## How MAN Works

A MAN connects multiple LANs using high-speed communication technologies such as **fiber-optic cables, microwave links, or other high-speed connections**.

<p align="center">
  <img src="../images/man.webp" alt="MAN Network Diagram" width="100%">
</p>

## Example

Suppose a university has several buildings located across a city. Each building has its own LAN.

A **MAN can connect these LANs**, allowing users and systems in different buildings to communicate and share resources.

Another example is a **city-wide public Wi-Fi project** or a **cable television network** that also provides internet access across a city.

## Key Characteristics

- Covers a **city or metropolitan area**.
- Larger than a **LAN**.
- Smaller than a **WAN**.
- Connects **multiple LANs**.
- Often uses **high-speed communication technologies** (fiber optics, microwave).
- Can be operated by organizations or telecommunications providers.

### 🧠 Hacker's Mindset

> **Why a hacker cares:** MANs are the **connective tissue** between different locations of the same organization. If an organization has multiple buildings, they often connect them via a MAN (using leased fiber lines). 
>
> **Key Concerns:**
> 1.  **Backbone Exposure:** The links between buildings are often less monitored than the internal LANs. An attacker might try to intercept traffic on these links.
> 2.  **ISP Involvement:** MANs often rely on Internet Service Providers (ISPs). If the ISP is compromised, the organization's MAN traffic can be intercepted.
> 3.  **VPNs:** Many MANs use encrypted VPN tunnels over the internet. If an ethical hacker finds a misconfigured VPN, they might be able to bypass the MAN's security and access all connected LANs.
>
> **The Hacker's Goal:** For an ethical hacker, MANs represent a **pivot point**. If you can compromise the connection between two branches, you can potentially access both LANs from a single entry point.

---

# 4. WAN — Wide Area Network

## Definition

A **Wide Area Network (WAN)** is a computer network that connects multiple networks across a **large geographical area**, such as countries, continents, or even the entire world.

WANs are used to connect **LANs and MANs** located in different geographical locations.

## How WAN Works

WANs use various communication technologies, including:

- **Fiber-optic connections** (Undersea cables)
- **Leased lines** (Dedicated circuits from ISPs)
- **Satellite communication**
- **Microwave links**
- **Cellular networks** (4G/5G)
- **The Internet** (The largest WAN)

<p align="center">
  <img src="../images/wan.jpg" alt="WAN Network Diagram" width="100%">
</p>

## Example

A multinational company may have offices in **Nepal, India, the United States, and the United Kingdom**.

Each office has its own LAN. A WAN can connect these different networks so employees and systems in different countries can communicate and access shared resources.

The **Internet** is the largest example of a WAN.

## Key Characteristics

- Covers a **large geographical area**.
- Can connect networks across **countries and continents**.
- Connects multiple **LANs and MANs**.
- Uses technologies such as **fiber, satellite, leased lines, and cellular networks**.
- Usually involves multiple network providers or organizations.
- Typically has **higher latency** and **lower speed** compared to LANs.
- Often uses **routers** to forward data between different networks.

### 🧠 Hacker's Mindset

> **Why a hacker cares:** WANs are the **global battlefield**. The Internet itself is a massive WAN, and it is the primary attack surface for remote ethical hackers.
>
> **Key Concerns:**
> 1.  **The Internet is Untrusted:** By design, the Internet is an open, public network. An ethical hacker's job is to protect an organization's internal LANs from the "wild west" of the Internet.
> 2.  **Perimeter Security:** The WAN represents the "outside." Firewalls, routers, and intrusion prevention systems sit at the boundary between the LAN (trusted) and the WAN (untrusted). Ethical hackers test these boundaries to ensure they cannot be bypassed.
> 3.  **Cloud and Remote Workers:** Modern networks often use WAN connections to connect to cloud providers (like AWS, Azure) and remote workers (via VPNs). These connections expand the attack surface.
>
> **The Hacker's Goal:** An attacker typically starts by scanning public-facing WAN addresses (IPs on the Internet) to find open ports and vulnerable services. Once they find a weakness (e.g., an unpatched web server), they breach the perimeter and try to move into the internal LAN.

---

# Comparison of PAN, LAN, MAN, and WAN (With Hacker Context)

| Feature | PAN | LAN | MAN | WAN |
|---------|-----|-----|-----|-----|
| **Full Form** | Personal Area Network | Local Area Network | Metropolitan Area Network | Wide Area Network |
| **Coverage** | Personal space | Building / local area | City | Country / worldwide |
| **Size** | Very small | Small | Medium | Very large |
| **Typical Range** | A few meters | Up to several kilometers | Several to tens of kilometers | Hundreds to thousands of kilometers |
| **Common Technologies** | Bluetooth, USB | Ethernet, Wi-Fi | Fiber, microwave | Fiber, satellite, leased lines, Internet |
| **Example** | Phone + smartwatch | Office network | City-wide university network | The Internet |
| **Hacker's Focus** | Physical proximity attacks | **Primary target** (Internal networks) | ISP/Backbone exploitation | **Perimeter attacks** (External entry) |
| **Security Concern** | Bluetooth vulnerabilities | Flat networks, ARP spoofing, Wi-Fi cracking | Unencrypted backbone links | DDoS, phishing, VPN misconfigurations |

---

# Network Size Overview

```text
PAN  →  LAN  →  MAN  →  WAN
 ↓       ↓       ↓       ↓
Very    Small   City    Large
Small           Area    Area
(1-10m) (100m-1km) (5-50km) (Global)

Hacker's Focus:
PAN:  Physical proximity
LAN:  Internal lateral movement
MAN:  Inter-branch communication
WAN:  External perimeter breach
