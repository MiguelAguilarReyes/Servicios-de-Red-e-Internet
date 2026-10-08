<h1>Actividad #1</h1>  
Está página ha sido usada como guía para hacer la actividad https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-20-04-es

-Instalar Apache y actualizar el firewall
Para comenzar con la configuración del servidor web en mi máquina Ubuntu, en primer lugar procedo a actualizar la lista de paquetes del gestor apt e instalar el paquete correspondiente a Apache

-Actualizar el índice de paquetes
Se ejecuta el siguiente comando para asegurar que se obtiene la información más reciente de los repositorios:

<img width="886" height="482" alt="image" src="https://github.com/user-attachments/assets/e4b1cf23-66fa-4e71-a3a7-73526c7639d2" />

-Configuración del firewall (UFW)
Una vez completada la instalación de Apache, procedo a ajustar la configuración del firewall (ufw) para permitir el tráfico web

-Listar los perfiles de aplicaciones disponibles en UFW
Para verificar qué perfiles de aplicación reconoce el firewall, para habilitar únicamente el tráfico web no cifrado mediante el perfil Apache y para verificar que la regla se ha aplicado correctamente y que el tráfico para Apache está permitido:

<img width="886" height="479" alt="image" src="https://github.com/user-attachments/assets/58249de8-ec67-4cfc-b6ef-f51169d7ca64" />

En esta captura se puede ver todo lo mencionado anteriormente

Una vez configurado y verificado el servidor web Apache, se procede a instalar el sistema gestor de bases de datos MySQL

<img width="886" height="478" alt="image" src="https://github.com/user-attachments/assets/d640a401-7493-4714-9b5d-bcae710ed168" />

Una vez completada la instalación, se ejecuta la secuencia de comandos de seguridad interactiva que viene preinstalada con MySQL(Aceptamos todo lo que nos pregunten). 

<img width="886" height="474" alt="image" src="https://github.com/user-attachments/assets/f684680b-71b6-4da4-8e08-5e14bb4832e0" />

Cuando termine, si comprueba si se puede iniciar sesión en la consola de MySQL al escribir lo siguiente:

<img width="886" height="480" alt="image" src="https://github.com/user-attachments/assets/ca8d34a9-6c43-4ed6-84e2-264e60d72f8f" />

Ya contamos con Apache para la interfaz visual y MySQL para la gestión de la información. Ahora incorporamos PHP, encargado de ejecutar el código para generar páginas dinámicas

Para lograrlo, instalamos el paquete principal junto con dos complementos indispensables: libapache2-mod-php (para que Apache interprete archivos PHP) y php-mysql (para conectar PHP con la base de datos)

<img width="886" height="476" alt="image" src="https://github.com/user-attachments/assets/5e06d507-990a-44ff-ab8f-64b9f4ddd48b" />

Una vez finalizada la instalación, se puede verificar que todo funcione correctamente y comprobar la versión instalada

<img width="886" height="482" alt="image" src="https://github.com/user-attachments/assets/8bf846fd-a0e4-4c26-8a37-c1f530c87b74" />

Apache permite utilizar hosts virtuales para gestionar múltiples dominios desde un mismo servidor. En esta guía emplearemos JMBQ como ejemplo (debes cambiarlo por tu dominio real).

Ubuntu 20.04 incluye un sitio web predeterminado en /var/www/html. Para evitar modificarlo y facilitar la administración de varios sitios, crearemos una nueva estructura de carpetas dentro de /var/www para nuestro dominio, manteniendo la carpeta predeterminada solo como respaldo.

Creamos la carpeta correspondiente y además le asignamos la propiedad del directorio a nuestro usuario actual mediante la variable de entorno
aparte también abrimos un nuevo archivo de configuración dentro del directorio sites-available de Apache:

<img width="886" height="479" alt="image" src="https://github.com/user-attachments/assets/866a788d-c122-4f7e-a03e-5d1c4af92a56" />

<img width="886" height="478" alt="image" src="https://github.com/user-attachments/assets/8e2abcf7-646f-4e86-880f-29ea53e03084" />

A continuación, habilitamos el nuevo host virtual:

<img width="886" height="479" alt="image" src="https://github.com/user-attachments/assets/7ca1d4d4-cf80-4b74-a2e8-5f61d9123d1f" />

Verificar y Aplicar la Configuración Antes de reiniciar el servidor, es fundamental comprobar que la configuración de Apache no tenga errores de sintaxis:

<img width="886" height="474" alt="image" src="https://github.com/user-attachments/assets/a676231d-bf43-4dc5-baac-165cd630c261" />

Crear la Página de Prueba El sitio web ya está activo, pero el directorio raíz está vacío. Creamos un archivo `index.html` para verificar que el host virtual funciona correctamente:

<img width="886" height="473" alt="image" src="https://github.com/user-attachments/assets/80c26f25-9484-4a15-b668-4ec958132ce6" />

Verificamos en el navegador Una vez realizados los pasos anteriores, abre tu navegador web y escribe el nombre de dominio o la dirección IP de tu servidor para comprobar que todo funciona correctamente:

<img width="886" height="459" alt="image" src="https://github.com/user-attachments/assets/ea519bd6-e9f7-4e87-9cf9-89f19f0b5b2b" />

Ahora que tenemos una ubicación personalizada para alojar los archivos y las carpetas de su sitio web, creamos una secuencia de comandos PHP de prueba para verificar que Apache pueda gestionar solicitudes y procesar solicitudes de archivos PHP.

<img width="886" height="463" alt="image" src="https://github.com/user-attachments/assets/9e6fff1a-bbaf-40cf-8dd7-0337089eb76e" />

Cuando terminemos, guardamos y cerramos el archivo. Para probar esta secuencia de comandos, vamos al navegador web y accedemos al nombre de dominio o la dirección IP del servidor, seguido del nombre de la secuencia de comandos, que en este caso es info.php:

<img width="886" height="462" alt="image" src="https://github.com/user-attachments/assets/835aa535-cd64-4468-a8fb-0dac28babb70" />

Para probar si PHP puede establecer conexión con MySQL y ejecutar consultas a la base de datos, se puede crear una tabla de prueba con datos ficticios y realizar consultas relacionadas con su contenido con una secuencia de comandos PHP. Para poder hacerlo, debemos crear una base de datos de prueba y un nuevo usuario de MySQL debidamente configurado para acceder a ella.

<img width="886" height="456" alt="image" src="https://github.com/user-attachments/assets/9f58d79a-0ee5-4dc9-b470-933705120cf2" />

Para crear una base de datos nueva, ejecute el siguiente comando desde su consola de MySQL, además de que comprobamos también que todo vaya a la perfección:

<img width="886" height="461" alt="image" src="https://github.com/user-attachments/assets/53a94acc-be40-49d0-8006-a39b494d53ed" />

A continuación, crearemos una tabla de prueba denominada todo_list: Desde la consola de MySQL, ejecute la siguiente instrucción:

<img width="886" height="692" alt="image" src="https://github.com/user-attachments/assets/2b553383-8424-4183-9893-abd2c91901f9" />

Inserte algunas filas de contenido en la tabla de prueba. Es posible que quiera repetir el siguiente comando algunas veces, usando valores diferentes:

<img width="886" height="460" alt="image" src="https://github.com/user-attachments/assets/db3cecc8-6722-48d3-ab0e-212f9491a46e" />

Creamos un nuevo archivo PHP en el directorio web root personalizado usando nano:

<img width="886" height="417" alt="image" src="https://github.com/user-attachments/assets/14c7c325-c873-4499-b659-acfcb36726ea" />

<img width="886" height="416" alt="image" src="https://github.com/user-attachments/assets/7d3c8606-6405-4037-a85c-03d9a7ec18c0" />

Guardamos y cerramos el archivo cuando finalice la edición.

Ahora, podemos acceder a esta página en el navegador web al visitar el nombre de dominio o la dirección IP pública del sitio web seguido de /todo_list.php:

<img width="886" height="461" alt="image" src="https://github.com/user-attachments/assets/de29da45-b4ae-4764-95e0-7d903d69eeb3" />




























