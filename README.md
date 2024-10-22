# 🛠️ Instalación de Odoo con Docker Compose

## Requisitos
- Tener instalados **Docker** y **Docker Compose** en tu sistema.

## Pasos para la instalación

### 1. Duplicar y renombrar archivos clave
Asegúrate de tener los siguientes archivos en la raíz del proyecto:
- `docker-compose.yaml`
- Cambiar `a.env`->`.env`
- `config/odoo.conf`

### 2. Configuración del archivo `.env`
- Define los parámetros específicos de tu instancia, como las credenciales de la base de datos y los puertos de red.

### 3. Configuración del archivo `config/odoo.conf`
- Asegúrate de que los parámetros de base de datos, como `DB_HOST`, `DB_PASSWD` y `DB_USER`, estén alineados con los valores establecidos en el archivo `.env`.
- **⚠️ Importante**: **EN UN ENTORNO DE PRODUCCION**, el valor de `ADMIN_PASSWD` debe ser seguro, ya que este controla la gestión de las bases de datos.
- 
## La estructura te debe quedar algo asi:
odoo/
├── docker-compose.yaml
├── .env
├── config/
|  └── odoo.conf
└── addons/ # esta carpeta se creará despues de la primera inicialización

### 4. Ejecución de Docker Compose
1. Abre una terminal en la raíz del proyecto donde está el archivo `docker-compose.yaml`.
2. Ejecuta el siguiente comando para levantar los servicios:
   ```bash
   docker-compose up -d
   ```
   ### Ejecución de Docker Compose (continuación)
- **Primera ejecución**:
  - Descargarás las imágenes de Odoo y PostgreSQL, lo que podría demorar varios minutos.
  
- **Ejecuciones posteriores**:
  - El arranque será mucho más rápido (solo unos segundos).

### 5. Acceder a Odoo
- El puerto web (`WEB_PORT`) que definiste en el archivo `.env` se utilizará para acceder a Odoo.
- Ingresa a Odoo a través de `http://localhost:<WEB_PORT>`.
- Si es tu primera vez accediendo, se te pedirá que crees una nueva base de datos a través de un formulario.

## Solución de Problemas
- **Error de conexión a la base de datos**: Asegúrate de que los parámetros en `.env` coincidan con los configurados en `odoo.conf`.
- **Tiempo de arranque prolongado**: La primera ejecución puede tardar más debido a la descarga de imágenes. Revisa tu conexión a Internet.

## Licencia
Este proyecto está bajo la MIT License. Para más detalles, consulta el archivo `LICENSE`.

---

✨ ¡Ahora tienes todo listo para empezar con Odoo!
