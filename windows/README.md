#### Установка и настройка
mkdir c:\zabbix\win64


    LogFile=c:\zabbix\win64\zabbix_agentd.log
    Server=192.168.0.21                        
    ServerActive=192.168.0.21
    Hostname=hostname
#### Настройка firewall
    Netsh Advfirewall Firewall Add Rule name="Zabbix" dir=in action=allow description="Zabbix" profile=any localport=10050 protocol=tcp

Скрипты для управления в папке scripts
