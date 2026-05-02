# Diccionario de Datos - Sistema Estante

Este documento detalla la estructura de la base de datos para el proyecto Estante, definiendo tipos de datos, longitudes y restricciones de integridad.

## Tabla: LIBROS
Almacena la información bibliográfica de los textos disponibles en el sistema.

| Nombre Campo | Tipo de Dato | Descripción | Restricciones |
| :--- | :--- | :--- | :--- |
| `id_libro` | INT | Identificador único del libro. | PK, AUTO_INCREMENT |
| `isbn` | VARCHAR(13) | Código internacional normalizado. | UNIQUE, NOT NULL |
| `titulo` | VARCHAR(255) | Título completo de la obra. | NOT NULL |
| `autor` | VARCHAR(150) | Nombre del autor principal. | NOT NULL |
| `id_categoria` | INT | Referencia a la categoría. | FK |

## Tabla: PRESTAMOS
Registra las transacciones de libros entre la biblioteca y los usuarios.

| Nombre Campo | Tipo de Dato | Descripción | Restricciones |
| :--- | :--- | :--- | :--- |
| `id_prestamo` | INT | Identificador de la transacción. | PK, AUTO_INCREMENT |
| `id_libro` | INT | Libro objeto del préstamo. | FK, NOT NULL |
| `fecha_salida` | DATE | Fecha en que se entrega el libro. | NOT NULL |
| `fecha_devolucion` | DATE | Fecha pactada de retorno. | NOT NULL |
| `estado` | VARCHAR(20) | Estado del préstamo (Activo, Devuelto). | DEFAULT 'Activo' |

## Tabla: CATEGORIAS
Clasificación lógica de los libros.

| Nombre Campo | Tipo de Dato | Descripción | Restricciones |
| :--- | :--- | :--- | :--- |
| `id_categoria` | INT | Identificador de la categoría. | PK, AUTO_INCREMENT |
| `nombre` | VARCHAR(100) | Nombre de la categoría (Ingeniería, etc.) | NOT NULL |