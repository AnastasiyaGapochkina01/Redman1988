# Часть 1: Работа с процессами
1) В домашней директории создать директорию web_server_dir
2) В директории web_server_dir создать файл web_server с содержимым
```
#!/bin/bash
LOG_FILE="$HOME/web_server.log"
log_levels=("ERROR" "INFO" "WARNING" "DEBUG")
methods=("GET" "POST" "PUT" "PATCH" "OPTIONS" "DELETE")
echo "Starting web-server on $(hostname)" >> $LOG_FILE
while true
do
  sleep 5
  random_method=${methods[$RANDOM % ${#methods[@]}]}
  random_level=${log_levels[$RANDOM % ${#log_levels[@]}]}
  echo "$(date +"%Y-%d-%m [%H:%M:%S]") $random_level $random_method" >> $LOG_FILE
  sleep 5
done
```
3) Сделать файл web_server исполняемым для всех
4) Выполнить команду ```./web_server &> /dev/null &```
5) Найти id процесса web_server
6) В домашней директории найти файл web_server.log и посмотреть его содержимое
7) В директории /proc найти каталог, который соответствует найденному выше процессу web_server
8) Приостановить процесс web_server (поставить на паузу, а не убить)
9) Вернуть из паузы процесс web_server
10) Убить процесс web_server
11) Запустить следующую команду
```
ping google.com &> /dev/null & ping yandex.ru &> /dev/null & ping microsoft.com &> /dev/null &
```
12) Найти все процессы ping с помощью ps и grep
13) Найти по их id директории в /proc
14) Убить все процессы ping
# Часть 2: Работа с текстом
1) В выводе ```sudo systemctl list-units --type=service``` найти journald.service
2) В файле /proc/vmstat найти значение numa_other
3) В файле /proc/filesystems найти все записи, содержащие ext
4) Из файла /etc/os-release получить значение VERSION_CODENAME и VERSION_ID
5) В директории text_processing создать файл php-fpm.conf с содержимым
```
;;;;;;;;;;;;;;;;;;;;;
; FPM Configuration ;
;;;;;;;;;;;;;;;;;;;;;

; Global Options
[global]

pid = /run/php/php-fpm.pid

error_log = /var/log/php-fpm.log

log_level = notice

daemonize = yes

; syslog.facility = daemon
; syslog.ident = php-fpm

rlimit_files = 1024

;;;;;;;;;;;;;;;;;;
; Pool Definitions ;
;;;;;;;;;;;;;;;;;;

[www]

user = www-data
group = www-data

listen = /var/run/php/php-fpm.sock

listen.owner = www-data
listen.group = www-data
listen.mode = 0660

pm = dynamic
pm.max_children = 50
pm.start_servers = 5
pm.min_spare_servers = 5
pm.max_spare_servers = 10
pm.process_idle_timeout = 10s;

pm.max_requests = 500

php_admin_value[error_log] = /var/log/php-fpm/www-error.log
php_admin_flag[log_errors] = on

php_value[memory_limit] = 128M
php_value[max_execution_time] = 30

php_admin_value[disable_functions] = exec,passthru,shell_exec,system
```
6) В файле php-fpm.conf найти пользователя и группу
7) В файле php-fpm.conf найти значение listen
8) В файле php-fpm.conf найти куда пишется error_log
