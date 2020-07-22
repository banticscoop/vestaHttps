# vestaHttps
Plantillas de VestaCP usadas para forzar redirección de HTTPS sobre Wordpress
Usamos VestaCP con Nginx

Utilizamos estas plantillas para forzar trafico a HTTPS (443) en caso que entre la peticion por el port 80
Estan probadas para implementaciones de WordPress, pero podrias modificarla para tus requerimientos.

Hay 2 archivos de plantillas, el tpl y stpl, la "magia" la hace el tpl (que se usa en request no SSL) que configura al nginx para hacer un rewrite al https

Instalacion:

git clone https://github.com/banticscoop/vestaHttps.git

sudo cp vestaHttps/WPress_Ban_force_https.* /usr/local/vesta/data/templates/web/nginx/php-fpm/

sudo service vesta restart

Con esto deberiamos poder elegir en los distintos dominios, la plantilla el cuestion.

