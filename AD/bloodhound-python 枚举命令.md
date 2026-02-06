---
os: linux
service: AD
syntax: bloodhound-python -u 'SUSANNA_MCKNIGHT' -p 'CHANGEME2023!' -d 'thm.local' -dc 'labyrinth.thm.local' -ns 10.82.181.185 --disable-autogc -c All --zip
---
在获得一个初始凭据后，可以用bloodHound进行下一步完整枚举
