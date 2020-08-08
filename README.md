Hay distintos juegos de plantillas para descargar en función a tu necesidad

# BanticsWordpressCombo
Esta plantilla intenta cubrir las siguientes características, que vemos generalmente util para sitios de Wordpress

* Forzar trafico HTTP (80) a HTTPS (443)
* Denegar acceso al archivo xmlrpc.php 
* PHPMyAdmin change port to 8085


* Instalación:

git clone https://github.com/banticscoop/vestaHttps.git

sudo cp vestaHttps/WPress_Ban_force_https.* /usr/local/vesta/data/templates/web/nginx/php-fpm/

sudo service vesta restart

Con esto deberíamos poder elegir en los distintos dominios, la plantilla el cuestión.

* Configuración:

En VestaCP Firewall tenemos que agregar una regla permitiendo el tráfico por el port 8085
Action: ACCEPT - Protocol: TCP - Port: 8085 - IP address: 0.0.0.0/0 - Comment: PHPMyAdmin
 
En caso de contar con un hosting a nivel infraestructura (AWS - GoogleCloud - etc) tambien debe agregarse a reglas de firewall el acceso al port 8085 (EN Aws Security Groups)

Se edita desde panel de vesta, en Server -> Config -> DB la url del phpmyadmin para corregir el acceso desde el panel del usuario. por ejemplo
https://bantics.com.ar:8085/phpmyadmin/  





# vestaHttps
Plantillas de VestaCP usadas para forzar redirección de HTTPS sobre Wordpress
Usamos VestaCP con Nginx

Utilizamos estas plantillas para forzar trafico a HTTPS (443) en caso que entre la petición por el port 80
Están probadas para implementaciones de WordPress, pero podrías modificarla para tus requerimientos.

Hay 2 archivos de plantillas, el tpl y stpl, la "magia" la hace el tpl (que se usa en request no SSL) que configura al nginx para hacer un rewrite al https

Instalación:

git clone https://github.com/banticscoop/vestaHttps.git

sudo cp vestaHttps/*.*tpl /usr/local/vesta/data/templates/web/nginx/php-fpm/

sudo service vesta restart 

Con esto deberíamos poder elegir en los distintos dominios, la plantilla el cuestión.

