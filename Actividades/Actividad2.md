# Universidad de San Carlos de Guatemala
**Facultad de Ingeniería**
**Escuela de Ciencias y Sistemas (ECYS)**
**Prácticas Iniciales - Sección C**

---
**Nombre**: Josué Javier Carrera Soyós
**Carné**: 202300834
**Fecha**: 20 de agosto de 2026

---
# Actividad en Clase: Despliegue de Servidor Apache2

**Descripción**: Actividad práctica sobre la instalación de Apache2, la gestión del servicio y una pequeña edición del archivo `index.html`, todo desde la terminal.

En esta actividad se instaló el servidor web Apache2 en Ubuntu y se modificó la página por defecto para verificar el correcto funcionamiento del servicio. Todas las acciones se realizaron desde la terminal.

### 1. Actualización de los repositorios del sistema

El primer paso fue actualizar la lista de paquetes disponibles en los repositorios de Ubuntu.

- **Comando utilizado:** `sudo apt update`
- **¿Qué realiza?** Descarga la información más reciente sobre los paquetes disponibles en los repositorios, de modo que el sistema sepa qué versiones actualizadas existen. Es el paso previo recomendado antes de instalar o actualizar software.

![[Screenshot_20260817_103631.png]]

### 2. Actualización de los paquetes instalados

Posteriormente se actualizaron los paquetes ya instalados en el sistema.

- **Comando utilizado:** `sudo apt upgrade -y`
- **¿Qué realiza?** Aplica las actualizaciones de todos los paquetes que tengan una versión más reciente disponible. La opción `-y` responde automáticamente "sí" a cualquier confirmación, evitando la interacción manual durante el proceso.

![[Screenshot_20260817_104025.png]]

### 3. Instalación de Apache2

Con los repositorios actualizados, se procedió a instalar el servidor web Apache2.

- **Comando utilizado:** `sudo apt install apache2 -y`
- **¿Qué realiza?** Descarga e instala Apache2 junto con sus dependencias. Apache2 es el servidor web más utilizado en Linux: se encarga de recibir las peticiones de los navegadores y entregarles las páginas web solicitadas. La opción `-y` confirma automáticamente la instalación.

![[Screenshot_20260817_104401.png]]

### 4. Verificación del estado del servicio

Para confirmar que Apache2 quedó instalado y en funcionamiento, se consultó el estado del servicio.

- **Comando utilizado:** `sudo systemctl status apache2`
- **¿Qué realiza?** Muestra el estado actual del servicio, incluyendo si se encuentra activo, sus procesos y registros recientes. Para confirmar que el servicio está encendido, se debe observar la línea `Active: active (running)`.

![[Screenshot_20260817_104504.png]]

Existen además otros comandos útiles para gestionar el servicio:

- `sudo systemctl start apache2`: inicia el servicio si se encuentra detenido.
- `sudo systemctl stop apache2`: detiene el servicio.
- `sudo systemctl restart apache2`: reinicia el servicio para aplicar cambios de configuración.

### 5. Verificación en el navegador web

Como verificación de que el servidor funciona correctamente, se accedió desde el navegador web a la dirección `http://localhost`. Esta ruta apunta al propio equipo, donde el servidor Apache2 escucha las peticiones. Al ingresar, se mostró la página por defecto de Apache2, es decir, el archivo `index.html` incluido con la instalación, lo que confirma que el servicio está operando.

![[Screenshot_20260817_104602.png]]

### 6. Acceso al directorio de archivos web

Los archivos que Apache2 sirve se encuentran en el directorio `/var/www/html/`. Para editarlos se siguió este procedimiento:

- Se accedió al directorio con el comando `cd /var/www/html/`.
- Se ejecutó `ls` para listar el contenido y se observó la presencia del archivo `index.html`.
- Se abrió el archivo con el comando `sudo nano index.html`.

![[Screenshot_20260817_151339.png]]

> **¿Por qué usamos `sudo`?** El directorio `/var/www/html/` pertenece al usuario *root* (administrador). Por lo tanto, para poder modificar los archivos dentro de él se necesitan privilegios elevados; sin `sudo` el sistema denegaría la edición.
>
> **¿Qué es `nano`?** Es un editor de texto interactivo que opera directamente en la terminal, ideal para modificar archivos de configuración o de código sin necesidad de una interfaz gráfica.

### 7. Edición del archivo index.html

Al abrir el archivo con nano, se pudo ver el código HTML que generaba la página por defecto de Apache2. Este contenido fue el que se mostró en el navegador en el paso anterior. Con el editor abierto, se procedió a modificar el archivo.

> **¿Qué es HTML?** Es el lenguaje de marcado estándar para la creación de páginas web. Permite estructurar el contenido a través de etiquetas como `<h1>`, `<p>` y `<body>`.

![[Screenshot_20260817_110037.png]]

Se eliminó todo el contenido original y se reemplazó por unas líneas básicas de HTML, creando una página personalizada.

![[Screenshot_20260817_110436.png]]

Para finalizar la edición se utilizaron los siguientes comandos de nano:

- **Guardar el archivo:** `Ctrl + O` (luego `Enter` para confirmar el nombre del archivo).
- **Cerrar el editor:** `Ctrl + X`.

### 8. Comprobación de los cambios

Finalmente, se accedió nuevamente a `http://localhost` desde el navegador. En esta ocasión se mostró el nuevo contenido en lugar de la página por defecto. Fue necesario recargar la página en el navegador para observar los cambios. El hecho de que el navegador muestre el contenido personalizado confirma que el archivo fue editado correctamente y que el servidor continúa funcionando de forma adecuada.

![[Screenshot_20260817_110538 1.png]]

### Conclusiones
- La actualización periódica de paquetes mediante `apt update` y `apt upgrade` asegura la estabilidad y seguridad del sistema antes de instalar nuevos servicios.
- El uso del comando `systemctl` permite verificar y controlar el ciclo de vida de los servicios en Linux.
- La modificación directa del archivo `index.html` demuestra cómo el servidor Apache2 sirve páginas estáticas almacenadas en la ruta por defecto `/var/www/html/`.
