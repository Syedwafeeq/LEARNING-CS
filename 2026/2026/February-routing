Static routing is a fundamental networking concept in the CCNA curriculum. It involves manually configuring routes on a router to direct traffic toward specific networks.

---

# 📌 What is Static Routing?

A **static route** is a route that is manually configured by a network administrator.

It tells the router:

> "To reach this network, forward packets to this next-hop IP address or exit interface."

Static routes do NOT update automatically.

---

# 🎯 Why Use Static Routing?

## ✅ Advantages

- Simple to configure
- Predictable behavior
- No routing protocol overhead
- Lower CPU and memory usage
- More secure (no routing advertisements)
- Ideal for small or stub networks

## ❌ Disadvantages

- Not scalable
- Manual maintenance required
- No automatic failover (unless configured with floating static routes)

---

# 🛠 Basic Static Route Syntax (Cisco IOS)

```
ip route <destination-network> <subnet-mask> <next-hop-ip>
```

### Example

```
ip route 192.168.2.0 255.255.255.0 10.0.0.2
```

Meaning:

To reach `192.168.2.0/24`, forward traffic to `10.0.0.2`.

---

# 🔹 Static Route Using Exit Interface

```
ip route 192.168.2.0 255.255.255.0 GigabitEthernet0/0
```

Typically used in point-to-point links.

---

# 🔹 Fully Specified Static Route

```
ip route 192.168.2.0 255.255.255.0 GigabitEthernet0/0 10.0.0.2
```

Used in multi-access networks to avoid ARP issues.

---

# 🌐 Default Static Route (Gateway of Last Resort)

Used when the router does not have a specific route for a destination.

## Syntax

```
ip route 0.0.0.0 0.0.0.0 <next-hop-ip>
```

### Example

```
ip route 0.0.0.0 0.0.0.0 10.0.0.1
```

This means:

If no matching route exists, send traffic to `10.0.0.1`.

Common in:

- Branch offices
- Edge routers connected to ISP
- Small networks

---

# 🧠 Administrative Distance (AD)

Administrative Distance determines which route is preferred.

| Route Type | AD |
|------------|----|
| Connected  | 0  |
| Static     | 1  |
| OSPF       | 110 |
| RIP        | 120 |

Lower AD = More preferred.

---

# 🔄 Floating Static Route (Backup Route)

Used as a backup to a primary route.

Example:

```
ip route 192.168.2.0 255.255.255.0 10.0.0.3 200
```

AD = 200

This route will only be used if the primary route fails.

---

# 🧩 Host Route

Route to a single device.

```
ip route 192.168.1.10 255.255.255.255 10.0.0.2
```

Subnet mask `255.255.255.255` indicates a single host.

---

# 📊 Verifying Static Routes

Useful commands:

```
show ip route
show ip route static
show running-config
show ip interface brief
ping
traceroute
```

---

# 📌 How Routes Are Selected

Routers use this order:

- Longest Prefix Match
- Lowest Administrative Distance
- Lowest Metric

Example:

- 192.168.1.0/24
- 192.168.1.128/25

The router chooses `/25` because it is more specific.

---

# 🧪 Lab Example

## Topology

R1 ——— R2

R1 LAN: 192.168.1.0/24  
R2 LAN: 192.168.2.0/24  
Link Network: 10.0.0.0/30  

---

## Configuration on R1

```
conf t
ip route 192.168.2.0 255.255.255.0 10.0.0.2
end
```

---

## Configuration on R2

```
conf t
ip route 192.168.1.0 255.255.255.0 10.0.0.1
end
```

---

# 🌍 Static Routing in IPv6

## Syntax

```
ipv6 route <destination-prefix> <next-hop>
```

## Example

```
ipv6 route 2001:DB8:1::/64 2001:DB8:12::2
```

Verify:

```
show ipv6 route
```

---

# 🛑 Common Troubleshooting Issues

| Issue | Possible Cause |
|-------|----------------|
| Destination unreachable | Missing route |
| No connectivity | Wrong next-hop IP |
| Intermittent failure | Interface down |
| One-way traffic | Missing return route |

---

# ⚖ Static vs Dynamic Routing

| Feature | Static | Dynamic |
|----------|--------|---------|
| Configuration | Manual | Automatic |
| CPU Usage | Low | Higher |
| Scalability | Poor | High |
| Updates | No | Yes |
| Best For | Small networks | Large networks |

Dynamic routing examples include OSPF and RIP.

---

# 🚀 Real-World Use Cases

- Branch office to HQ connection
- Stub networks
- ISP edge configuration
- Backup routing path
- Small enterprise networks

---




Happy Networking 🚀
