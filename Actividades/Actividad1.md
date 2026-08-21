# Universidad de San Carlos de Guatemala
- **Facultad de Ingeniería**
- **Escuela de Ciencias y Sistemas (ECYS)**
- **Prácticas Iniciales - Sección C**

---
- **Nombre**: Josué Javier Carrera Soyós
- **Carné**: 202300834
- **Fecha**: 13 de agosto de 2026

---
# Tarea: Instalación de Ubuntu y Comandos Iniciales.

## 1. Instalación de Ubuntu

**Descripción**: Entorno utilizado para la práctica de comandos en Linux.

- **Versión**: Ubuntu 24.04 LTS
- **Modalidad**: Virtualización
- **Hipervisor**: VirtualBox

![Pasted image 20260820171119.png](../Attachments/Pasted%20image%2020260820171119.png)


## 2. Comandos de Navegación

### **`pwd` (Print Working Directory)**
---
 **Sintaxis:** `pwd [opciones]`
    
**Variaciones:**
   
   - `pwd`: Muestra la ruta del directorio actual.
       
   - `pwd -P`: Muestra la ruta física real (resolviendo enlaces simbólicos).
       
   - `pwd -L`: Muestra la ruta lógica (incluyendo enlaces simbólicos).

> **Nota técnica:** Un enlace simbólico funciona como un acceso directo en otros sistemas. La opción `-P` (Physical) omite los enlaces y revela la ubicación física real en el disco, mientras que `-L` (Logical) preserva la ruta de navegación.
       
**Ejemplo práctico:**

Partiendo del directorio `/home/vboxuser/` se ejecutaron los comandos `pwd`, `pwd -P` y `pwd -L`, y los tres devolvieron la misma respuesta: `/home/vboxuser`. Esto se debe a que el directorio actual no se accedió a través de un enlace simbólico, por lo que la ruta física (real) y la ruta lógica coinciden.

Se obtendría una diferencia únicamente si el directorio actual se alcanzara mediante un enlace simbólico: `pwd -P` mostraría la ruta real del directorio destino (resolviendo el enlace), mientras que `pwd -L` mostraría la ruta lógica que incluye el enlace simbólico.

![Pasted image 20260819220805.png](../Attachments/Pasted%20image%2020260819220805.png)
### **`cd` (Change Directory)**
---
**Sintaxis:** `cd [directorio]`
   
 **Variaciones:**
    
   - `cd`: Cambia al directorio personal (`/home/usuario`).
       
   - `cd ~`: Igual a `cd`, lleva al directorio personal.
       
   - `cd ..`: Sube un nivel en el árbol de directorios.
       
   - `cd -`: Regresa al directorio anterior donde se estaba ubicado.
       
   - `cd /ruta/absoluta`: Navega directamente utilizando la ruta desde la raíz `/`.

> **Concepto clave:** Las rutas **absolutas** inician siempre desde la raíz `/` (ej. `/home/vboxuser/Desktop`), mientras que las rutas **relativas** parten desde el directorio actual de trabajo (ej. `Desktop/Tarea`).
       
**Ejemplo práctico:**

Partiendo del directorio `/home/vboxuser/` se ejecutaron los siguientes comandos:
- `cd Desktop/`: ingresó al subdirectorio `Desktop`.
- `cd ..`: subió un nivel, regresando a `/home/vboxuser/`.
- `cd Desktop/Tarea/`: navegó directamente a la carpeta `Tarea` ubicada dentro de `Desktop`, usando una ruta relativa.
- `cd`: sin argumentos, regresó al directorio personal `/home/vboxuser/`.

![Pasted image 20260819222456.png](../Attachments/Pasted%20image%2020260819222456.png)
## 3. Comandos de Listado y Creación

### **`ls` (List)**
---
 **Sintaxis:** `ls [opciones] [directorio/archivo]`
    
 **Variaciones:**
    
   - `ls`: Lista archivos y carpetas del directorio actual.
       
   - `ls -l`: Muestra el listado en formato detallado (permisos, propietario, tamaño, fecha).
        
   - `ls -a`: Lista todos los archivos, incluidos los ocultos (los que empiezan con `.`).
        
   - `ls -lh`: Muestra detalles con tamaños legibles para humanos (KB, MB, GB).
        
   - `ls -la`: Combina formato largo y muestra archivos ocultos.

> **Nota técnica:** En el formato detallado (`-l`), el primer carácter indica el tipo de elemento (`-` para archivo regular y `d` para directorio), seguido por la cadena de permisos de lectura (`r`), escritura (`w`) y ejecución (`x`) para el propietario, grupo y otros usuarios.
        
**Ejemplo práctico:**

Estando en `/home/vboxuser/` se ejecutaron los comandos `ls`, `ls -l` y `ls -a`:
- `ls`: listó los archivos y carpetas del directorio actual.
- `ls -l`: mostró el listado en formato detallado (permisos, propietario, tamaño y fecha de modificación).
- `ls -a`: listó todos los archivos, incluidos los ocultos (los que comienzan con `.`).

![Pasted image 20260819222706.png](../Attachments/Pasted%20image%2020260819222706.png)

Luego se ejecutaron los comandos `ls -lh` y `ls -la`:
- `ls -lh`: mostró el listado detallado con los tamaños en formato legible para humanos (KB, MB, GB).
- `ls -la`: combinó el formato largo con la visualización de los archivos ocultos.

![Pasted image 20260819222857.png](../Attachments/Pasted%20image%2020260819222857.png)
## 4. Comandos de Manipulación de Archivos
### **`cp` (Copy)**
---
**Sintaxis:** `cp [opciones] origen destino`
    
**Variaciones:**
    
   - `cp archivo.txt copia.txt`: Copia un archivo en el mismo u otro directorio.
        
   - `cp -r carpeta1/ carpeta2/`: Copia una carpeta y todo su contenido de forma recursiva.
        
   - `cp -i origen destino`: Pide confirmación antes de sobrescribir si el archivo destino existe.
        
   - `cp -v origen destino`: Muestra en pantalla el progreso de lo que se está copiando.
        
**Ejemplo práctico:**

Ubicados en el directorio `/home/vboxuser/Desktop`, inicialmente se ejecutó `ls` para verificar el contenido existente, identificando el archivo simple `202300834` y la carpeta `Reporte` (la cual contenía un archivo en su interior).

Posteriormente, se realizaron las siguientes operaciones:
- `cp -v 202300834 202300834-copy`: Generó una copia del archivo simple, mostrando en la consola la confirmación del proceso gracias a la opción `-v` (verbose).
- `cp -r Reporte/ Reporte-copy/`: Copió la carpeta `Reporte` y todo su contenido de forma recursiva hacia un nuevo directorio denominado `Reporte-copy`.
- `ls Reporte-copy/`: Permitió comprobar que la estructura interna y los archivos contenidos en la carpeta original fueron duplicados de manera exitosa.

![Pasted image 20260820172218.png](../Attachments/Pasted%20image%2020260820172218.png)
### **`mkdir` (Make Directory)**
---
**Sintaxis:** `mkdir [opciones] nombre_directorio`
    
 **Variaciones:**
    
   - `mkdir carpeta`: Crea un único directorio.
        
   - `mkdir carpeta1 carpeta2`: Crea múltiples directorios a la vez.
        
   - `mkdir -p ruta/de/carpetas/anidadas`: Crea un árbol completo de directorios anidados (padres e hijos si no existen).
        
   - `mkdir -v carpeta`: Muestra un mensaje detallado por cada directorio creado.
        
**Ejemplo práctico:**

Desde la ruta `/home/vboxuser/Desktop`, se ejecutó primeramente el comando `ls` para inspeccionar el directorio, confirmando únicamente la presencia del archivo `202300834`.

A continuación, se realizaron los procedimientos de creación de directorios:
- `mkdir Tarea`: Creó un directorio individual llamado `Tarea`.
- `mkdir -v Actividades Presentaciones`: Creó simultáneamente dos carpetas (`Actividades` y `Presentaciones`), imprimiendo un mensaje descriptivo en consola por cada directorio generado.
- `mkdir -p Usac/Practicas/Reportes`: Creó una estructura jerárquica de subcarpetas anidadas de forma automática mediante la opción `-p` (parents).

Para finalizar, se ejecutaron comandos `ls` en las rutas creadas para verificar la correcta estructura del árbol de directorios.

![Pasted image 20260820172817.png](../Attachments/Pasted%20image%2020260820172817.png)

### **`mv` (Move)**
---
**Sintaxis:** `mv [opciones] origen destino`
    
 **Variaciones:**
    
   - `mv viejo.txt nuevo.txt`: Renombra un archivo o carpeta.
        
   - `mv archivo.txt /ruta/destino/`: Mueve un archivo a otro directorio.
        
   - `mv -i origen destino`: Solicita confirmación antes de sobrescribir.
        
   - `mv -n origen destino`: No sobrescribe ningún archivo existente en el destino.
        
**Ejemplo práctico:**

Partiendo del directorio `/home/vboxuser/Desktop`, se ejecutó el comando `ls` para verificar los elementos disponibles, observando el archivo `202300834` y la carpeta vacía `Reporte`.

Luego se realizaron las siguientes acciones:
- `mv 202300834 Reporte/`: Trasladó el archivo `202300834` hacia la carpeta destino `Reporte`.
- `ls`: Permitió corroborar que el archivo original ya no figuraba en la ruta actual (`Desktop`).
- `ls Reporte/`: Confirmó la reubicación exitosa del archivo dentro de la carpeta `Reporte`.

![Pasted image 20260820173250.png](../Attachments/Pasted%20image%2020260820173250.png)

### **`rm` (Remove)**
---
**Sintaxis:** `rm [opciones] archivo/directorio`
    
**Variaciones:**
    
   - `rm archivo.txt`: Elimina un archivo regular.
        
   - `rm -r carpeta/`: Elimina una carpeta y todo su contenido recursivamente.
        
   - `rm -f archivo`: Fuerza la eliminación sin pedir confirmación ni mostrar advertencias.
        
   - `rm -rf carpeta/`: Fuerza la eliminación recursiva de un directorio completo.
        
**Ejemplo práctico:**

Estando ubicados en `/home/vboxuser/Desktop`, se comprobó con `ls` la existencia del archivo `202300834` y del directorio `Reporte` (el cual contenía un archivo interno).

A continuación, se llevaron a cabo los siguientes pasos:
- `rm 202300834`: Eliminó de forma permanente el archivo regular especificado.
- `ls`: Sirvió para confirmar que el archivo `202300834` había sido removido del directorio actual.
- `ls Reporte/`: Verificó el contenido existente dentro de la carpeta antes de su eliminación.
- `rm -r Reporte/`: Eliminó la carpeta `Reporte` junto con todo su contenido interno de manera recursiva.
- `ls`: Confirmó de forma definitiva la eliminación total de los archivos y directorios previamente trabajados.

![Pasted image 20260820173723.png](../Attachments/Pasted%20image%2020260820173723.png)
### **`rmdir` (Remove Directory)**
---
**Sintaxis:** `rmdir [opciones] directorio`
    
**Variaciones:**
    
   - `rmdir carpeta`: Elimina un directorio **únicamente si está vacío**.
        
   - `rmdir -p padre/hijo`: Elimina carpetas vacías anidadas de forma jerárquica.
        
   - `rmdir -v carpeta`: Muestra un mensaje procesando la eliminación.
        
**Ejemplo práctico:**

Partiendo del directorio `/home/vboxuser/Desktop`, se ejecutó el comando `ls` para verificar los elementos del área de trabajo, observando la carpeta `Reporte` y el directorio `Usac` (el cual contenía la subcarpeta `Practicas`).

A continuación, se realizaron los siguientes pasos:
- `ls Reporte/`: Verificó que la carpeta `Reporte` se encontraba completamente vacía.
- `ls Usac/` y `ls Usac/Practicas/`: Inspeccionaron la estructura jerárquica para corroborar que `Practicas` no contenía archivos.
- `rmdir Reporte/`: Eliminó exitosamente el directorio `Reporte` al no contener elementos.
- `rmdir -p Usac/Practicas/`: Eliminó de forma descendente la subcarpeta `Practicas` y su directorio padre `Usac`, ya que ambos quedaron vacíos en la cadena.

> **Nota:** El comando `rmdir` es aplicable exclusivamente a directorios vacíos. Para remover carpetas con contenido, es necesario recurrir a `rm -r`.

![Pasted image 20260820180148.png](../Attachments/Pasted%20image%2020260820180148.png)