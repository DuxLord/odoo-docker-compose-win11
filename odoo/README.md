# 🛠️ Instalación de Odoo con Docker Compose

## Requisitos
- Tener instalados **Docker** y **Docker Compose** en tu sistema.

## Pasos para la instalación

### 1. Duplicar y renombrar archivos clave
Asegúrate de tener los siguientes archivos en la raíz del proyecto:
- `docker-compose.yaml`
- Cambiar de `a.env`->`.env`
- `config/odoo.conf`

### 2. Configuración del archivo `.env`
- Define los parámetros específicos de tu instancia, como las credenciales de la base de datos y los puertos de red.

### 3. Configuración del archivo `config/odoo.conf`
- Asegúrate de que los parámetros de base de datos, como `DB_HOST`, `DB_PASSWD` y `DB_USER`, estén alineados con los valores establecidos en el archivo `.env`.
- **⚠️ Importante**: **EN UN ENTORNO DE PRODUCCION**, el valor de `ADMIN_PASSWD` debe ser seguro, ya que este controla la gestión de las bases de datos.

### 4. Ejecución de Docker Compose
1. Abre una terminal en la raíz del proyecto donde está el archivo `docker-compose.yaml`.
2. Ejecuta el siguiente comando para levantar los servicios:
   ```bash
   docker-compose up -d
   ```
   ### 4. Ejecución de Docker Compose (continuación)

- **Primera ejecución**: 
  - Descargarás las imágenes de Odoo y PostgreSQL, lo que podría demorar varios minutos.
  
- **Ejecuciones posteriores**: 
  - El arranque será mucho más rápido (solo unos segundos).

### 5. Acceder a Odoo
- El puerto web (`WEB_PORT`) que definiste en el archivo `.env` se utilizará para acceder a Odoo.
- Ingresa a Odoo a través de `http://localhost:<WEB_PORT>`.
- Si es tu primera vez accediendo, se te pedirá que crees una nueva base de datos a través de un formulario.

---

✨ ¡Ahora tienes todo listo para empezar con Odoo!
