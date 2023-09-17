# README - Base de Datos de Coches 🚘

Este repositorio contiene la estructura de una base de datos relacional diseñada para almacenar información sobre coches, incluyendo modelos, marcas, revisiones, datos de seguro y más. A continuación, se detalla el diseño de la base de datos y los pasos seguidos para su creación.

## Diseño de la Base de Datos 📋

Para modelar adecuadamente la estructura de datos de los coches, se han definido **9 entidades principales**:

**1. Coche:** Contiene información específica de cada vehículo, como matrícula, modelo, marca, color, fecha de compra y kilómetros totales.

**2. Revisión:** Registra los detalles de las revisiones realizadas a cada coche, incluyendo la matrícula del coche, kilómetros de la revisión, fecha y costo.

**3. Moneda:** Almacena información sobre los tipos de moneda utilizados para pagar las revisiones de los coches.

**4. Modelo:** Describe los modelos de coches, incluyendo su nombre y la marca a la que pertenecen.

**5. Marca:** Representa las marcas de coches, con una relación uno a muchos con modelos.

**6. Grupo:** Categoriza las marcas en grupos, permitiendo una relación muchos a uno entre marcas y grupos.

**7. Color:** Contiene los colores disponibles para los coches.

**8. Seguro:** Registra información sobre los seguros asociados a los coches, incluyendo el número de póliza, la aseguradora y la fecha de alta del seguro.

**9. Aseguradora:** Almacena datos de las compañías de seguros, incluyendo su nombre.

## Pasos para Crear la Base de Datos 🗄️

### Paso 1: Identificación de Entidades y Atributos 🔍

- Identificamos las entidades clave relacionadas con los coches y sus atributos correspondientes.

### Paso 2: Definición de Claves Primarias 🔑

- Cada tabla tiene una clave primaria única. Por ejemplo, la matrícula se utiliza como clave primaria en la tabla "Coche", mientras que otras tablas utilizan identificadores (ID) numéricos autoincrementales como clave primaria.

### Paso 3: Establecimiento de Relaciones 🔗

- Se definee relaciones entre las tablas para reflejar la estructura de los datos, como la relación entre "Coche" y "Modelo".

### Paso 4: Claves Foráneas 🗝️

- Se usan claves foráneas para establecer relaciones entre tablas, como las relaciones entre "Coche" y "Modelo" o "Revisión" y "Moneda".

### Paso 5: Tipos de Relación y Cardinalidad 🖇️

- Se define la naturaleza de las relaciones (uno a uno, uno a muchos, muchos a uno) y establecemos las restricciones de cardinalidad.

En el diseño de esta base de datos, se han establecido diferentes tipos de relaciones entre las tablas para reflejar cómo se relacionan los datos. A continuación, se describen estas relaciones y su cardinalidad:

**Relación Uno a Uno (1:1):** Ejemplo: La relación entre la tabla Coche y Seguro es uno a uno. Cada Seguro está asociada a un solo Coche, y cada coche pertenece a un solo seguro. Aunque en casos excepcionales un coche puede tener más de un seguro, en la mayoría de las ocasiones es una relación 1:1, por eso se plantea así en el ejemplo.

**Relación Uno a Muchos (1:N):** Ejemplo: La relación entre la tabla Coche y Revisión es uno a muchos. Un coche puede tener múltiples revisiones a lo largo del tiempo, pero cada revisión está relacionada con un solo coche.

**Relación Muchos a Uno (N:1):** Ejemplo: La relación entre la tabla Marca y Grupo es muchos a uno. Varias marcas pueden pertenecer al mismo grupo, pero cada marca solo pertenece a un grupo.

**Relación Muchos a Muchos (N:N):** Ejemplo: No tenemos en el ejemplo una relación directa muchos a muchos. Sin embargo, en situaciones como los propietarios de coches, podríamos tener una tabla intermedia que conecte Persona y Coche si una persona puede poseer varios coches y un coche puede pertenecer a varios propietarios.

### Paso 6: Creación de Tablas 🗂️

- Se crean las tablas en el sistema de gestión de bases de datos (en este caso, se proporciona un script SQL para PostgreSQL).

### Paso 7: Consultas y Pruebas ✔️

- Se utiliza el conjunto de datos proporcionado para realizar consultas y pruebas iniciales.

Ejemplos de algunas de las consultas que se hicieron al inicio:

```
SELECT DISTINCT moneda
FROM coches;

SELECT DISTINCT color
FROM coches;

SELECT DISTINCT matricula, modelo, color, fecha_compra, kms_totales
FROM coches;

SELECT matricula, kms_revision, fecha_revision, importe_revision, moneda
FROM coches;

SELECT matricula, n_poliza, aseguradora, fecha_alta_seguro
FROM coches ORDER BY fecha_alta_seguro;
```

## Scripts SQL 💻

En este repositorio encontrarás dos scripts SQL:

1. `script_mysql.sql`: Script MySQL que incluye consultas iniciales para comprobar la funcionalidad.

2. `script_postgresql.sql`: Script adaptado para PostgreSQL con la creación de tablas y consultas.

Estos scripts te ayudarán a configurar la estructura de la base de datos y a realizar consultas de prueba.


Ten en cuenta que este README proporciona una descripción general del diseño de la base de datos y los pasos seguidos para su creación. Puedes utilizar los scripts proporcionados para configurar la base de datos en tu sistema de gestión de bases de datos preferido y explorar las capacidades de esta estructura de datos de coches.