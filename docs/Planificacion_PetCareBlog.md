# 🧩 Planificación simple para crear el blog "PetCare Blog"

**Objetivo:** construir un blog básico de bienestar animal con HTML, CSS
y JavaScript, conectado a un backend en Java (Spring Boot) y base de
datos PostgreSQL.

------------------------------------------------------------------------

## 🏗️ 1. Estructura inicial (frontend estático)

-   Crear una carpeta raíz llamada `petcare-blog/`.
-   Dentro, crear:
    -   `/index.html` → página principal del blog.\
    -   `/style.css` → estilos generales.\
    -   `/script.js` → lógica del lado del cliente.\
    -   `/img/` → imágenes y logo del blog.

### HTML

-   Estructura básica con `<header>`, `<main>`, `<footer>`.
-   Incluir secciones: "Inicio", "Artículos", "Sobre Nosotros",
    "Contacto".
-   Añadir contenedor para mostrar posts cargados dinámicamente con JS.

### CSS

-   Diseñar un estilo limpio: colores suaves (verde menta, blanco,
    beige).
-   Usar `flexbox` o `grid` para distribuir las tarjetas de artículos.

### JavaScript

-   Crear función `getPosts()` que consulte la API REST del backend.
-   Mostrar los artículos en tarjetas dentro del `main`.

------------------------------------------------------------------------

## ⚙️ 2. Backend con Java (Spring Boot)

-   Crear proyecto con Spring Initializr con dependencias:
    -   **Spring Web**, **Spring Data JPA**, **PostgreSQL Driver**,
        **Lombok**, **Spring Boot DevTools**.
-   Crear las capas:
    -   `model/` → clase `Post.java` con campos `id`, `title`,
        `content`, `author`, `date`.
    -   `repository/` → interfaz `PostRepository`.
    -   `controller/` → `PostController` con endpoints REST:
        -   `GET /posts` → listar artículos.
        -   `POST /posts` → crear artículo.
        -   `DELETE /posts/{id}` → eliminar artículo.

### Configuración de conexión en `application.properties`

``` properties
spring.datasource.url=jdbc:postgresql://localhost:5432/petcare_db
spring.datasource.username=postgres
spring.datasource.password=tu_password
spring.jpa.hibernate.ddl-auto=update
```

------------------------------------------------------------------------

## 🐘 3. Base de datos PostgreSQL

-   Crear base de datos `petcare_db`.
-   Tabla `posts` generada automáticamente por JPA.

------------------------------------------------------------------------

## 🌐 4. Integración frontend-backend

-   En `script.js`, usar `fetch('http://localhost:8080/posts')` para
    obtener los artículos.
-   Mostrar los resultados en tarjetas HTML.
-   Permitir agregar nuevos artículos desde un formulario simple.

------------------------------------------------------------------------

## 🚀 5. Despliegue

-   Ejecutar el backend (`mvn spring-boot:run`).
-   Servir el frontend con `Live Server` o incluirlo en
    `resources/static` de Spring.
-   Probar conexión completa: frontend → backend → PostgreSQL.
