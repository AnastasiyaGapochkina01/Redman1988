1) В домашней директории создать директорию text_processing
2) В директории text_processing создать файл products с содержимым
```
Handle:Title:SKU:Location:On hand:Available:Count
product-1:Product A:PROD-A:Warehouse A:100
product-1:Product A:PROD-A:Warehouse A:50
product-2:Product B:PROD-B:Warehouse B:200
product-2:Product B:PROD-B:Warehouse B:150
product-3:Product C:PROD-C:Warehouse C:300
product-4:Product D:PROD-D:Warehouse A:400
product-4:Product D:PROD-D:Warehouse A:250
product-5:Product E:PROD-E:Warehouse B:500
product-5:Product E:PROD-E:Warehouse B:300
product-6:Product F:PROD-F:Warehouse C:600
product-6:Product F:PROD-F:Warehouse C:400
```
3) Найти в файле products все строки, содержащие  PROD-C
4) Найти в файле products все строки, содержащие слово product-3 и вывести для них значение Count
5) Найти в файле products все строки, у которых столбец Available равен C и для них вывести значения Handle и Count
6) В директории text_processing создать файл hosts с содержимым
```
hostname,interval,timestamp,%user,%system,%memory
sel-srv1,600,2023-10-08 00:00:01 UTC,30.01,20.77,96.21
sel-srv1,600,2023-10-08 00:05:01 UTC,40.07,13.00,84.55
sel-srv1,600,2023-10-08 00:10:01 UTC,5.00,90.55,89.23
sel-srv2,600,2023-10-09 00:15:01 UTC,25.01,15.77,92.21
sel-srv3,600,2023-10-09 00:20:01 UTC,35.07,10.00,80.55
sel-srv3,600,2023-10-09 00:25:01 UTC,10.00,85.55,88.23
sel-srv2,600,2023-10-09 00:30:01 UTC,20.01,25.77,95.21
sel-srv2,600,2023-10-09 00:35:01 UTC,45.07,12.00,82.55
sel-srv3,600,2023-10-09 00:40:01 UTC,15.00,80.55,87.23
```
7) Найти в файле hosts строки, содержащие sel-srv2 и вывести значение timestamp
8) Найти в файле hosts строки, содержащие дату 2023-10-08
9)  В директории text_processing создать файл inventory с содержимым
```
[Compute1]
IP_Address = 192.168.1.100
Location = Datacenter A
Service_Name = Web Server

[Compute2]
IP_Address = 192.168.1.101
Location = Datacenter B
Service_Name = Database Server

[Compute3]
IP_Address = 192.168.1.102
Location = Datacenter C
Service_Name = Application Server

[Compute4]
IP_Address = 192.168.1.103
Location = Datacenter A
Service_Name = File Server

[Compute5]
IP_Address = 192.168.1.104
Location = Datacenter B
Service_Name = Mail Server
```
9) Найти в файле inventory все сервисы, которые относятся к Datacenter B
10) СНайти в файле inventory все хосты, которые относятся к Datacenter C и вывести только их ip
11) Отфильровать вывод команды lscpu так, чтобы получить значение CPU MHz
12) Отфильровать вывод команды lscpu так, чтобы получить значение Hypervisor vendor
13) Из файла /proc/meminfo получить все строки. относящиеся к HugePages
14) Отфильтровать вывод команды free -h так, чтобы получить размер Swap
15) Из файла /etc/group вывести названия групп и их id (3 поле)
16) В директории text_processing создать файл logs с содержимым
```
# Cron logs
Oct 20 06:24:01 server1 CRON[1349677]: (user1) CMD (   /usr/bin/python3 /home/user1/update.py)
Oct 20 06:25:01 server3 CRON[1349678]: (user2) CMD (   /usr/bin/python3 /home/user2/report.py)
Oct 20 06:26:01 server2 CRON[1349679]: (root) CMD (   /usr/bin/cleanup.sh)
Oct 20 06:27:01 server3 CRON[1349680]: (user3) CMD (   /usr/bin/backup.sh)
Oct 20 06:28:01 server1 CRON[1349681]: (user4) CMD (   /usr/bin/monitor.sh)

# Error logs
Oct 20 06:30:00 server1 sshd[12345]: Failed password for invalid user admin from 192.168.0.10 port 22 ssh2
Oct 20 06:31:00 server3 sshd[12346]: Failed password for invalid user guest from 192.168.0.11 port 22 ssh2
Oct 20 06:32:00 server1 sshd[12347]: Accepted password for user2 from 192.168.0.12 port 22 ssh2
Oct 20 06:33:00 server1 sshd[12348]: Failed password for invalid user test from 192.168.0.13 port 22 ssh2

# Warning logs
Oct 20 06:35:00 server1 kernel: [123456] Warning! CPU temperature is high.
Oct 21 09:10:00 server2 kernel: [123458] Warning! High CPU usage detected on process ID 5678.
Oct 21 09:11:00 server2 systemd[1]: Warning! Service myservice.service is taking too long to start.
Oct 21 09:12:00 server2 sshd[23461]: Warning! Multiple failed login attempts from 192.168.0.25.
Oct 21 09:13:00 server2 application[34571]: Warning! Disk space on /home is below 10% remaining.

# Info logs
Oct 21 09:02:00 server2 application[34569]: INFO User1 logged in successfully.
Oct 21 09:03:00 server2 application[34570]: INFO User3 logged out.
Oct 21 09:14:00 server2 application[34572]: INFO User4 logged in successfully from 192.168.0.26.
Oct 21 09:15:00 server2 application[34573]: INFO Backup completed successfully at /backup/user4_backup.tar.gz.
Oct 21 09:16:00 server2 systemd[1]: INFO Service myservice.service started successfully.
Oct 21 09:17:00 server2 sshd[23462]: INFO User1 logged out from session on terminal pts/0.
```
17) В файле logs найти все записи, которые содержат application
18) В файле logs найти записи о запусках cron на сервере server3 и вывести команду, которая запускалась
19) В файле logs найти записи о неудачных попытках входа в систему и вывести имена пользователей от имени которых происходил вход
20) Из вывода команды df -Th получить файловые системы с типом ext4
21) Из вывода команды lscpu получить значение Vendor ID
22) В директории text_processing создать файл iptables.log с содержимым
```
Nov  6 08:15:30 firewall kernel: [12345.678901] iptables: IN=eth0 OUT= MAC=00:11:22:33:44:55:66:77:88:99:aa:bb:cc:dd SRC=203.0.113.10 DST=192.168.1.100 LEN=40 TOS=0x00 PREC=0x00 TTL=235 ID=54321 PROTO=TCP SPT=45678 DPT=80 WINDOW=1024 RES=0x00 SYN URGP=0
Nov  6 08:15:35 firewall kernel: [12345.789012] iptables: IN=eth0 OUT= MAC=00:11:22:33:44:55:66:77:88:99:aa:bb:cc:dd SRC=10.0.0.5 DST=192.168.1.1 LEN=52 TOS=0x00 PREC=0x00 TTL=64 ID=12345 PROTO=TCP SPT=56789 DPT=22 WINDOW=64240 RES=0x00 SYN URGP=0
Nov  6 08:15:40 firewall kernel: [UFW BLOCK] iptables: IN=eth0 OUT= MAC=00:11:22:33:44:55:66:77:88:99:aa:bb:cc:dd SRC=192.168.1.50 DST=8.8.8.8 LEN=84 TOS=0x00 PREC=0x00 TTL=64 ID=0 DF PROTO=UDP SPT=54321 DPT=53 LEN=64
Nov  6 08:15:45 firewall kernel: [UFW BLOCK] iptables: IN=eth0 OUT= MAC=00:11:22:33:44:55:66:77:88:99:aa:bb:cc:dd SRC=203.0.113.20 DST=192.168.1.100 LEN=40 TOS=0x00 PREC=0x00 TTL=235 ID=54322 PROTO=TCP SPT=45679 DPT=443 WINDOW=1024 RES=0x00 SYN URGP=0
Nov  6 08:15:50 firewall kernel: [12346.012345] iptables: IN=eth0 OUT= MAC=00:11:22:33:44:55:66:77:88:99:aa:bb:cc:dd SRC=192.168.1.101 DST=192.168.1.1 LEN=60 TOS=0x00 PREC=0x00 TTL=64 ID=38282 DF PROTO=ICMP TYPE=8 CODE=0 ID=1234 SEQ=1
Nov  6 08:15:55 firewall kernel: [12346.123456] iptables: IN=eth0 OUT= MAC=00:11:22:33:44:55:66:77:88:99:aa:bb:cc:dd SRC=10.0.0.10 DST=192.168.1.100 LEN=52 TOS=0x00 PREC=0x00 TTL=127 ID=25588 DF PROTO=TCP SPT=49206 DPT=3389 WINDOW=8192 RES=0x00 SYN URGP=0
Nov  6 10:35:22 firewall kernel: [UFW BLOCK] IN=eth0 OUT= MAC=00:11:22:33:44:55:66:77:88:99:aa:bb:cc:dd SRC=203.0.113.20 DST=192.168.1.1 LEN=40 TOS=0x00 PREC=0x00 TTL=249 ID=54321 PROTO=TCP SPT=45678 DPT=22 WINDOW=1024 RES=0x00 SYN URGP=0
```
23) В файле iptables.log найти записи, которые содержат "_UFW BLOCK_" и вывести только ip адрес источника
24) Получить из вывода команды lscpu количество ядер (CPU(s))
25) В выводе команды ```dpkg --list``` найти cron и curl и вывести название пакета и его версию
26) Из вывода команды ```dpkg-architecture``` получить значение переменных DEB_HOST_ARCH и DEB_TARGET_GNU_CPU
27) Из вывода команды ```locale``` вывести значение LC_MESSAGES
28) Из вывода команды ```lslocks``` вывести PID и PATH
