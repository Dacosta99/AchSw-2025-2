# Entregable - Laboratory 1 (SwArch2025ii)

**Nombre completo:** Danny Marcelo Yaluzan Acosta

## 1) Representación gráfica (diagrama simple)
Arquitectura monolítica con dos componentes principales:
- swarch-mo (monolito Flask)
- swarch-db (MySQL)

Diagrama (ASCII):
```
+----------------------+          +----------------------+
|   swarch-mo (Flask)  | <------> |   swarch-db (MySQL)  |
|  - controllers       |          |  - base de datos     |
|  - services          |          +----------------------+
|  - repositories     |
|  - templates         |
+----------------------+
```

## 2) Descripción de cinco (5) propiedades del sistema

1. **Modificabilidad**: El sistema se organiza en capas (controllers -> services -> repositories -> models -> templates). Esta separación facilita cambios locales (por ejemplo, cambiar la lógica de negocio en services) sin tocar la interfaz web o el acceso a datos directamente.

2. **Portabilidad**: Al contenerse en imágenes Docker, el sistema puede desplegarse en distintas máquinas que soporten Docker con mínima configuración (solo variables de entorno para la base de datos).

3. **Observabilidad / Testabilidad**: Al ser una aplicación modular (módulos separados por responsabilidades), es sencillo añadir pruebas unitarias a services y repositories. Además, el uso de SQLAlchemy facilita la creación de bases de datos temporales para tests.

4. **Consistencia de datos**: El uso de una base de datos relacional (MySQL) y transacciones en los repositorios asegura que las operaciones de escritura sean atómicas (commit/rollback), manteniendo la integridad de la tabla `grades`.

5. **Simplicidad / Comprensibilidad**: La arquitectura monolítica y la elección de Flask y SQLAlchemy hacen que el código sea compacto y fácil de entender para un primer acercamiento a conceptos arquitectónicos.

---
**Notas**: El proyecto incluye el código fuente, Dockerfile y docker-compose.yml tal como se solicita en el documento del laboratorio. Asegúrese de reemplazar el campo "Nombre completo" por su nombre antes de entregar.
