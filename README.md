![logotipo](inove.jpg)
# Drone
### Simuladorde datos de un Drone basado en Flask

Este es un proyecto realizado por miembros de inove como un servicio para incorporar telemetr铆a de los sensores de un drone para el programa de ejemplos del curso de Python IoT.

![logotipo](sistema.jpg)

# Comenzando 馃殌
El objetivo de este proyecto es dar un ejemplo de aplicaci贸n de Python en la generaci贸n de datos de sensores y actuadores del tipo IoT. Este proyecto se basa en tomar la telemetr铆a generada y compartir dicha informaci贸n por mqtt.

__IMPORTANTE__: La aplicaci贸n se desarrollo con certificados SSL no verificados, es por ello que cuando ingrese a la URL el explorador le consultar谩 si "est谩 seguro" que desea ingresar a la p谩gina "no segura". Su URL se ver谩 como la siguiente:
```sh
https://<ip_host_flask>:5010
```

# Pre-requisitos 馃搵
Para poder ejecutar esta aplicaci贸n, ser谩 necesario tener instalada la versi贸n 3.7 de Python o superior.\
Instale las librerias que se comentan en requirements.txt

# T贸picos de MQTT
Por defecto la aplicaci贸n busca conectarse a un broker MQTT local (localhost) en el puerto 1883. Los datos de telemetr铆a de los sensores de la aplicaci贸n son:
```
sensores/inericiales
sensores/gps
```
Ejemplo usando mosquitto sub:
```sh
$ mosquitto_sub -t "sensores/inericiales"
```

Puede controlar el estado de la luz del drone (ON=1, OFF=0) o desl sisetma de vuelo y motores se realiza desde lossiguientes t贸picos:
```
actuadores/luces/1
actuadores/vuelo
actuadores/motores/1
actuadores/motores/2
actuadores/motores/3
actuadores/motores/4
```
Ejemplo usando mosquitto pub:
```sh
$ mosquitto_pub -t "actuadores/luces/1" -m 1
```

# Instalaci贸n y pruebas 馃敡鈿欙笍
Una vez levantado el server, deber谩 conocer la IP del servidor en su red local para poder ingresar:
```ssh
https://<ip_host_flask>:5010
```
Inmediatamente despu茅s podr谩 ver en su MQTT broker la telemetr铆a que evoluciona a medida que interactua con el sistema. Los comandos para ver los mensajes que llegan y como controlar los actuadores por mqtt se encuentran en la secci贸n anterior.

# Autores 鉁掞笍
### Miembros de Inove (coding school)
:octocat: Hern谩n Contigiani\
:octocat: Hector Vergara\
:octocat: Javier Carguno

# Licencia 馃搫
Este proyecto est谩 bajo la Licencia de Inove (coding school) para libre descarga y uso. Este proyecto tiene un prop贸sito educativo y de muestra, por ello, no nos responsabilizaremos por su uso indebido. As铆 mismo, no existe garant铆a en su implementaci贸n debido a que se trata de una demostraci贸n de uso gratuito con prop贸sitos educativos. 
### :copyright: Inove (coding school) 2022.
