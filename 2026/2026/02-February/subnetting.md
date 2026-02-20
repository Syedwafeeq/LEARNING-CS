# 🌐 Subnetting — Beginner Friendly Complete Guide

📅 Date: 2026-02  
📚 Category: Network Fundamentals  
🎯 Focus: Understanding IPv4 Subnetting  

---

# 1️⃣ What is Subnetting?

Subnetting is the process of dividing one large network into smaller networks called **subnets** (short for "sub-networks").

A network is a group of devices (computers, phones, servers, routers) that can communicate with each other.

Subnetting helps organize and manage these devices efficiently.

---

## Why Do We Use Subnetting?

- To use IP addresses efficiently  
- To reduce network congestion (too much traffic)  
- To improve security by separating networks  
- To make troubleshooting easier  

---

# 2️⃣ What is an IP Address?

An **IP address (Internet Protocol address)** is a unique number assigned to every device on a network.

IPv4 (Internet Protocol version 4) addresses:

- Are 32 bits long  
- Are divided into 4 sections called **octets**  
- Each octet contains 8 bits  

Example:


192.168.1.10


Each octet can have a value from 0 to 255.

---

## What is a Bit?

A **bit** (binary digit) is the smallest unit of data in computing.

It can only be:


0 or 1


Example of IP in binary:


192.168.1.10
11000000.10101000.00000001.00001010


Binary is the language computers understand.

---

# 3️⃣ Network Portion vs Host Portion

Every IP address has two parts:


[ Network Portion | Host Portion ]


### Network Portion
Identifies which network the device belongs to.

### Host Portion
Identifies the specific device inside that network.

---

# 4️⃣ What is a Subnet Mask?

A **subnet mask** is a number that tells us which part of the IP address is the network and which part is the host.

Example:


IP Address: 192.168.1.10
Subnet Mask: 255.255.255.0


This means:

- 192.168.1 → Network
- .10 → Host

---

# 5️⃣ What is CIDR?

**CIDR (Classless Inter-Domain Routing)** is a modern way of writing subnet masks.

Instead of writing:


255.255.255.0


We write:


/24


The number after "/" tells how many bits are used for the network.

Example:


192.168.1.0/24


- 24 bits = Network
- 8 bits = Host (because 32 - 24 = 8)

---

# 6️⃣ Important Subnetting Formula

If:


Host bits = h


Then:


Total addresses = 2^h
Usable hosts = 2^h - 2


Why minus 2?

Because:

1. One address is reserved as the **Network Address**
2. One address is reserved as the **Broadcast Address**

---

## What is a Network Address?

The first address in a subnet.  
It identifies the subnet itself.  
It cannot be assigned to a device.

## What is a Broadcast Address?

The last address in a subnet.  
It sends data to all devices in that subnet.  
It cannot be assigned to a device.

---

# 7️⃣ Common Subnet Masks

| CIDR | Subnet Mask | Usable Hosts |
|------|-------------|--------------|
| /24 | 255.255.255.0 | 254 |
| /25 | 255.255.255.128 | 126 |
| /26 | 255.255.255.192 | 62 |
| /27 | 255.255.255.224 | 30 |
| /28 | 255.255.255.240 | 14 |
| /29 | 255.255.255.248 | 6 |
| /30 | 255.255.255.252 | 2 |

---

# 8️⃣ How to Calculate Block Size (Easy Method)

Block size helps us find subnet ranges quickly.

Formula:


256 - Last number in subnet mask


Example:

Mask:


255.255.255.192


Calculation:


256 - 192 = 64


So subnet numbers increase by 64:


0, 64, 128, 192


---

# 9️⃣ Step-by-Step Example

Divide:


192.168.1.0/24


Into 4 subnets.

Step 1:

4 subnets = 2²  
So we borrow 2 bits.

New CIDR:


/26


New Subnet Mask:


255.255.255.192


Block size:


64


Subnets:

| Subnet | Usable Range | Broadcast |
|--------|-------------|------------|
| 192.168.1.0 | .1 – .62 | .63 |
| 192.168.1.64 | .65 – .126 | .127 |
| 192.168.1.128 | .129 – .190 | .191 |
| 192.168.1.192 | .193 – .254 | .255 |

---

# 🔟 What is VLSM?

**VLSM (Variable Length Subnet Mask)** means using different subnet sizes depending on need.

Example:

- One department needs 100 devices  
- Another needs 10 devices  

Instead of making equal subnets, we adjust sizes.

This prevents wasting IP addresses.

---

# 1️⃣1️⃣ Private IP Address Ranges

Private IP addresses are used inside local networks (like homes or offices).

They are not used directly on the internet.

| Range | CIDR |
|-------|------|
| 10.0.0.0 – 10.255.255.255 | /8 |
| 172.16.0.0 – 172.31.255.255 | /12 |
| 192.168.0.0 – 192.168.255.255 | /16 |

---

# 1️⃣2️⃣ Special IP Addresses

| Type | Example | Meaning |
|------|----------|----------|
| Network Address | 192.168.1.0 | Identifies subnet |
| Broadcast Address | 192.168.1.255 | Sends to all devices |
| Loopback | 127.0.0.1 | Tests your own computer |
| APIPA | 169.254.x.x | Automatic IP if DHCP fails |

---

## What is DHCP?

**DHCP (Dynamic Host Configuration Protocol)** is a system that automatically assigns IP addresses to devices.

---

# 1️⃣3️⃣ Why Subnetting is Important in Cybersecurity

Subnetting helps in:

- Defining scanning scope (example: using tools like Nmap)  
- Creating secure network segments  
- Setting firewall rules  
- Detecting suspicious traffic  
- Performing penetration testing  

Without subnet knowledge, network security becomes difficult.

---

# ✅ Final Summary

Subnetting becomes easy when:

- You understand CIDR  
- You remember the formula  
- You know how to calculate block size  
- You practice examples  

It is one of the most important foundations in networking and cybersecurity.
