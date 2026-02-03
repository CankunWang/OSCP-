---
syntax:
os: linux
---
# 确认是否处于容器内部
ls -la /.dockerenv
ps -ef  # 查看pid=1的进程，如果不是system等进程，大概率处于容器
cat /proc/1/cgroup # 检查是否包含docker等字符
# 确认目标环境有哪些sql
php -m | egrep -i 'mysqli|pdo|mysql|sqlite|pgsql'

