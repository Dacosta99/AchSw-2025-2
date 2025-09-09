# SwArch - Laboratory 1
Estructura del proyecto para el laboratorio 1 (SwArch2025ii).

## Cómo ejecutar (localmente con Docker)
1. Tener Docker y docker-compose instalados.
2. Construir y levantar contenedores:
   ```bash
   docker-compose up --build
   ```
3. Abrir en el navegador: http://localhost:8080
4. Usuario: (no hay autenticación). Para inspeccionar la base de datos:
   ```bash
   docker exec -it <container_name> sh
   mysql -u root -p
   Password = 123
   USE swarch-db;
   SELECT * FROM grades;
   ```
