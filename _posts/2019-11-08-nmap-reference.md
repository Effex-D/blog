---
title: "NMAP Reference"
date: 2019-11-08
author: Effex
tags: []
---

1. nmap -sP <target>: Simple ping scan to check host availability without port scanning.
2. nmap -F <target>: Fast scan of the 100 most common ports for a quick vulnerability assessment.
3. nmap -sV <target>: Service version scan to determine the version of services running on each port, great for OS and app fingerprinting.
4. nmap -A <target>: Aggressive scan combining OS detection, version detection, script scanning, and traceroute.
5. nmap -sn <target>: ICMP ping scan to discover hosts without port scanning.
6. nmap -sT <target>: TCP connect scan to check if ports are open by completing the 3-way handshake.
7. nmap -sU <target>: UDP scan to find open UDP ports, useful for services like DNS and SNMP.
8. nmap -p- <target>: Scan all ports (1-65535) on a target for comprehensive port scanning.
9. nmap -O <target>: Enable OS detection to determine the operating system running on the target host.
10. nmap -sS <target>: SYN scan to send SYN packets and analyze the responses to determine open ports.
11. nmap -sX <target>: XMAS scan to send TCP packets with the FIN, PSH, and URG flags set, useful for firewall evasion.
12. nmap -sC <target>: Scan with default scripts enabled to perform advanced vulnerability scanning and service detection.
13. nmap -v <target>: Verbose output to provide more detailed information during the scan.
14. nmap -T<0-5> <target>: Settiming template for the scan (higher is faster but less reliable).
15. nmap -iL <file>: Read targets from a file to perform scans.

Further reading: "Nmap Network Scanning" by Gordon "Fyodor" Lyon
