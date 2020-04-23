
CONTAINER_PREFIX=tp3

setup:
	docker-compose up
clean:
	docker-compose down 

delete_route:
	docker exec -ti $(CONTAINER_PREFIX)_r1_1 ip -6 route del default;
	docker exec -ti $(CONTAINER_PREFIX)_r2_1 ip -6 route del default;
	docker exec -ti $(CONTAINER_PREFIX)_r3_1 ip -6 route del default;
	docker exec -ti $(CONTAINER_PREFIX)_r4_1 ip -6 route del default;
	docker exec -ti $(CONTAINER_PREFIX)_r5_1 ip -6 route del default;
	docker exec -ti $(CONTAINER_PREFIX)_r1_1 ip  route del default;
	docker exec -ti $(CONTAINER_PREFIX)_r2_1 ip  route del default;
	docker exec -ti $(CONTAINER_PREFIX)_r3_1 ip  route del default;
	docker exec -ti $(CONTAINER_PREFIX)_r4_1 ip  route del default;
	docker exec -ti $(CONTAINER_PREFIX)_r5_1 ip  route del default;

default_gw:
	docker exec -ti --privileged $(CONTAINER_PREFIX)_h1_1 route add default gw 172.16.3.12
	docker exec -ti --privileged $(CONTAINER_PREFIX)_h2_1 route add default gw 172.16.4.12
	docker exec -ti --privileged $(CONTAINER_PREFIX)_h3_1 route add default gw 172.16.5.12
	docker exec -ti --privileged $(CONTAINER_PREFIX)_server1_1 route add default gw 172.16.2.12
	docker exec -ti --privileged $(CONTAINER_PREFIX)_server2_1 route add default gw 172.16.2.12
	docker exec -ti --privileged $(CONTAINER_PREFIX)_r2_1 route add default gw 192.168.3.11
	docker exec -ti --privileged $(CONTAINER_PREFIX)_r3_1 route add default gw 192.168.4.11


probar_server_desde_h3:
	docker exec -ti tp3_h3_1  wget -qO - http://172.16.2.15:80
probar_server_desde_h2:
	docker exec -ti tp3_h2_1  wget -qO - http://172.16.2.15:80
probar_server_desde_h1:
	docker exec -ti tp3_h1_1  wget -qO - http://172.16.2.15:80
probar_h1_no_alcanzable:
	docker exec -ti tp3_h3_1  ping 172.16.3.15

