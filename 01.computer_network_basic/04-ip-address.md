

## Introduction

An **IP address** is one of the most important concepts in computer networking.

Every device that communicates over an IP network needs an address so that data can be delivered to the correct destination.


---

# 1. What Is an IP Address?

**IP** stands for **Internet Protocol**.

An IP address is a logical address assigned to a device or network interface so that it can communicate using the Internet Protocol.

Think of an IP address like a **postal address**.

If you want to send a letter to someone, you need their address.

Similarly, when one computer sends data to another computer, the network needs an address to know where the data should go.

### Simple Example

```text
Computer A
IP: 192.168.1.10

        |
        | Data
        v

Computer B
IP: 192.168.1.20
```

Computer A can send data to Computer B using its IP address.

---

# 2. Why Do We Need IP Addresses?

Networks can contain thousands or millions of devices.

The network needs a way to identify:

* Where data comes from
* Where data should go
* Which network a device belongs to
* Which device should receive the data

An IP address provides logical addressing for IP communication.

### Example

Suppose you open a website:

```text
Your Computer
     |
     v
   Router
     |
     v
   Internet
     |
     v
Web Server
```

Your computer sends network packets toward the server.

The packets contain source and destination addressing information so that routers can forward them toward the correct destination.

---

# 3. IP Address vs MAC Address

IP addresses and MAC addresses are different.

## IP Address

An IP address is a **logical address** used by the Internet Protocol.

Example:

```text
192.168.1.10
```

## MAC Address

A MAC address is a **link-layer address** associated with a network interface.

Example:

```text
00:1A:2B:3C:4D:5E
```

### Simple Difference

```text
IP Address
    |
    +-- Logical addressing
    +-- Used for routing between networks
    +-- Can change

MAC Address
    |
    +-- Link-layer addressing
    +-- Used for local network communication
    +-- Usually associated with a network interface
```

Do not confuse an IP address with a MAC address.

---

# 4. Versions of IP

There are two major versions of the Internet Protocol in common use:

1. IPv4
2. IPv6

IPv4 is older and still extremely common.

IPv6 was developed to provide a much larger address space and additional improvements.

---

# 5. IPv4

IPv4 stands for **Internet Protocol version 4**.

IPv4 uses **32 bits** for an IP address.

An IPv4 address is normally written as four decimal numbers separated by dots.

Example:

```text
192.168.1.10
```

Each number is called an **octet**.

```text
192 . 168 . 1 . 10
  |     |    |    |
Octet Octet Octet Octet
```

Each octet contains 8 bits.

Therefore:

```text
8 + 8 + 8 + 8 = 32 bits
```

---

# 6. IPv4 Range

Each IPv4 octet can contain a value from:

```text
0 to 255
```

Therefore, a valid IPv4 address can look like:

```text
10.0.0.1
172.16.5.20
192.168.1.100
8.8.8.8
```

An address such as this is invalid:

```text
192.168.1.300
```

because `300` is outside the valid octet range.

---

# 7. IPv4 Address Structure

An IPv4 address can be divided into two conceptual parts:

```text
Network Portion + Host Portion
```

The **network portion** identifies the network.

The **host portion** identifies an address within that network.

Exactly where the division occurs depends on the subnet mask or CIDR prefix.

### Example

```text
IP Address:
192.168.1.10

Subnet Mask:
255.255.255.0
```

This corresponds to:

```text
192.168.1.0/24
```

Here, `/24` indicates that the first 24 bits are the network prefix.

---

# 8. CIDR Notation

CIDR stands for **Classless Inter-Domain Routing**.

CIDR notation represents an IP address together with its network prefix length.

Example:

```text
192.168.1.10/24
```

The `/24` means:

```text
24 bits = network prefix
8 bits  = remaining address bits
```

Because IPv4 has 32 bits:

```text
32 - 24 = 8
```

So there are 8 bits remaining after the prefix.

---

# 9. IPv6

IPv6 stands for **Internet Protocol version 6**.

IPv6 uses **128 bits** for an address.

Example:

```text
2001:db8:1234:5678::1
```

IPv6 addresses use hexadecimal notation and are separated into groups using colons.

### IPv6 Example

```text
2001:db8:1234:5678:0000:0000:0000:0001
```

This can be shortened to:

```text
2001:db8:1234:5678::1
```

---

# 10. Why Was IPv6 Created?

IPv4 provides approximately:

```text
2^32
```

possible addresses.

That is about:

```text
4.3 billion
```

addresses.

This may sound like a huge number, but the Internet contains a massive number of devices.

IPv6 uses 128-bit addresses:

```text
2^128
```

This provides an enormously larger address space.

### Main Reason

One of the major reasons IPv6 was developed was to provide a much larger address space than IPv4.

---

# 11. IPv4 vs IPv6

| Feature           | IPv4           | IPv6                       |
| ----------------- | -------------- | -------------------------- |
| Address size      | 32 bits        | 128 bits                   |
| Example           | `192.168.1.10` | `2001:db8::1`              |
| Notation          | Decimal        | Hexadecimal                |
| Separator         | Dot `.`        | Colon `:`                  |
| Address space     | Smaller        | Extremely large            |
| NAT commonly used | Yes            | Less central to addressing |

IPv4 and IPv6 can operate on networks today, and many networks use both.

---

# 12. Public IP Address

A **public IP address** is an address that can be used for communication across the public Internet.

For example, a router connected to an Internet service provider may have a public IPv4 address.

A public IP address can allow Internet services to identify the network endpoint from which traffic is coming.

### Important

A public IP address does not automatically mean that a device is directly reachable from the Internet.

Firewalls, NAT, routing, and other security controls can affect reachability.

---

# 13. Private IP Address

Private IPv4 addresses are intended for use inside private networks.

The main private IPv4 ranges are:

```text
10.0.0.0/8
```

```text
172.16.0.0/12
```

```text
192.168.0.0/16
```

Examples:

```text
10.0.0.5
172.16.10.20
192.168.1.100
```

These addresses are not globally routable on the public Internet.

---

# 14. Public IP vs Private IP

| Public IP                        | Private IP                                  |
| -------------------------------- | ------------------------------------------- |
| Used on public networks          | Used inside private networks                |
| Globally unique within its scope | Can be reused in different private networks |
| Can be Internet-routable         | Not directly Internet-routable              |
| Often assigned by an ISP         | Often assigned by a router or DHCP server   |

### Example Home Network

```text
              Internet
                  |
          Public IP Address
                  |
               Router
             /       \
            /         \
   192.168.1.10    192.168.1.20
     Laptop          Phone
```

The laptop and phone can use private IP addresses inside the home network while the router communicates with the Internet using an external address.

---

# 15. Static IP Address

A **static IP address** is an address that is intentionally configured to remain stable.

Static addressing can be useful for systems that need a predictable address.

Examples:

* Servers
* Network infrastructure
* Some printers
* Security appliances
* Certain network services

Example:

```text
Server
192.168.1.50
```

The administrator may configure the server to consistently use that address.

---

# 16. Dynamic IP Address

A **dynamic IP address** is assigned automatically, commonly using **DHCP**.

DHCP stands for:

**Dynamic Host Configuration Protocol**

A DHCP server can provide devices with network configuration such as:

* IP address
* Subnet mask or prefix
* Default gateway
* DNS server information

### Example

```text
Laptop
   |
   | DHCP request
   v
DHCP Server
   |
   | IP configuration
   v
192.168.1.25
```

---

# 17. Static vs Dynamic IP

| Static                              | Dynamic                        |
| ----------------------------------- | ------------------------------ |
| Manually or deliberately configured | Usually assigned automatically |
| Predictable                         | May change                     |
| Useful for servers                  | Common for client devices      |
| Requires administration             | Easier for large networks      |

---

# 18. Loopback Address

A **loopback address** refers to the local host itself.

For IPv4, the commonly used loopback address is:

```text
127.0.0.1
```

The loopback range is:

```text
127.0.0.0/8
```

For IPv6, the loopback address is:

```text
::1
```

### Example

When you connect to:

```text
127.0.0.1
```

you are communicating with the local machine rather than another device on the network.

Loopback addresses are commonly used for:

* Testing
* Local development
* Running local services
* Troubleshooting

---

# 19. Default Gateway

A **default gateway** is the router or next-hop device that a host uses when it needs to send traffic outside its local network.

Example:

```text
Laptop
192.168.1.10
     |
     v
Router
192.168.1.1
     |
     v
Internet
```

The laptop may use:

```text
192.168.1.1
```

as its default gateway.

If the destination is outside the local network, the laptop sends the packet toward the default gateway.

---

# 20. DNS and IP Addresses

Humans usually prefer names instead of remembering IP addresses.

For example:

```text
example.com
```

can resolve to an IP address through the **Domain Name System (DNS)**.

Conceptually:

```text
You
 |
 | example.com
 v
DNS Server
 |
 | IP address
 v
Web Server
```

DNS and IP addressing work together, but they are different systems.

### DNS

Translates domain names into IP information.

### IP

Provides addressing for IP communication.

---

# 21. Unicast

**Unicast** means one sender communicates with one destination.

Example:

```text
Computer A
     |
     |-------> Computer B
```

This is the most common communication pattern on IP networks.

---

# 22. Broadcast

A **broadcast** is communication intended for all applicable hosts on a local IPv4 broadcast domain.

For example, an IPv4 subnet can have a broadcast address.

For:

```text
192.168.1.0/24
```

the traditional directed broadcast address is:

```text
192.168.1.255
```

Broadcast traffic is generally limited to the local network and is not routed across the Internet in the normal way.

IPv6 does not use broadcast; it uses multicast instead.

---

# 23. Multicast

**Multicast** allows a sender to send traffic to a group of interested receivers.

Conceptually:

```text
             +---- Computer A
             |
Sender ------+---- Computer B
             |
             +---- Computer C
```

Multicast can be useful for applications where multiple devices need the same data.

IPv4 multicast addresses are in:

```text
224.0.0.0/4
```

---

# 24. Anycast

**Anycast** allows the same address to be used by multiple network locations.

Network routing can direct traffic to an appropriate or nearby instance.

Conceptually:

```text
             +---- Server A
             |
Client ------+---- Server B
             |
             +---- Server C
```

The client uses the same destination address, while routing determines which instance receives the traffic.

Anycast is widely used in large-scale Internet services.

---

# 25. Network Address Translation (NAT)

**NAT** stands for **Network Address Translation**.

NAT allows a network device, commonly a router, to translate addresses between different addressing domains.

A common home-network example is:

```text
Private Network
192.168.1.10
192.168.1.20
192.168.1.30
       |
       v
     Router
       |
       v
Public Network
```

Multiple private devices can share an external IPv4 address using NAT, often together with port translation.

---

# 26. Why Is NAT Commonly Used?

One major reason NAT became widespread is IPv4 address conservation.

For example, a home may have many devices:

```text
Laptop
Phone
Tablet
TV
Game Console
IoT Devices
```

These devices can use private IPv4 addresses internally while sharing an external IPv4 address through the router.

---

# 27. How a Router Uses IP Addresses

Routers examine packet information and use routing information to determine where to forward packets.

Example:

```text
Computer
192.168.1.10
     |
     v
Router
     |
     +------> Network A
     |
     +------> Network B
     |
     +------> Internet
```

The router compares the destination address with its routing table and selects an appropriate next hop or outgoing interface.

---

# 28. Routing Table

A router maintains a **routing table**.

A simplified routing table might look like:

```text
Destination       Next Hop
192.168.1.0/24    Local
10.0.0.0/8        Router A
0.0.0.0/0         ISP Router
```

The route:

```text
0.0.0.0/0
```

is commonly called the **default route** for IPv4.

It is used when no more specific route matches the destination.

---

# 29. IP Packet

When data is sent using IP, it is carried in an IP packet.

An IPv4 packet contains important information such as:

```text
Source IP Address
Destination IP Address
Protocol
TTL
Payload
```

The exact header contains additional fields.

### Example

```text
+---------------------------+
| Source IP                 |
+---------------------------+
| Destination IP            |
+---------------------------+
| Other IP Header Fields    |
+---------------------------+
| Payload                   |
+---------------------------+
```

The destination IP address helps routers determine where the packet should go.

---

# 30. TTL

TTL stands for **Time To Live** in IPv4.

TTL is a field in the IPv4 header that limits how many router hops a packet can make.

Each router normally decreases the TTL.

If the TTL reaches zero, the packet is discarded.

This helps prevent packets from circulating indefinitely because of routing loops.

IPv6 uses a similar field called **Hop Limit**.

---

# 31. IP Address Does Not Mean Physical Location

An IP address should not be treated as an exact physical location.

An IP address may provide information about a network or approximate geographic region, depending on the address and available databases.

It normally does **not** reveal someone's exact home address by itself.

Internet service providers and organizations may have additional information that is not contained in the IP address itself.

---

# 32. How to Find Your IP Address

## Windows

Open Command Prompt and run:

```bash
ipconfig
```

For more detailed information:

```bash
ipconfig /all
```

Look for the network adapter and its IPv4 or IPv6 configuration.

---

## Linux

You can use:

```bash
ip address
```

or:

```bash
ip addr
```

To inspect routing information:

```bash
ip route
```

---

## macOS

You can inspect network settings through the system settings or use commands such as:

```bash
ifconfig
```

---

# 33. Local IP vs Public IP

When you run:

```bash
ipconfig
```

on a typical home computer, you may see a private address such as:

```text
192.168.1.10
```

That is your local/private address.

Your Internet connection may use a different external address at the router or ISP level.

Conceptually:

```text
Your Computer
192.168.1.10
      |
      v
Home Router
External Address
      |
      v
Internet
```

---

# 34. IP Address and Cybersecurity

Understanding IP addresses is extremely important in cybersecurity.

Security professionals use IP addressing when analyzing:

* Network traffic
* Firewalls
* Logs
* Intrusion attempts
* Servers
* Network connections
* Malware traffic
* Security incidents
* Network scanning
* Access control

For example, a security analyst may see a log entry such as:

```text
Source: 203.0.113.50
Destination: 192.168.1.10
Port: 22
Protocol: TCP
```

The analyst can investigate what the connection means and whether it is expected or suspicious.

---

# 35. IP Spoofing

**IP spoofing** is when an attacker manipulates the source IP information in network packets so that the packets appear to come from another address.

Conceptually:

```text
Attacker
   |
   | Fake Source IP
   v
Target
```

IP spoofing does not necessarily mean the attacker has control over the device whose IP address is being impersonated.

It is important to understand that the source IP field alone is not always reliable proof of who actually sent traffic.

---

# 36. IP Scanning

Security professionals and attackers may scan IP addresses to discover systems and services.

For example, a network might contain:

```text
192.168.1.10
192.168.1.11
192.168.1.12
192.168.1.13
```

A security assessment may determine:

* Which hosts are active
* Which ports are open
* Which services are exposed
* Which systems need security improvements

Scanning should only be performed on systems and networks where you have permission.

---

# 37. IP Address in Firewall Rules

Firewalls can use IP addresses as part of access-control rules.

For example:

```text
Allow:
192.168.1.0/24

Deny:
203.0.113.50
```

A firewall may also use:

* Source IP
* Destination IP
* Port
* Protocol
* Connection state
* Application information

IP addresses are therefore an important part of network security controls.

---

# 38. IP Address and Logs

Security logs frequently contain IP addresses.

Example:

```text
2026-09-06 10:15:20
Source IP: 203.0.113.50
Destination: Web Server
Port: 443
Protocol: TCP
```

An analyst can use these records to investigate network activity.

However, an IP address alone does not automatically identify a specific person.

Addresses can be shared, translated through NAT, dynamically assigned, or otherwise associated with different users over time.

---

# 39. Common IP Address Mistakes

### Mistake 1: Thinking IP and MAC are the same

They are different types of addresses used at different networking layers.

### Mistake 2: Thinking every IP is public

Many devices use private IP addresses.

### Mistake 3: Thinking an IP always identifies a person

An IP address identifies a network endpoint or interface at a particular point in time and context. It does not automatically identify an individual.

### Mistake 4: Thinking IP addresses never change

Dynamic addresses can change.

### Mistake 5: Thinking IPv4 and IPv6 are the same

They are different versions of the Internet Protocol with different address formats and sizes.

---

# 40. Quick Summary

An **IP address** is a logical address used for communication over IP networks.

The two major versions are:

```text
IPv4
32-bit address
Example: 192.168.1.10
```

```text
IPv6
128-bit address
Example: 2001:db8::1
```

IPv4 private address ranges include:

```text
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
```

