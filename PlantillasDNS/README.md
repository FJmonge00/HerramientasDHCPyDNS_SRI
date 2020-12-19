# Herramientas SRI
## Rutas y Comandos Importantes

`/etc/resolv.conf`

`apt install bind9`

`/etc/default/bind9`

`/etc/nsswitch.conf`

`/etc/nsswitch.conf`

`/etc/bind/named.conf.local`

`named-checkconf named.conf.local`

`/etc/bind/db.fp211.org`

` sudo named-checkzone fp211.org db.fp211.org`

`dig @192.168.3.1 google.es`

`dig @192.168.3.1 servidor`

`dig @192.168.3.1 192.168.3.11`

`dig @192.168.3.1 192.168.3.12`

`dig google.es +noall +stats`

`nslookup gooogle.es`

`nslookup servidor`

## (SI NO PODEMOS RESOLVER DOMINIOS DE INTERNET):

`ping 1.1.1.1` 

**Si no salimos a internet con la IP comprobar las reglas de FIREWALL**

### Nftables
**Habilitar forwarding paquetes ipv4 --> vim /etc/sysctl.conf  línea 28 descomentar**

`sysctl -p (reinicia)`

`apt install nftables`

`nft add rule ip nat postrouting oifname "enp0s3" ip saddr 192.168.3.0/24 counter masquerade || nft list ruleset > /etc/nftables.conf`

`sysctl -p`

`nft list tables_chains_rules`

`nft add table nat`

`nft add chain nat prerouting {type nat hook prerouting priority 0 ; }`

`nft add chain nat postrouting {type nat hook postrouting priority 100 \; }ip`

`nft add rule ip nat postrouting oifname "enp0s3" ip saddr 192.168.3.0/24 counter masquerade || nft list ruleset > /etc/nftables.conf`