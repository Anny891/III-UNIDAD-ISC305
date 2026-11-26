
# III-UNIDAD-ISC305

## API CRUD de Personas con Laravel

### Descripción

Este proyecto consiste en el desarrollo de una API REST utilizando Laravel 13, que permite registrar, consultar, actualizar y eliminar personas mediante peticiones HTTP y respuestas en formato JSON.

La API utiliza MySQL para almacenar los registros y Postman para realizar las pruebas de funcionamiento y validación de datos.

### Tecnologías utilizadas

- Laravel 13
- PHP 8.5
- Composer
- MySQL
- Postman
- Git y GitHub

### Estructura del proyecto

- `backend/`: contiene el proyecto Laravel.
- `postman/`: contiene la colección de pruebas de la API.
- `README.md`: documentación del proyecto.

### Instalación y configuración

1. Clonar el repositorio:

```bash
git clone https://github.com/Anny891/III-UNIDAD-ISC305.git
```

2. Ingresar a la carpeta backend:

```bash
cd III-UNIDAD-ISC305/backend
```

3. Instalar las dependencias:

```bash
composer install
```

4. Crear el archivo `.env` en Windows:

```cmd
copy .env.example .env
```

5. Generar la clave de la aplicación:

```bash
php artisan key:generate
```

6. Crear la base de datos en MySQL:

```sql
CREATE DATABASE api_db;
```

7. Configurar la conexión en el archivo `.env`:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=api_db
DB_USERNAME=root
DB_PASSWORD=
```

Ajustar el usuario y la contraseña según la configuración local de MySQL.

8. Ejecutar las migraciones:

```bash
php artisan config:clear
php artisan migrate
```

9. Iniciar el servidor:

```bash
php artisan serve
```

### Endpoints de la API

| Método | Ruta | Descripción | Código HTTP |
|--------|------|-------------|-------------|
| GET | /api/hola | Mensaje de bienvenida | 200 |
| GET | /api/personas | Listar personas | 200 |
| GET | /api/personas/{id} | Consultar una persona | 200 |
| POST | /api/personas | Registrar una persona | 201 |
| PUT | /api/personas/{id} | Actualizar una persona | 200 |
| DELETE | /api/personas/{id} | Eliminar una persona | 204 |

### Ejemplo de datos JSON

```json
{
    "dni": "0000000000001",
    "nombre": "Ana López",
    "fecha_nacimiento": "2000-05-15"
}
```

### Validaciones implementadas

- El DNI debe contener exactamente 13 dígitos.
- El DNI no puede estar duplicado.
- El nombre es obligatorio y admite hasta 100 caracteres.
- La fecha de nacimiento es obligatoria y no puede ser futura.
- Se permite conservar el DNI al actualizar la misma persona.
- No se permite actualizar una persona con el DNI de otra.

### Códigos de respuesta HTTP

- 200 OK: consulta o actualización exitosa.
- 201 Created: registro creado correctamente.
- 204 No Content: registro eliminado correctamente.
- 404 Not Found: registro no encontrado.
- 422 Unprocessable Entity: error de validación.

### Conceptos aprendidos

- Ruta: permite relacionar una URL y un método HTTP con una operación del sistema.
- Controlador: recibe las peticiones, procesa los datos y devuelve una respuesta.
- Modelo: permite interactuar con los registros de la base de datos.
- Migración: permite definir y crear la estructura de las tablas.
- JSON: formato utilizado para enviar y recibir datos entre aplicaciones.
- Código de estado HTTP: indica el resultado de una petición realizada a la API.

### Conclusión

Mediante esta práctica logré comprender el funcionamiento de una API en Laravel y cómo realizar las operaciones CRUD sin utilizar vistas Blade. También pude comprobar mediante Postman el funcionamiento de las rutas, las validaciones y los diferentes códigos de respuesta HTTP, verificando que los datos se almacenan correctamente en MySQL.

Esta API es una práctica local con datos ficticios y todavía no cuenta con autenticación en sus endpoints.

### Asignatura

ISC-305 Programación Web

III Unidad
