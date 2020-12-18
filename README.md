# Herramientas SRI
## [Plantillas DHCP](plantillasFicherosDHCP)
## [Plantillas DNS](PlantillasDNS)
### Nftables
**Habilitar forwarding paquetes ipv4 --> vim /etc/sysctl.conf  línea 28 descomentar**

`sysctl -p (reinicia)`

`apt install nftables`

`nft add rule ip nat postrouting oifname "enp0s3" ip saddr 192.168.3.0/24 counter masquerade || nft list ruleset > /etc/nftables.conf`

`sysctl -p`

`nft list tables_chains_rules`

`nft add table nat`

`nft add chain nat prerouting {type nat hook prerouting priority 0 ; }`

`nft add chain nat postrouting {type nat hook postrouting priority 100 ; }ip`

`nft add rule ip nat postrouting oifname "enp0s3" ip saddr 192.168.3.0/24 counter masquerade || nft list ruleset > /etc/nftables.conf`
