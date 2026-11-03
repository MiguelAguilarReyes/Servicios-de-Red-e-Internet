<h1>Actividad #2</h1>
<h2>Ejercicios</h2>

1. Apache utilizará el puerto 81 además del 80

2. Añadir el dominio “marisma.intranet” en el fichero “hosts”

3. Cambia la directiva “ServerTokens” para mostrar el nombre del producto

4. Comprueba si se visualiza el pie de página en las páginas generadas por Apache (por ejemplo, en las páginas de error). Cambia el valor de la directiva “ServerSignature” y comprueba que funciona correctamente

5. Crea un directorio “prueba” y otro directorio “prueba2”. Incluye un par de páginas en cada una de ellas

6. Redirecciona el contenido de la carpeta “prueba” hacia “prueba2”

7. Es posible redireccionar tan solo una página en lugar de toda la carpeta. Pruébalo

8. Usa la directiva userdir

9. Usa la directiva alias para redireccionar a una carpeta dentro del directorio de usuario

10. ¿Para qué sirve la directiva Options y dónde aparece. Comprueba si apache indexa los directorios. Si es así, ¿cómo lo desactivamos?

<h2>1. Configurar Apache para usar el puerto 81 además del 80</h2>

El archivo correcto es /etc/apache2/ports.conf.

Listen 80 Listen 81

<img width="886" height="425" alt="image" src="https://github.com/user-attachments/assets/54ea2afd-89c3-4dff-a63e-a0b3eeb42599" />

<img width="886" height="420" alt="image" src="https://github.com/user-attachments/assets/ff1a58f4-d1e3-4bc7-a03a-bef9cfd065e2" />

<img width="886" height="421" alt="image" src="https://github.com/user-attachments/assets/98a12795-2492-42e8-9386-3c8b19e3e332" />

<img width="886" height="423" alt="image" src="https://github.com/user-attachments/assets/95c29156-2c21-4338-88e6-e2fe3e4d228f" />

<h2>2. Añadir el dominio “marisma.intranet” en el fichero “hosts”</h2>

El archivo se llama /etc/hosts. Además, el dominio debe ir junto marisma.intranet

Abre el archivo con permisos de administrador:

sudo nano /etc/hosts

<img width="886" height="421" alt="image" src="https://github.com/user-attachments/assets/45822c1a-8db5-4885-84b5-a22b7a7192a4" />

Y añade la siguiente línea al final:

127.0.0.1 marisma.intranet

<h2>3. Modificar la directiva ServerTokens</h2>

Para reforzar la seguridad y el endurecimiento (hardening) del servidor web Apache, se ajusta la directiva ServerTokens dentro del archivo de configuración, 
restringiendo la información que se transmite en las cabeceras de respuesta HTTP. 
Al configurar el parámetro en modo Prod, el sistema únicamente revelará la etiqueta genérica del software (Apache), omitiendo cualquier detalle o número de versión específico.

<img width="886" height="423" alt="image" src="https://github.com/user-attachments/assets/a2730f95-f5f9-4ca6-bcfa-e90937d198d0" />

<h2>4. Modificar la directiva ServerSignature</h2>

Se comprueba si Apache muestra un pie de página en las páginas generadas por el servidor, como las páginas de error. Para ello, se modifica la directiva ServerSignature en el archivo security.conf
ServerSignature On

Verificación del estado inicial (On): Por defecto, Apache revela información del entorno en el pie de página de las respuestas de error. 
Puedes comprobarlo generando una incidencia de forma intencionada mediante el acceso a un recurso o URL que no exista.
Aplicación de la medida de seguridad: Modifica el parámetro para establecer su valor en Off, bloqueando así la exposición de dichos datos.

<h2>5. Crear los directorios prueba y prueba2</h2>
Se crean dos directorios dentro del sitio web de Apache, llamados prueba y prueba2. En cada uno se incluyen dos páginas HTML para comprobar que el servidor puede acceder a su contenido

<img width="886" height="422" alt="image" src="https://github.com/user-attachments/assets/1870e1e8-c1fe-4ee0-93fa-76874355c4a2" />
Hacemos lo mismo con prueba2

<h2>6. Redireccionar el contenido de prueba hacia prueba2</h2>

Se configura Apache para redirigir las peticiones realizadas al directorio prueba hacia prueba2. 
De esta forma, al acceder a una página de prueba, el navegador se dirige al directorio de destino En la carpeta de la imagen usando "sudo nano" para entrar. 
En lo ultimo escribimos "Redirect /prueba /prueba2" 

<img width="886" height="420" alt="image" src="https://github.com/user-attachments/assets/91c7573d-5a75-4073-8379-66122fa06e59" />

Luego de eso usamos el comando "Sudo systemctl restart apache2" para reiniciar el servicio

<h2>7. Redirección de una página específica</h2>

La regla de redirección puede acotarse de manera específica para que impacte únicamente sobre un fichero particular, en lugar de extenderse a todo el contenedor o directorio raíz.

Redirect /prueba/pagina.html /prueba2/nueva_pagina.html

<img width="694" height="61" alt="image" src="https://github.com/user-attachments/assets/57a75793-87bc-4231-97f6-85e73373181e" />

<img width="288" height="30" alt="image" src="https://github.com/user-attachments/assets/4dea6742-c6a6-4bde-bdfb-152e1bc4db02" />

<img width="696" height="64" alt="image" src="https://github.com/user-attachments/assets/743e1b23-a278-4792-b612-1d3d8dd9f03d" />

<h2>8. Habilitación y configuración del módulo Userdir (userdir)</h2>

Mediante la configuración del módulo userdir de Apache, se permite que cada usuario del sistema despliegue y sirva páginas web particulares utilizando como origen sus propias rutas o directorios personales de usuario.

<img width="886" height="415" alt="image" src="https://github.com/user-attachments/assets/17b0caf8-a6f6-47c7-b24a-38abfd76916c" />

Reiniciamos Apache y creamos una carpeta de prueba para nuestro usuario, además de que creamos un nuevo archivo index. Después comprobamos que funciona.

<img width="432" height="42" alt="image" src="https://github.com/user-attachments/assets/d55318f4-9949-493c-ada9-b781de4e6422" />

<h2>9. Uso de la directiva Alias hacia el directorio de usuario</h2>

Mediante el uso de la directiva Alias, es posible asociar direcciones URL determinadas con ubicaciones físicas externas al directorio raíz principal (DocumentRoot) del servidor web.
En este escenario particular, esta funcionalidad se emplea para asociar una ruta de red con un directorio específico situado en el espacio de usuario del sistema operativo.
Actualización del archivo de configuración:
Es necesario acceder al fichero de configuración principal de Apache (como por ejemplo /etc/apache2/apache2.conf o al archivo de los sitios disponibles en /etc/apache2/sites-available/000-default.conf)
para incorporar la directiva Alias.

<img width="1021" height="493" alt="image" src="https://github.com/user-attachments/assets/1142fff1-a8e8-454f-a8d6-ff6b42f0bf68" />

Reiniciar el servidor web: Para aplicar los cambios realizados en la configuración de Apache y comprobamos 

<img width="1024" height="272" alt="image" src="https://github.com/user-attachments/assets/32c6a993-eea4-4376-9011-63b8befd8271" />

<h2>10. Uso y configuración de la directiva Options</h2>

¿Cuál es la función de la directiva Options?
Permite gestionar qué propiedades o capacidades del servidor web se habilitan o deshabilitan en una ruta o directorio concreto.
Entre sus aplicaciones se incluye la administración de enlaces simbólicos, la autorización para ejecutar scripts o la habilitación de listados de archivos.
¿En qué ubicación se declara?
Se sitúa en el interior de los bloques de configuración de directorios de Apache, delimitada por etiquetas como <Directory> o <DirectoryMatch> 
(por ejemplo, dentro del archivo /etc/apache2/sites-available/000-default.conf o en un fichero .htaccess).

<img width="1027" height="510" alt="image" src="https://github.com/user-attachments/assets/f5ce3852-b9dc-4b84-9c19-1bf57ac11f35" />

Para verificar si el servidor web Apache cuenta con la indexación de directorios habilitada (Directory Listing),
es suficiente con acceder desde un navegador web a una ruta o carpeta que carezca de un fichero predeterminado de bienvenida (como index.html o index.php). 
Si en lugar de recibir un código de error por acceso denegado se visualiza un listado con los archivos y subdirectorios que integran dicha ruta, se confirma que la indexación está activa.

<img width="1024" height="272" alt="image" src="https://github.com/user-attachments/assets/172a2fbb-02cc-4a78-8185-15683d6aa7cf" />

Cómo lo desactivamos? Para deshabilitar la indexación automática y evitar que los usuarios puedan ver el contenido de las carpetas, debes anteponer un signo menos a la opción (-Indexes).
Debe quedar configurado de la siguiente manera en tu archivo de Apache:

<img width="1024" height="493" alt="image" src="https://github.com/user-attachments/assets/9090a16e-581f-4ef6-8d25-564bcdbe4af2" />

<h1>Actividad 2.2</h1>

Primero hay que crear el script para ello nos vamos a colocar en el directorio /ete/apache2 con el siguiente comando:

cd /etc/apache2

Una vez estemos en ese directorio crearemos el archivo ports.sh con el comando sudo nano ports.sh Una vez hayamos creado el archivo tendremos que poner el siguiente codigo:

#!/bin/sh
if [$# -ne 1]; then
  echo "Falta numero de puerto"
  echo "Sintaxis: ./puerto.sh num"
  echo "Ejemplo : ./puerto.sh 81"
else
    grep "Listen $1" ports.conf >> null
    if [$? -eq o]; then
        echo "Error. Existe ese numero de puerto en ports.conf"
    else
        echo "No existe ese puerto en ports.conf"
        cp ports.conf ports.bak
        echo "Listen $1" >> ports.conf
        echo "Puerto añadido"
        service apache2 restart
        echo "Apache reiniciado"

  fi

fi

Al ejecutar esto nos añadirá el puerto a ports.conf

El siguiente paso consiste en implementar un script diseñado para añadir una asociación de dominio e IP al fichero hosts.
Para su desarrollo, reutilizaremos la lógica del script previo, modificando los parámetros necesarios para adaptarlo a esta nueva funcionalidad.

#!/bin/sh
if [$# -ne 1]; then
        echo "Faltan los datos"
        echo "Sintaxis: ./hosts.sh ip dominio"
        echo "Ejemplo : ./hosts.sh 172.0.0.1 prueba.com"
else
        grep -w "$2" /etc/hosts > /dev/null
        if [$? -eq 0]; then
                echo "Error. Existe ese dominio"
        else
                echo "No existe el host"
                cp hosts hosts.bak
                echo "$1 $2" >> hosts
                echo "Dominio añadido"
                service apache2 restart
                echo "Apache reiniciado"
        fi
fi

Para el tercer script necesitaremos hacer el siguiente script:

#!/bin/sh

if [ $# -ne 3 ]; then
        echo "Faltan parametros"
        echo "Sintaxis: ./crear_web.sh titulo cabecera mensaje"
        echo "Ejemplo: ./crear_web.sh MiWeb Bienvenidos Hola"
else
        echo "<html>" > /var/www/your_domain/index.html
        echo "<head>" >> /var/www/your_domain/index.html
        echo "<title>$1</title>" >> /var/www/your_domain/index.html
        echo "</head>" >> /var/www/your_domain/index.html
        echo "<body>" >> /var/www/your_domain/index.html
        echo "<h1>$2</h1>" >> /var/www/your_domain/index.html
        echo "<p>$3</p>" >> /var/www/your_domain/index.html
        echo "</body>" >> /var/www/your_domain/index.html
        echo "</html>" >> /var/www/your_domain/index.html

  echo "Pagina web creada correctamente"
  echo "Archivo creado: index.html"
fi














































































