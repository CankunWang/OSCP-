```dataview
TABLE service as "服务", syntax as "常用语法", risk as "风险等级"
FROM "Labs/THM" OR "Enumeration"
WHERE cmd_type = "Recon"
SORT service ASC
```
