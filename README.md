# Proyecto de Implementación en AWS

Este repositorio contiene los archivos y documentación relacionados con la implementación de una aplicación web en AWS. Aquí encontrarás manuales, código fuente y configuraciones utilizadas durante el despliegue.

## Estructura del Repositorio

- **aws/**: Contiene el manual de implementación en AWS, que describe los pasos seguidos para desplegar la aplicación en la nube.
- **locales/**: Incluye los archivos y documentación para realizar pruebas en el entorno local. Contiene el código necesario para ejecutar la aplicación en un entorno local y verificar su funcionamiento.
- **backend.zip**: Archivo comprimido con el código fuente del backend, que ha sido subido a AWS para su despliegue.
- **webapp2.zip**: Archivo comprimido con el código fuente del frontend, también subido a AWS.
- **bbd/**: Contiene el script utilizado para ejecutar la base de datos.

## Estado de la Implementación

- Se ha seguido la guía en la carpeta **aws/** para el despliegue en AWS.
- La aplicación ha sido probada en el entorno local utilizando los archivos en la carpeta **locales/**.
- Actualmente, no se ha podido comprobar el correcto funcionamiento de la API Key en la configuración del backend en AWS. Se requiere una validación adicional para asegurar que las credenciales están funcionando correctamente.

## Pasos para Ejecutar en Local
1. Descomprimir el contenido de la carpeta **locales/**.
2. Seguir las instrucciones del manual dentro de la carpeta para configurar y ejecutar el entorno local.
3. Verificar el funcionamiento de la aplicación antes de proceder con cualquier cambio en AWS.

## Pendientes
- Validar la correcta configuración de la API Key en el backend desplegado en AWS.
- Revisar logs y permisos de acceso para garantizar el correcto funcionamiento del backend en la nube.



