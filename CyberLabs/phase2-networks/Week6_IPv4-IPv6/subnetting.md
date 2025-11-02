# Week 6 – IPv4 / IPv6 Deep Dive

## 🎯 Objective
Understand IP addressing, subnetting, and IPv6 fundamentals.

## 🔹 IPv4 Concepts
- Structure: 32-bit address, 4 octets.
- CIDR notation (Classless Inter-Domain Routing).
- Subnet mask and prefix length.
- Calculating number of hosts and subnets.

### ExampleNetwork: 192.168.10.0/26
Subnet mask: 255.255.255.192
Host range: 192.168.10.1 – 192.168.10.62
Broadcast: 192.168.10.63
Total hosts: 62

---

## 🔹 IPv6 Concepts
- 128-bit addresses, written in hexadecimal.
- Abbreviation rules (:: for zero blocks).
- Dual-stack systems (IPv4 + IPv6 coexistence).
- Basic commands:
   ip -6 addr
  ping6 google.com
  
---

## 🧠 Key Learning
- Subnetting in binary and CIDR.
- Network planning (allocating IP ranges).
- Transition to IPv6 addressing.

---

## 🧩 Tools Used
- ipcalc — for subnet calculations.
- ping / ping6
- ifconfig / ip addr

---

## 📸 Screenshots
Place IPv4 and IPv6 screenshots here.
