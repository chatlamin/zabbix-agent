# Zabbix Agent на OS Ubuntu 16.04

## Добавление Zabbix репозитория

    sudo wget https://repo.zabbix.com/zabbix/4.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_4.0-2+xenial_all.deb
    sudo dpkg -i zabbix-release_4.0-2+xenial_all.deb
    sudo apt update

## Установка Zabbix Agent

    sudo apt install zabbix-agent

## Настройка Zabbix Agent

Конфиг-файл находится тут /etc/zabbix/zabbix_agentd.conf

    LogFileSize=10
    Server=192.168.0.21
    ServerActive=192.168.0.21
    Hostname=system.hostname

Перезапускаем агент

    sudo /etc/init.d/zabbix-agent restart

[Официальная документация](https://www.zabbix.com/documentation/4.0/ru/manual/installation/install_from_packages/debian_ubuntu)