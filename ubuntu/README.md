### Установка
#### получаем из репозитория последнюю версию zabbix-agent (в данном случае 3.4)
sudo wget http://repo.zabbix.com/zabbix/3.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_3.4-1+xenial_all.deb
sudo dpkg -i zabbix-release_3.4-1+xenial_all.deb
sudo apt-get update
#### устанавливаем агент
sudo apt install zabbix-agent
#### настраиваем конфиг файл   /etc/zabbix/zabbix_agentd.conf
LogFileSize=10
Server=192.168.1.109
ServerActive=192.168.1.1
Hostname=system.hostname
#### перезапускаем агент 
sudo /etc/init.d/zabbix-agent restart
#### добавляем узел сети в своем zabbix-server
