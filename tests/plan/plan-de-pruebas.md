# Plan de Pruebas - Proyecto Estante

## 1. Objetivo
Garantizar que el gestor de base de datos realice correctamente las operaciones CRUD (Crear, Leer, Actualizar, Borrar) y mantenga la integridad de los datos al conectar con diferentes motores mediante JDBC.

## 2. Alcance
### En alcance
- Validación de la conexión JDBC con SQLite y MySQL.
- Verificación de la persistencia de datos en el archivo físico.
- Pruebas de la interfaz gráfica en JavaFX (validación de formularios).

### Fuera de alcance
- Pruebas de carga masiva (más de 5,000 registros simultáneos).
- Compatibilidad con sistemas operativos antiguos (Windows 7 o anteriores).

## 3. Tipos de prueba
- [x] Unitarias
- [x] Integración
- [x] Funcionales manuales
- [ ] Rendimiento
- [x] Seguridad
- [x] Regresión

## 4. Entornos

| Entorno | SO | Versión |
|---|---|---|
| Local | Windows 10/11 | Java 17 / JDBC 4.2 |
| CI | Ubuntu latest | GitHub Actions |

## 5. Responsables

| Rol | Responsable |
|---|---|
| Diseño de casos | Rodrigo Baltazar Borras |
| Ejecución manual | Rodrigo Baltazar Borras |
| Automatización | Rodrigo Baltazar Borras |
| Reporte | Rodrigo Baltazar Borras |

## 6. Criterios de salida
- [x] Cobertura mínima de 80% de los métodos principales.
- [x] Cero bugs críticos abiertos en la conexión JDBC.
- [x] Todos los casos de prueba base ejecutados satisfactoriamente.

## 7. Riesgos

| Riesgo | Probabilidad | Impacto | Mitigación |
|---|---|---|---|
| Incompatibilidad de Driver JDBC | Media | Alto | Usar versiones estables y documentadas en el Glosario. |
| Corrupción de archivo de datos | Baja | Muy Alto | Implementar cierres de conexión seguros en los métodos. |
| Errores en la interfaz JavaFX | Media | Medio | Realizar pruebas manuales de validación de campos. |