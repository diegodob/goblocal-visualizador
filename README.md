# GOBLOCAL - VISUALIZADOR DE EJEMPLO
Prueba de concepto de visualizador para el proyecto GOBLOCAL

## LICENCIA
Fork de:
https://github.com/ign-argentina/argenmap
Autor de Argenmap: IGN
Licencia: GPL

## LICENCIA PROXY
## 6 Proxy
El visualizador de GOBLOCAL consume información de servidores que no tienen habilitado la opción de CORS o que no implementan certificado de seguridad SSL/TSL.  Debido a que es necesario que dichas configuraciones estén establecidas en los servidores para poder tomar datos correctamente de ellos es imprescindible para el correcto funcionamiento del visualizador se ha habilitado temporariamente un proxy que suple dichas falencias.
El proxy se encuentra licenciado por Esri mediante la licencia Apache License, Version 2.0 y puede ser descargado de la siguiente URL: https://github.com/Esri/resource-proxy.
Una copia del proxy, su configuración y licencia se encuentra en el presente repositorio descargado previamente.
Requerimientos del proxy:
Requirements
* PHP 5.6 or higher (recommended)
* cURL PHP extension
* OpenSSL PHP extension
* PDO_SQLITE PDO PHP extension

El proxy tiene un archivo de log que debe ser redirigido a un directorio que PHP pueda escribir.
Para configurarlo debe editarse el archivo: /proxy/proxy.config
En el caso de GOBLOCAL se puede habilitar el log agregando el atributo logFile. 
	
Por ejemplo:

	<?xml version="1.0" encoding="utf-8" ?>
	<ProxyConfig allowedReferers="*"
	logFile="/var/log/proxy_log.log"
	mustMatch="true">


Debe validar que el directorio se pueda escribir. Si encuentra problemas al utilizar el proxy, puede deshabilitar el log para evaluar si es un problemas de permisos en el directorio de salida del archivo del log, eliminando la opción <b>logFile</b>

	<?xml version="1.0" encoding="utf-8" ?>
	<ProxyConfig allowedReferers="*"	
	mustMatch="true">
	

