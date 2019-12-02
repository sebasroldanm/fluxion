<p align="center"><img src="https://github.com/sebasroldanm/fluxion/master/logos/logo1.jpg?raw=true" /></p>

# Fluxion es el futuro de los ataques MITM WPA
Fluxion es un remake de linset de vk496 con (con suerte) menos errores y más funcionalidad. Es compatible con la última versión de Kali (rodante). El ataque es principalmente manual, pero las versiones experimentales manejarán automáticamente la mayoría de las funcionalidades de las versiones estables.

## :trident: FAQ

#### "Los clientes no se conectan automáticamente al punto de acceso falso"
Este es un ataque de ingeniería social y no tiene sentido arrastrar clientes automáticamente. El script se basa en el hecho de que un usuario debe estar presente para ingresar las credenciales inalámbricas.

#### "No hay conectividad a Internet en el punto de acceso falso"
No debería haber uno. Todo el tráfico se está hundiendo en el portal cautivo incorporado a través de un falso respondedor DNS para capturar las credenciales.

#### "Los sitios falsos no funcionan"
Puede haber un problema con lighttpd. La versión experimental se prueba en lighttpd 1.439-1, cualquier cosa nueva puede romper la funcionalidad. Si tiene problemas, utilice la versión estable.

#### "El menú experimental no responde"
En la versión experimental, comprobará automáticamente el apretón de manos. Arreglaré el menú en breve. Si necesita una GUI, use la versión estable (que no controla automáticamente los apretones de manos).

#### "Necesito iniciar sesión (en Android)"
Así es como funciona el guión. El portal cautivo falso está configurado por el propio script para recopilar las credenciales. No te asustes, está bien.

#### "La dirección MAC del punto de acceso falso difiere de la original"
La dirección MAC del punto de acceso falso difiere en un octeto del original para evitar que Fluxion desatente a los clientes durante la sesión.
## Instalación
``` wget https://raw.githubusercontent.com/sebasroldanm/fluxion/master/install/install.sh && bash install.sh ```

## Actualizaciones
Si desea enviar una función, hágalo etiquetando su problema como una "mejora" o envíe un PR. No tengo tiempo suficiente para hacer cambios diarios en fluxion, lo siento.

## :white_check_mark: versiones de dependencia incluidas1. Aircrack : 1:1.2-0~rc4-0parrot0
2. Lighttpd : 1.439-1
3. Hostapd  : 1:2.3-2.3 _Si quieres comparar este tipo `dpkg -l | grep "name"`_

## :scroll: Registro de cambios
Fluxion recibe actualizaciones semanales con nuevas características, mejoras y correcciones de errores.
Asegúrese de revisar el [registro de cambios aquí](https://github.com/sebasroldanm/fluxion/commits/master).

## :octocat: Cómo contribuir
¡Todas las contribuciones son bienvenidas! Código, documentación, gráficos o incluso sugerencias de diseño son bienvenidos; usa GitHub al máximo. Envíe solicitudes de extracción, contribuya con tutoriales u otro contenido wiki; lo que tenga que ofrecer, ¡lo agradeceríamos!

## :book: Cómo funciona
* Escanear las redes.
* Capture un apretón de manos (no se puede usar sin un apretón de manos válido, es necesario verificar la contraseña)
* Utilice la interfaz WEB *
* Inicie una instancia de FakeAP para imitar el punto de acceso original
* Genera un proceso MDK3, que elimina la autenticación de todos los usuarios conectados a la red de destino, para que puedan ser atraídos a conectarse a FakeAP e ingresar la contraseña de WPA.
* Se lanza un servidor DNS falso para capturar todas las solicitudes de DNS y redirigirlas al host que ejecuta el script
* Se lanza un portal cautivo para servir una página, que solicita al usuario que ingrese su contraseña WPA
* Cada contraseña enviada es verificada por el apretón de manos capturado anteriormente
* El ataque terminará automáticamente, tan pronto como se envíe una contraseña correcta

## :heavy_exclamation_mark: Requisitos
Un sistema operativo basado en Linux. Recomendamos Kali Linux 2 o Kali 2016.1 rolling. Kali 2 y 2016 son compatibles con las últimas versiones de aircrack-ng. Se recomienda una tarjeta wifi externa.

## :octocat: Creditos
1. l3op - contribuyente
2. dlinkproto - contribuyente
3. vk496 - desarrollador de linset
4. Derv82 - @Wifite/2
5. Princeofguilty - @webpages
6. Photos for wiki @http://www.kalitutorials.net
7. Ons Ali @wallpaper
8. PappleTec @sites

## Aviso Legal

***Fluxion está destinado a ser utilizado solo con fines de seguridad legal, y solo debe usarlo para proteger las redes / hosts que posee o tiene permiso para probar. Cualquier otro uso no es responsabilidad del desarrollador (es). Asegúrese de comprender y cumplir con las licencias y leyes de Fluxion en su área. En otras palabras, no seas estúpido, no seas un imbécil y utiliza esta herramienta de manera responsable y legal.***

