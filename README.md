# 🎬 API RESTful de Pruebas: Catálogo de Películas

Esta es una **API de prueba (Mock API)** para practicar peticiones HTTP (CRUD) usando [JSON Server](https://www.npmjs.com/package/json-server). Contiene un catálogo de **más de 150 películas** con datos como director, año, rating y taquilla.

Es una herramienta ideal para desarrolladores que necesiten un *backend* funcional y fácil de usar para proyectos de frontend (React, Vue, Angular) o para practicar *testing* con herramientas como Postman o cURL.

## 🛠️ Prerrequisitos

Asegúrate de tener instalado:

* **Node.js** (v16 o superior)
* **npm** (Gestor de paquetes de Node)
* Un cliente HTTP (Postman, Insomnia o cURL)

## 🚀 Instalación y Uso Local

Sigue estos pasos para poner la API en funcionamiento en tu máquina local en menos de un minuto.

1.  **Clona el repositorio:**
    ```bash
    git clone [URL_DE_TU_REPOSITORIO]
    cd peliculas-api-test
    ```

2.  **Instala las dependencias:**
    ```bash
    npm install
    ```

3.  **Inicia el servidor de prueba:**
    ```bash
    npm run start:api
    ```
    El servidor se iniciará en modo "watch" (vigilancia), lo que significa que los cambios de `POST/PUT/DELETE` se guardarán en el archivo `db.json` localmente.

4.  **Verificación:**
    Abre tu navegador y navega a: `http://localhost:3000/peliculas`

## 🔗 Endpoints Principales

La API expone dos colecciones principales: `/peliculas` y `/directores`.

### Operaciones CRUD en `/peliculas`

| Método | URL de la Petición | Cuerpo (Body) | Propósito de Testing |
| :--- | :--- | :--- | :--- |
| **GET** | `/peliculas` | N/A | Obtener el listado completo (más de 150 recursos). |
| **GET** | `/peliculas/1` | N/A | Obtener los detalles de una película por su ID. |
| **POST** | `/peliculas` | JSON de la nueva película. | Crear un nuevo recurso (la respuesta será **201 Created**). |
| **PUT** | `/peliculas/1` | JSON con **todos los campos** actualizados. | Reemplazar completamente un recurso. |
| **PATCH** | `/peliculas/1` | JSON solo con el campo a cambiar (ej: `{"rating": 9.4}`). | **Actualizar parcialmente** un recurso (ideal para probar *endpoints*). |
| **DELETE** | `/peliculas/1` | N/A | Eliminar un recurso de la base de datos de prueba. |

### Ejemplos de Filtros y Consultas (Query Parameters)

JSON Server soporta filtrado avanzado automáticamente.

| Funcionalidad | Método | URL de Ejemplo |
| :--- | :--- | :--- |
| **Búsqueda por Director** | `GET` | `/peliculas?director=Christopher Nolan` |
| **Rating Mínimo** | `GET` | `/peliculas?rating_gte=9.0` |
| **Rango de Año (1990-1999)** | `GET` | `/peliculas?anio_gte=1990&anio_lte=1999` |
| **Ordenar por Taquilla (Descendente)** | `GET` | `/peliculas?_sort=taquilla_millones&_order=desc` |

## 🌟 Licencia

Este proyecto está disponible bajo la **Licencia MIT**. Siéntete libre de usarlo, modificarlo y compartirlo en tus proyectos personales y comerciales.