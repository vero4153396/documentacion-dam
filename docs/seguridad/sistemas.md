
# Seguridad Sistemas

## Firewall

Es recomendable al firewall añadirle las listas de paises que más ataques genera:

- http://www.ipdeny.com/ipblocks/data/countries/all-zones.tar.gz

Y también mantener actualizadas en el firewall las listas de IPs desde las que se generan más ataques:

- https://github.com/stamparm/ipsum
- https://www.spamhaus.org/


## Fail2ban

Bloqueará la IP orígen si se realizan diversos intentos de autenticación ssh erróneos:

- https://github.com/fail2ban/fail2ban

## Bastion

Nos permitirá centralizar, auditar y establecer permisos de acceso a nuestros servidores en infraestructura:

- https://github.com/warp-tech/warpgate

## Knock

Mecanismo de combinación de puertos que nos permitirá abrir o cerrar accesos (iptables) cuando ejecutemos las peticiones de puertos en orden correcto:

- https://github.com/jvinet/knock/