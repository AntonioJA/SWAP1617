# Documentacion Práctica 3 #

## Servidor Web Nginx
Una vex instalado nginx en la máquina balanceadora con los comandos:

sudo apt-get update && sudo apt-get dist-upgrade && sudo apt-get
autoremove

sudo apt-get install nginx

sudo systemctl start nginx

Ahora procedemos a configurar el archivo /etc/nginx/conf.d/default.conf de la siguiente forma:
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/ConfiguracionNginx.png)

Una vez configurado el archivo default.conf hemos borrado el archivo /etc/nginx/sites-enabled/default para que nos salga la página de inicio de cada una de las máquinas
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/RmDefault.png)

Y una vez hecho esto, ya podemos comprobar que el balanceo de carga entre las dos máquinas que en nuestro caso hemos modificado el archivo default.conf para que la máquina 1 tenga el doble de capacidad que la máquina 2:

![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/ConfiguracionDefaultFinal.png)

Finalmente podemos comprobar el reparto de carga final:

![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/FuncionaminetoFinal.png)

## Balanceo de carga con haproxy

Primero instalamos haproxy con:

sudo apt-get install haproxy

Ahora procedemos a configurar el archivo /etc/haproxy/haproxy.cfg que lo dejamos de la siguiente manera:

![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/ConfiguracionHaproxy.png)


Lanzamos el servicio con el comando:

sudo /usr/sbin/haproxy -f /etc/haproxy/haproxy.cfg

Y comprobamos el balanceo de carga:

![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/RepartoHaproxy.png)

## Someter a una alta carga el servidor balanceador

Con el comando:

ab -n 10000 -c 100 10.0.2.14/index.html

Hacemos un Benchmark a la máquina balanceadora.

Primeramente le realizamos el Benchmark con el servicio Nginx funcionando:

![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/ApacheBenchmarktNginx.png)

Y ahora realizamos el mismo Benchmark con el servicio Haproxy funcionando:

![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica3/ApacheBenchmarkHaproxy.png)
