# OSPF with IPv6
To create routers with OSPFv3 and IPv6 configuration it is necessary to execute docker-compose:

```
$ sudo docker-compose build
$ sudo docker-compose up
```

# Para que haya ping
Se modificó el archivo docker compose para que añada los comandos en cada servicio de host.
Entonces se añaden solas las configuraciónes de default gateway de los hosts.

Se dejó un remanente de los intentos, que probableme habría que borrar.
Los remanentes son: los volumenes hXX_netorks y la linea gateway en las networks del docker-compose.yml

