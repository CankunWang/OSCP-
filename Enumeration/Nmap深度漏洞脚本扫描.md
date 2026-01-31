---
cmd_type: Recon
service: Vulnerability-Scan
tags: cmd
syntax: "nmap -Pn -p <PORTS> --script vuln <IP>"
risk: Medium
---
对目标进行通用漏洞脚本扫描，时间需求长，且中等概率触发WAF告警