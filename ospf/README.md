# OSPF with IPv6
To create routers with OSPFv3 and IPv6 configuration it is necessary to execute docker-compose:

```
$ sudo docker-compose up
```

# Para que haya ping
1. Tenes que entrar en algún host de la red 192.168.2.0 (h1-3) y cambiar el default gateway con
```
$ sudo docker exec -ti ospf_h1_1 ash
# ip route del default
# ip route add default via 192.168.2.12
```
2. Repetí lo mismo para el host 4 con
```
$ sudo docker exec -ti ospf_h4_1 ash
# ip route del default
# ip route add default via 192.168.7.14
```

Eso debería darte ping entre los hosts 1 y 4. Si hacés lo mismo para los hosts 2, 3 y 5 (que debería tener por dg 192.168.6.15) tendría que haber ping entre todos.

Hay que buscar la forma de hacer que esta config sea persistente. Meti algo en el docker-compose.yml que leí [acá](https://docs.docker.com/compose/compose-file/compose-file-v2/#ipv4_address-ipv6_address), pero me sigue tomando el default gateway por defecto.
