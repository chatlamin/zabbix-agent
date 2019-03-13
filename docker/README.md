# Zabbix Agent в Docker контейнере

    docker run -d \
      --restart=always \
      --name zabbix-agent \
      -p 10050:10050 \
      -v /proc:/host/proc:ro \
      -v /sys:/host/sys:ro \
      -v /dev:/host/dev:ro \
      -v /etc:/host/etc:ro \
      -v /var/run/docker.sock:/host/var/run/docker.sock \
      --env ZABBIX_SERVER=192.168.0.21 \
      --env HOST=hostname \
      digiapulssi/docker-zabbix-agent

[Источник](https://github.com/digiapulssi/docker-zabbix-agent)