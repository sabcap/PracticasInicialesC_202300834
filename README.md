# Reporte 3: Práctica Inicial de Linux y Servicios Web

**Universidad de San Carlos de Guatemala**  
**Facultad de Ingeniería**  
**Escuela de Ciencias y Sistemas (ECYS)**  
**Prácticas Iniciales - Sección C**  

---

### Datos del Estudiante
- **Nombre:** Josué Javier Carrera Soyós
- **Carné:** 202300834
- **Fecha:** 20 de agosto de 2026

---

## Introducción

Este repositorio contiene la documentación técnica y las actividades prácticas correspondientes a la introducción del sistema operativo Linux y la administración de servicios en la nube. A través de este proyecto se aborda el ciclo completo de aprovisionamiento de un entorno virtualizado utilizando **VirtualBox**, el dominio de la interfaz de línea de comandos (CLI) para la gestión del sistema de archivos, y el despliegue funcional de un servidor web **Apache2**.

El propósito de esta documentación es brindar una guía estructurada y clara tanto para la consulta técnica de comandos esenciales como para la verificación paso a paso del flujo de instalación y configuración de servicios en entornos Linux.

---

## Estructura y Contenido del Reporte

El reporte se organiza en tres documentos principales que detallan las diferentes etapas de la práctica:

1. **[Manual Técnico](Manual.md)**  
   Documento consolidado que reúne la guía completa del proyecto. Incluye los objetivos generales y específicos, la explicación detallada del entorno de virtualización en VirtualBox, la guía teórica y práctica de comandos CLI, el procedimiento de instalación y edición del servidor Apache2, y las conclusiones finales.

2. **[Actividad 1: Instalación de Ubuntu y Comandos Iniciales](Actividades/Actividad1.md)**  
   Documento centrado en las primeras pruebas en la terminal de Linux. Contiene ejemplos prácticos paso a paso para comandos de navegación (`pwd`, `cd`), listado (`ls`) y manipulación de archivos y directorios (`cp`, `mkdir`, `mv`, `rm`, `rmdir`), acompañados de notas técnicas sobre tipos de rutas, enlaces simbólicos y permisos.

3. **[Actividad 2: Despliegue de Servidor Apache2](Actividades/Actividad2.md)**  
   Documento enfocado en la administración de servicios web. Detalla la actualización de repositorios con `apt update` y `apt upgrade`, la instalación de Apache2, la gestión del servicio mediante `systemctl`, la edición del archivo `index.html` con `nano` y la verificación de cambios en el navegador web.

---

## Organización de Archivos y Multimedia

- **`Attachments/`**: Carpeta que almacena las capturas de pantalla y evidencias visuales activas utilizadas en los documentos Markdown.

---

## Entorno Técnico Utilizado

- **Sistema Operativo:** Ubuntu 24.04 LTS (64 bits)
- **Hipervisor:** Oracle VM VirtualBox
- **Servidor Web:** Apache2 (`apache2.service`)
- **Editor de Texto en Terminal:** GNU nano
