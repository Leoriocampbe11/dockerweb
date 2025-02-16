# Manual: Servir un Frontend Estático con `npx http-server`

Este manual explica cómo ejecutar un frontend estático localmente usando `npx http-server`, sin necesidad de instalar nada globalmente.

---

## **1. Prerrequisitos**
Antes de comenzar, asegúrate de tener instalado Node.js y npm en tu sistema. Para verificarlo, ejecuta:

```bash
node -v  # Verifica la versión de Node.js
npm -v   # Verifica la versión de npm
```
Si no están instalados, descárgalo desde [Node.js](https://nodejs.org/).

---

## **2. Descargar y Extraer el Frontend**
Si el frontend está comprimido en un archivo `.zip`, sigue estos pasos:

1. Descarga el archivo `front_modified.zip`.
2. Extrae el contenido en una carpeta de tu elección.
3. Abre una terminal y navega hasta esa carpeta:
   
   ```bash
   cd /ruta/del/frontend-extraido
   ```

---

## **3. Iniciar el Servidor con `npx`**
Para servir los archivos estáticos sin instalar nada, usa el siguiente comando:

```bash
npx http-server -p 8080
```

Esto iniciará un servidor web en el puerto `8080`. Si quieres cambiar el puerto, reemplaza `8080` por otro número.

---

## **4. Acceder al Frontend en el Navegador**
Una vez iniciado el servidor, abre tu navegador y visita:

```
http://localhost:8080
```

Si todo está configurado correctamente, deberías ver la interfaz del frontend.

---

## **5. Solución de Problemas**
### Error: `command not found: npx`
Si ves un error indicando que `npx` no está instalado, actualiza npm:

```bash
npm install -g npm
```

### Error: `EADDRINUSE` (Puerto Ocupado)
Si el puerto `8080` está en uso, prueba otro puerto:

```bash
npx http-server -p 9090
```

---

## **6. Detener el Servidor**
Para detener el servidor, presiona `Ctrl + C` en la terminal.

---

Con este método, puedes servir un frontend estático rápidamente sin necesidad de configuraciones adicionales. 🚀

