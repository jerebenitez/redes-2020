# OSPF with IPv6
To create routers with OSPFv3 and IPv6 configuration it is necessary to execute docker-compose:

```
$ sudo docker-compose build
$ sudo docker-compose up
```

# Para tener webserver
Hay que hacer lo de siempre:
¨¨¨
$ docker exec -ti tp3_webserver_1 bash
# ip r del default
# ip r add default via 192.168.2.12
¨¨¨

Nota: no se puede agregar as-is a command en docker-compose.yml porque después de ejecutarlo se cierra el container (no sé por qué. Agregar && top al final hace que deje de funcionar el proceso)
