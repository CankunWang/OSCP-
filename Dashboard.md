#  Pentest Operations Dashboard

## 进度 (THM/HTB)
```dataview
TABLE 
    Status as "状态", 
    OS as "系统", 
    ip as "IP地址",
    Start_Time as "启动时间"
FROM "Labs" 
WHERE Status != null
SORT Start_Time DESC
```

```dataview
TABLE 
    syntax as "执行命令", 
    risk as "风险指数"
FROM #cmd 
WHERE cmd_type = "Recon" OR cmd_type = "Exploit"
SORT service ASC
```

```dataview
TABLE service, syntax
FROM #cmd
WHERE contains(service, "") 
SORT service ASC
```

```
