# Modelo de Datos - Proyecto Estante

Este documento describe la estructura lógica y el modelo entidad-relación del gestor de base de datos del sistema.

## 1. Entidades Principales y Atributos

### Entidad: Tabla
Representa la estructura base donde se organiza la información.
* **id_tabla** (INT): Clave Primaria (PK). Identificador único.
* **nombre** (VARCHAR): Nombre descriptivo de la tabla.
* **fecha_creacion** (DATETIME): Fecha y hora de creación.
* **ubicacion_archivo** (VARCHAR): Ruta física donde se almacena el archivo de datos.

### Entidad: Registro (Fila)
Representa los datos individuales almacenados dentro de una tabla.
* **id_registro** (INT): Clave Primaria (PK). Identificador único de fila.
* **id_tabla** (INT): Clave Foránea (FK). Vincula el registro con su tabla correspondiente.
* **contenido** (TEXT): Datos específicos almacenados en la fila.

## 2. Relaciones entre Entidades

* **Relación Tabla - Registro (Uno a Muchos / 1:N):** Una **Tabla** puede contener múltiples **Registros**, pero cada **Registro** pertenece obligatoriamente a una sola **Tabla**. La integridad se mantiene mediante el campo `id_tabla` en la entidad Registro.

## 3. Resumen de Claves y Tipos

| Entidad | Clave Primaria (PK) | Clave Foránea (FK) | Descripción de Relación |
| :--- | :--- | :--- | :--- |
| **Tabla** | id_tabla | No aplica | Entidad maestra. |
| **Registro** | id_registro | id_tabla | Depende de la entidad Tabla. |

