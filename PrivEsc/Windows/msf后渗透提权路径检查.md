---
cmd_type: Privilege Escalation Enumeration
service: Metasploit Post-Module
protocol: Meterpreter
tags:
  - tool/msf
  - enum/privesc
  - post/windows
syntax: "run post/multi/recon/local_exploit_suggester"
OS: multi
---

#  MSF 提权漏洞扫描

使用本地漏洞建议模块自动识别可利用的提权路径。

### 🛠️ 执行步骤

**1. 保持 Session 在后台**
#tag/msf/background
在 Meterpreter 会话中按 `Ctrl+Z` 或输入 `background`。

**2. 载入建议模块**
#tag/msf/module
```bash
use post/multi/recon/local_exploit_suggester