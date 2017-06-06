# Práctica 4

Práctica realizada en la sesión 4

## Parte de Nginx

**captura de pantalla de la configuración del archivo default.conf de nginx**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/configuracionNginx.png)

Con esta configuración tenemos un reparto de trabajo de peso 1 para ambas máquinas.
Para evitar problemas a la hora de mostrar las páginas correspondientes realizamos un rm al directorio 
/etc/nginx/sites-enabled/default

**captura de pantalla en el que se muestra este reparto de trabajo por defecto**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/repartoTrabajo.png)

Ye hemos tenido en cuenta que podemos indicar nosotros el peso que queramos con weigth como dice la prácitca,
el uso de ip_has para el balanceo por ip y el de keepalive. Dejamos el reparto por pesos 1 y 2.

**captura de pantalla de la configuración con reparto12**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/default21.png)


**captura de pantalla del reparto del trabajo con esta cofiguración**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/reparto2.png)

## Parte de Haproxy

**captura de pantalla de la configuración del archivo haproxy.cfg**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/haproxyconf.png)

Para que funcione correctamente paramos el servicio nginx y activamos el de haproxy.
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/haproxystart.png)

**captura de pantalla en el que se muestra este reparto de trabajo por defecto**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/repartohaproxy.png)

## Parte de alta carga

Utilizamos primero con la configuración mediante nginx con 10000 peticiones haciendo 100 cada vez.
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/cargarnginx.png)

Hacemos lo mismo pero con la configuración de haproxy
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/cargarhaproxy.png)
