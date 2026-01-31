---
cmd_type: Recon
service: General
protocol: TCP
tags: cmd
syntax: "nmap -Pn -sV -sC -p <PORTS> <IP> -oN nmap_detailed"
---
目标忽略ICMP时，对特定开放端口所运行的服务进行扫描，同时使用默认安全脚本