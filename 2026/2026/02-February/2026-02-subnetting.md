# 🌐 Subnetting — Complete Guide

📅 Date: 2026-02-20  
📚 Category: Network Fundamentals  
🎯 Focus: IPv4 Subnetting  

---

## 📌 What is Subnetting?

Subnetting is the process of dividing a large IP network into smaller logical networks (subnets).

### Why Subnet?

- Efficient IP usage  
- Reduced broadcast traffic  
- Better security segmentation  
- Easier network management  

---

## 🌍 IPv4 Basics

An IPv4 address:

- 32 bits  
- 4 octets  
- Each octet = 8 bits  

Example:

```

192.168.1.10

```

Binary:

```

11000000.10101000.00000001.00001010

```

Each octet ranges from 0–255.

---

## 🧩 Network vs Host

Every IP address has two parts:

```

[ Network Portion | Host Portion ]

```

The subnet mask decides the split.

Example:

```

IP:   192.168.1.10
Mask: 255.255.255.0

```

Network: 192.168.1  
Host: .10  

---

## 📐 Subnet Mask & CIDR

CIDR = Classless Inter-Domain Routing  

Example:

```

192.168.1.0/24

```

- 24 bits → Network  
- 8 bits → Host  

---

### Common Subnet Masks

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

## 🧮 Important Formulas

If host bits = h:

```

Total addresses = 2^h
Usable hosts = 2^h - 2

```

Why minus 2?

- Network address  
- Broadcast address  

If subnet bits = s:

```

Number of subnets = 2^s

```

---

## ⚡ Block Size (Fast Method)

Formula:

```

256 - Last Non-255 Octet

```

Example:

Mask: 255.255.255.192  

```

256 - 192 = 64

```

Subnets increase by 64:

```

0, 64, 128, 192

```

---

## 🛠 Example: Divide 192.168.1.0/24 into 4 Subnets

4 subnets = 2² → Borrow 2 bits  

New CIDR:

```

/26

```

New Mask:

```

255.255.255.192

```

Block size:

```

64

```

| Subnet | Usable Range | Broadcast |
|--------|-------------|------------|
| 192.168.1.0 | .1 – .62 | .63 |
| 192.168.1.64 | .65 – .126 | .127 |
| 192.168.1.128 | .129 – .190 | .191 |
| 192.168.1.192 | .193 – .254 | .255 |

---

## 🔀 FLSM vs VLSM

| FLSM | VLSM |
|------|------|
| Equal subnet sizes | Variable subnet sizes |
| Wastes IPs | Efficient |
| Old method | Modern method |

---

## 🏠 Private IP Ranges

| Range | CIDR |
|-------|------|
| 10.0.0.0 – 10.255.255.255 | /8 |
| 172.16.0.0 – 172.31.255.255 | /12 |
| 192.168.0.0 – 192.168.255.255 | /16 |

---

## 📡 Special Addresses

| Type | Example | Purpose |
|------|----------|----------|
| Network | 192.168.1.0 | Identifies subnet |
| Broadcast | 192.168.1.255 | Sends to all hosts |
| Loopback | 127.0.0.1 | Self testing |
| APIPA | 169.254.x.x | Auto assigned IP |

---

## 🔢 Binary Reference Table

| Value |
|-------|
| 128 |
| 64 |
| 32 |
| 16 |
| 8 |
| 4 |
| 2 |
| 1 |

Example:

224 = 128 + 64 + 32  
Binary:

```

11100000

```

---

## 🔗 /30, /31, /32 Explained

| CIDR | Usage |
|------|--------|
| /30 | Point-to-point links |
| /31 | Router-to-router |
| /32 | Single host |

---

## 🛡 Why Subnetting Matters in Cybersecurity

Subnetting is essential for:

- Network scanning
- Recon scope identification
- Firewall rules
- Network segmentation
- IDS/IPS configuration
- Pivoting during penetration testing

---

## 🧠 Memory Table

| CIDR | Hosts |
|------|--------|
| /25 | 126 |
| /26 | 62 |
| /27 | 30 |
| /28 | 14 |
| /29 | 6 |
| /30 | 2 |

---

## ✍️ Summary

Subnetting becomes easy once:

- CIDR is understood  
- Block size is memorized  
- Binary values are comfortable  

It is a foundational skill for networking and cybersecurity.
```
