Este manual incluye los pasos para configurar un backend Symfony con una base de datos y soluciona problemas comunes encontrados durante el proceso.

---

## 1. **Cargar el Script de la Base de Datos**

### Paso 1: Ejecutar el Script SQL

Si tienes un script SQL para inicializar la base de datos:

1. Abre **HeidiSQL** o el gestor de bases de datos de tu elección.
2. Importa el archivo `.sql` ejecutando el script.

---

## 2. **Instalar Dependencias Necesarias para Symfony**

### Verificar Instalaciones Básicas

Asegúrate de que PHP y Composer estén instalados. Usa:

```bash
php -v
composer -v

```
![alt text](image.png)
![alt text](image-1.png)

### Instalar Extensiones PHP Requeridas

Algunos paquetes de Symfony requieren extensiones específicas como `ext-xml`. Para instalarlas, ejecuta:

```bash
sudo apt-get install php8.3-xml

```

En caso de errores con Postfix u otros paquetes, puedes modificar su configuración (ver troubleshooting abajo).

---

## 3. **Configurar Symfony y Conexión con la Base de Datos**

### Verificar Archivo `.env`

El archivo `.env` debe contener la configuración de la base de datos. Por ejemplo:

```
DATABASE_URL="mysql://usuario:password@127.0.0.1:3306/nombre_base_datos"

```

Corrige errores como valores con espacios sin comillas (" ").

### Instalar Dependencias del Proyecto

Ejecuta:

```bash
composer install

```
![alt text](image-2.png)

Si encuentras problemas con `symfony/runtime`, instálalo manualmente:

```bashca
composer require symfony/runtime

```

---

## 4. **Comprobar el Estado de la Base de Datos**

### Validar el Esquema de la Base de Datos

Usa el siguiente comando para asegurarte de que los mapeos y la base de datos estén sincronizados:

```bash
php bin/console doctrine:schema:validate

```

Resultado esperado:

```
Mapping
-------
 [OK] The mapping files are correct.

Database
--------
 [OK] The database schema is in sync with the mapping files.

```
![alt text](image-3.png)

### Probar Conexión a la Base de Datos

Puedes ejecutar una consulta SQL simple:

```bash
php bin/console doctrine:query:sql "SELECT 1"

```

Resultado esperado:

```
 ---
  1
 ---
  1
 ---

```


Esto confirma que Symfony está conectado correctamente a la base de datos.

---

![alt text](image-4.png)
## 5. **Troubleshooting**

### Problema 1: `symfony/runtime` faltante

**Error:**

```
Symfony Runtime is missing. Try running "composer require symfony/runtime".

```

**Solución:**
Ejecuta:

```bash
composer require symfony/runtime

```

Si hay conflictos de dependencias, asegúrate de instalar todas las extensiones requeridas (como `php-xml`).

### Problema 2: Extensiones PHP faltantes

**Error:**

```
requires ext-xml * -> it is missing from your system. Install or enable PHP's xml extension.

```

**Solución:**

Instala la extensión faltante. Por ejemplo, para `ext-xml`:

```bash
sudo apt-get install php8.3-xml

```

Si el error persiste, verifica las extensiones habilitadas:

```bash
php --ini

```

Confirma que la extensión aparece en los archivos `.ini` cargados.

### Problema 3: `doctrine:database:connect` no existe

**Error:**

```
Command "doctrine:database:connect" is not defined.

```

**Solución:**
El comando no está disponible en Symfony. Usa en su lugar:

```bash
php bin/console doctrine:query:sql "SELECT 1"

```

Esto verifica la conexión a la base de datos.

### Problema 4: `.env` mal configurado

**Error:**

```
A value containing spaces must be surrounded by quotes

```

**Solución:**
Edita el archivo `.env` y asegúrate de que los valores con espacios estén entre comillas:

```
DATABASE_URL="mysql://usuario:password@127.0.0.1:3306/nombre_base_datos"

```

### Problema 5: Clase "App\Kernel" no encontrada

**Error:**

```
Class "App\Kernel" not found

```

**Solución:**
Confirma que el archivo `Kernel.php` existe en `src/`. Si no, recrea el archivo o verifica que el autoload esté actualizado:

```bash
composer dump-autoload

```

---

## 6. **Notas Finales**

- Siempre verifica los logs para más detalles de errores.
- Usa `php bin/console` para listar todos los comandos disponibles.
- Si necesitas reinstalar dependencias, puedes ejecutar:

```bash
composer install

```