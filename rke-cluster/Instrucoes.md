Comando para subir as imangens vagrant

vagrant up



Configurando o IP Fixo das imagens Vagrant

Editar o arquivo interfaces, ao final ele deve estar parecido com o seguinte:

sudo nano /etc/network/interfaces


# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).

source /etc/network/interfaces.d/*

# The loopback network interface

# The primary network interface
allow-hotplug eth0
auto lo
iface lo inet loopback
iface eth0 inet static
address 192.168.0.200
nemask 255.255.255.0
gateway 192.168.0.1
dns-nameserver 4.2.2.1
dns-nameserver 4.2.2.2
dns-nameserver 8.8.8.8
dns-nameserver 208.67.220.220
pre-up sleep 2


executar o comando para atualizar a rede 

sudo systemctl restart networking