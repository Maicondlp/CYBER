#### GERENCIAMENTO DE REDE 

A configuração de IP na estação de trabalho poderá ser feita utilizando o comando:
~~~
ifconfig eth0 IP_DESEJADO netmask MÁSCARA_DESEJADA
~~~

Ou diretamente no arquivo /etc/network/interfaces como o exemplo abaixo:
~~~		
auto eth0
iface eth0 inet static
address IP_DESEJADO
netmask MÁSCARA_DESEJADA
gateway IP_GATEWAY
~~~

Para obter um IP automaticamente deverá ser feita a configuração de DHCP no arquivo /etc/network/interfaces, como o exemplo abaixo:
~~~		
auto eth0
iface eth0 inet dhcp 
~~~		

A configuração de Gateway também poderá ser feita utilizando o comando:
~~~		
route -n
route del default
route add default gw IP_GATEWAY
~~~		

Para reiniciar o serviço de rede utilize:
~~~		
/etc/init.d/networking restart
~~~		

#### MAPEAR VOLUME DO SAMBA
~~~	
mount -t cifs -o username=USUARIO //IP_DO_SERVIDOR/DIRETÓRIO/ /mnt
~~~	
