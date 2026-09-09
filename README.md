<h1 align="center"> 💬 ForoHub 🗣️ </h1>

<p align="center">
  <img width="400" height="350" alt="amigo secreto" src="src/main/java/com/andromeda/forohub/assets/foro.png" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/STATUS-Finished-brightgreen?style=for-the-badge"> &nbsp;
  <img src="https://img.shields.io/badge/springboot-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white" alt="Spring Boot"> &nbsp; 
  <img src="https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java"> &nbsp; 
  <img src="https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white" alt="Database"> &nbsp;
  <img src="https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens" alt="JWT Token"> &nbsp;
</p>

---

## 📝 Descripción del Proyecto

ForoHub es una API REST desarrollada con Spring Boot que simula el funcionamiento de un foro de discusión técnico. 
El proyecto implementa la persistencia de datos en una base de datos relacional y utiliza JWT (JSON Web Tokens) para asegurar que solo usuarios autenticados puedan interactuar con la plataforma. 

Este proyecto forma parte del programa **Oracle Next Education (ONE)**.

---

## 🛠️ Tecnologías utilizadas

- Java 21
- Spring Boot 3
- Spring Security
- Spring Data JPA
- Auth0 JWT
- MySQL
- Flyway
- Lombok
- Maven
---

## 🚀 Características

- Autenticación Stateless: Seguridad con JWT para manejo de sesiones sin estado.
- Persistencia: Gestión de datos con MySQL y Spring Data JPA.
- Migraciones: Control de versiones de base de datos con Flyway.
- Seguridad: Protección de rutas con Spring Security y encriptación BCrypt.
- Arquitectura: Organización clara mediante Controladores, Servicios, DTOs y Repositorios.
- Manejo de Errores: Tratamiento centralizado de excepciones.

---

## 🔐 Seguridad y Autenticación

El sistema utiliza un esquema de seguridad Stateless (sin estado).

- **Registro:** Los usuarios se registran y su contraseña se almacena de forma segura mediante BCrypt hashing.
- **Login:** El usuario envía sus credenciales y, si son válidas, la API devuelve un Token JWT.
- **Autorización:** Para acceder a rutas protegidas, el usuario debe enviar el token en el encabezado Authorization.

---
## 📋 Endpoints Principales

### Autenticación (Público):

- `POST /login:` Recibe email/password y devuelve el JWT.
- `POST /users:` Registro de nuevos usuarios.

### Gestión de Tópicos (Protegido):

- `GET /topics:` Lista todos los tópicos del foro(soporta paginación y ordenamiento).
- `GET /topics/{id}:` Detalle de un tópico específico y sus respuestas.
- `POST /topics:` Creación de un nuevo hilo de discusión.
- `PUT /topics/{id}:` Actualización de título o mensaje de un tópico propio.
- `DELETE /topics/{id}:` Eliminación de un tópico.

## Gestión de Cursos y Usuarios (Protegido)
  
- `GET /courses:` Lista de cursos disponibles.
- `POST /courses:` Registro de nuevos cursos.
- `POST /responses:` Envía una solución o comentario a un tópico específico:

---

## ▶️ Ejecución

1. **Clonar el repositorio:**

   ```bash
   git clone https://github.com/tu-usuario/forohub.git
   ```

1. **Configurar la Base de Datos:**

   - Crea una base de datos en MySQL llamada `forohub`.

   - Configura tus credenciales en el archivo `src/main/resources/application.properties`:

      ```properties
      spring.datasource.url=tu_url
      spring.datasource.username=tu_usuario
      spring.datasource.password=tu_contraseña
      api.security.secret=${JWT_SECRET:tu_codigo}
      ```
  
1. **Ejecutar las Migraciones:**

   - Al iniciar la aplicación, Flyway creará automáticamente las tablas necesarias.

1. **Correr la aplicación:**

   - Usa tu IDE (IntelliJ/Eclipse) o ejecuta:

      ```bash
     mvn spring-boot:run
     ```

---

## 📂 Estructura del Proyecto

- `controller`: Puntos de entrada para Cursos, Respuestas, Tópicos y Usuarios.
- `dto:` Clases Record para la transferencia de datos segura y validada.
- `exceptions:` Manejo global de errores y excepciones personalizadas.
- `infra.security:` El núcleo de seguridad (JWT Service, Filtros y Configuraciones).
- `model`: Entidades JPA.
- `repository:` Interfaces para la comunicación con la base de datos.
- `service:` Lógica de negocio.

## 👤 Autor

| [<img src="https://github.com/user-attachments/assets/ed62fad0-2a7e-4029-8525-2eec5c620be3" width="155"><br><sub>Andrio Contreras</sub>](https://github.com/DranxFa) |
| :---: |

---

## 📌 Estado del Proyecto

✅ Finalizado — abierto a mejoras o nuevas versiones.
