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

#### добавляем узел сети в своем zabbix-server
для docker контейнера  digiapulssi/docker-zabbix-agent

    docker run -d \
      --restart=always \
      --name zabbix-agent \
      -p 10050:10050 \
      -v /proc:/host/proc:ro \
      -v /sys:/host/sys:ro \
      -v /dev:/host/dev:ro \
      -v /etc:/host/etc:ro \
      -v /var/run/docker.sock:/host/var/run/docker.sock \
      --env ZABBIX_SERVER=192.168.1.2 \
      --env HOST=hostname \
      digiapulssi/docker-zabbix-agent

[Официальная документация](https://www.zabbix.com/documentation/4.0/ru/manual/installation/install_from_packages/debian_ubuntu)