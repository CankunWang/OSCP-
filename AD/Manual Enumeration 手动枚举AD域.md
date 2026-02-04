
whoami /all    # 输出用户SID, group members 以及用户权限
hostname      # 列出所在机器的主机名，大概率可以验证所在主机是目标域的什么角色
systeminfo     # 几乎所有的详细信息，但是需要权限
set                  # 列出所有的变量， 如果是windows系统，使用dir env:
net                 # net系列命令可以枚举所在域的其他用户
net user /domain      # 列出所有在域内的用户
net user <username> /domain # 列出目标用户的全名，账户状态，信息等
net group /domain   # 列出所有的组
net localgroup <groupname># 列出所有目标组内的用户
query user或者quser # 列出登录过机器的用户
tasklist /v # 列出当前的进程
net session # 列出SMB进程，需要权限
wmic service get   #获取服务的信息
wmic service get Name,StartName #需要权限运行，同样的用处，不过可以显示特定的行
sc query state=all # 返回所有的windows里的服务，需要权限运行
reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon" /v keyword # 访问自动登录的凭据
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall # 访问已下载软件信息


whoami /priv  #列出所拥有的权限,权限如下

- **SeImpersonatePrivilege**: As mentioned already, this privilege allows a process to impersonate the security context of another user after authentication. The “potato” attack revolves around abusing this privilege.
- 
- **SeAssignPrimaryTokenPrivilege**: This privilege permits a process to assign the primary token of another user to a new process. It is used in conjunction with the SeImpersonatePrivilege privilege.
- 
- **SeBackupPrivilege**: This privilege lets users read any file on the system, ignoring file permissions. Consequently, attackers can use it to dump sensitive files like the SAM or SYSTEM hive.
- 
- **SeRestorePrivilege**: This privilege grants the ability to write to any file or registry key without adhering to the set file permissions. Hence, it can be abused to overwrite critical system files or registry settings.
- 
- **SeDebugPrivilege**: This privilege allows the account to attach a debugger to any process. As a result, the attacker can use this privilege to dump memory from LSASS and extract credentials or even inject malicious code into privileged processes.

