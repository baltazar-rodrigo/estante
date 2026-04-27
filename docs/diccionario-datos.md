# Diccionario de Datos - DBMS Estante

Este documento detalla la estructura lógica del sistema, definiendo los tipos de datos y restricciones de integridad del motor de base de datos.

## Tabla: LIBROS (Entidad de Almacenamiento)
| Campo | Tipo | Descripción | Restricciones |
|---|---|---|---|
| `id_libro` | INT | Identificador único del registro. | PK, NOT NULL, AUTOINCREMENT |
| `isbn` | VARCHAR(13) | Código internacional único. | UNIQUE, NOT NULL |
| `titulo` | VARCHAR(200) | Título almacenado en el buffer. | NOT NULL |

## Tabla: PRESTAMOS (Entidad Transaccional)
| Campo | Tipo | Descripción | Restricciones |
|---|---|---|---|
| `id_prestamo` | INT | ID de la transacción. | PK, NOT NULL |
| `id_libro` | INT | Puntero a la tabla LIBROS. | FK, NOT NULL |
| `fecha_inicio` | DATE | Registro de tiempo de la operación. | NOT NULL |