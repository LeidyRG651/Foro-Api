


 Foro Hub - API
La API de Foro Hub permite realizar una gestión de temas para la plataforma For Hub, facilitando la interacción y administración de tópicos entre usuarios.

Tecnologías Implementadas
Java para el backend
MySQL como base de datos relacional
Seguridad mediante JWT y cifrado de contraseñas con BCrypt
Swagger para la documentación y prueba de la API
Configuración de propiedades en archivos .yml
Pruebas y solicitudes realizadas con Insomnia o Postman
Rutas Principales
Autenticación: http://localhost:8080/login
Documentación Swagger: http://localhost:8080/swagger-ui/index.html#/
Endpoint Base para Tópicos: http://localhost:8080/topico
Configuración de Entorno
Requisitos Iniciales
Es necesario tener instalados los siguientes programas:

JDK versión 21 o superior
Servidor MySQL
Un IDE, preferentemente IntelliJ IDEA
Postman o Insomnia para pruebas de API
Clonación del Proyecto
Para obtener el código, clona el repositorio con:

bash
Copiar código
git clone https://github.com/marbello1973/Foro-Hub-BackEnd.git
cd Foro-Hub-BackEnd
Configuración de la Base de Datos
Crea una base de datos en MySQL llamada forohubdb.
Define las credenciales de acceso en el archivo application.yml.
Para ejecutar el proyecto, configura la conexión con estos parámetros en tu archivo application.yml:
yaml
Copiar código
spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost/forohub
    username: root
    password: tu_contraseña
Acceso y Pruebas
Para consultar la documentación de la API, accede a Swagger UI:

http://localhost:8080/swagger-ui/index.html#/

Seguridad de la API
Autenticación basada en JWT y encriptación de contraseñas con BCrypt.
Puedes iniciar sesión con el correo david@gmail.com y la contraseña 123456 para pruebas.
Asegúrate de incluir el token JWT en los headers para todas las solicitudes protegidas.
Principales Endpoints
Consultar todos los temas

http
Copiar código
GET /topicos
Parámetros	Tipo	Descripción
No	GET	Se requiere autenticación
Consultar un tema por ID

http
Copiar código
GET /topico/${id}
Parámetros	Tipo	Descripción
id	GET	Autenticación requerida; pasar ID en la URL
Crear un nuevo tema

http
Copiar código
POST /topico
Parámetros	Tipo	Descripción
No	POST	Requiere autenticación
Modificar un tema existente

http
Copiar código
PUT /topico/${id}
Parámetros	Tipo	Descripción
No	PUT	Requiere autenticación; ID en el cuerpo JSON
Desactivar un tema

http
Copiar código
DELETE /topico/${id}
Parámetros	Tipo	Descripción
id	DELETE	Requiere autenticación; ID en la URL
