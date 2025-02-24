# CONECIONES-INALAMBRICAS-CON-CISCO
## **Paso 1: Añadir dispositivos**
-  Abrir Cisco Packet Tracer
- Arrastrar un Router inalambrico o un Acces point
- Añade dispositivos finales como PC, Smartphones
---

## **Paso 2: Configuracion del router **

1.- Accede a la configuracion del router :

Haz clic en el router analambrico 

---

## **Paso 3: Crear y ejecutar un contenedor con PostgreSQL**

Ejecuta el siguiente comando para crear y ejecutar el contenedor:

```bash
docker run --name mi_postgres -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=admin123 -e POSTGRES_DB=mi_base -p 5432:5432 -d postgres
```
📌 **Parámetros:**
- `--name mi_postgres` → Nombre del contenedor.
- `-e POSTGRES_USER=admin` → Usuario de la base de datos.
- `-e POSTGRES_PASSWORD=admin123` → Contraseña.
- `-e POSTGRES_DB=mi_base` → Nombre de la base de datos.
- `-p 5432:5432` → Expone el puerto 5432.
- `-d postgres` → Ejecuta en segundo plano.

Verifica que el contenedor está corriendo con:

```bash
docker ps
```
---

## **Paso 4: Conectarse a PostgreSQL dentro del contenedor**

Ejecuta el siguiente comando para ingresar al contenedor y conectarte a PostgreSQL:

```bash
docker exec -it mi_postgres psql -U admin -d mi_base
```
---

## **Paso 5: Crear la tabla "Estudiante"**

Dentro de la consola de PostgreSQL, ejecuta:

```sql
CREATE TABLE Estudiante (
    id SERIAL PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    edad INT,
    correo VARCHAR(100) UNIQUE,
    fecha_registro TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```
Verifica que la tabla fue creada con:

```sql
\d Estudiante
```

---

## **Paso 6: Insertar y consultar datos**

Para insertar un estudiante:

```sql
INSERT INTO Estudiante (nombre, edad, correo) VALUES ('Juan Pérez', 22, 'juanperez@gmail.com');
``
Consulta los datos:

```sql
SELECT * FROM Estudiante;
```
---

## **Paso 7: Salir y detener el contenedor**

Para salir de PostgreSQL:

```sql
\q
```
Con estos pasos, ya tienes PostgreSQL corriendo en Docker con una base de datos y una tabla funcional.
