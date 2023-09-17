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

Para diseñar la estructura de la base de datos y establecer las relaciones entre las tablas, se utilizó la herramienta [app.diagrams.net](https://app.diagrams.net/). Puedes ver el diseño completo [aquí](https://viewer.diagrams.net/?tags=%7B%7D&highlight=E6E6E6&edit=_blank&layers=1&nav=1&title=diagramas.png#R7V1bc6M4Fv41rpp9SIqLufgxcSedqU22e9O9mZl96ZJBtpnGyCXjxO5fP8JcDEhgMGBzUVeqY4Qi8DmfzpE%2BHR2N5Olq9xmD9fIFmdAeSYK5G8mfRpIkqbpGfnkle79EFCTFL1lgywzKjgXfrF8wrBiUbi0TbhIVXYRs11onCw3kONBwE2UAY%2FSRrDZHdvKpa7CAVME3A9h06R%2BW6S79Ul0RjuVP0FoswyeLQnBnBcLKQcFmCUz0kSiCO%2FcROW7wil8hXgEHOi658wLwT4hHysPSdb1vejeSHsnP3Kt9u0BoYUOwtja3BlqRYmNDqjzOwcqyPTnHGroPGiKPkx9G8hQj5PqfVrsptD1lhWrw3%2Bkx424kB%2By1W%2BAPpjfv%2B%2Befgus8fchv7svL4qs2uxElv5l3YG8DAQfCcfehxKFJFBBcIuwu0QI5wH44lt5Dx7zzVEsqPLz%2Bghh9Ry%2FAId%2F8fuMC7B7vISeo%2FmiRd5M%2FiWGV4Fo43HXx%2Fs%2Fg5uHiL%2B%2FOrRJeftrFa37aB1cYbR0TmuG9neVGjZDPsTbI1bEJ7yJsgZZoIOQN2mID5ohRDjoCwAsY%2FOnqeffld2U%2F0%2F%2F64%2B3lTZen39Wnm3FQ0RNp7AmBwj5DtILkK5EKH0doRwBexmEdFmJoA9d6T3YOEAB4ETUYPeMrsg54DgzCOGwnNAe6kGzC%2F%2BrBX8XRlW5ITTYkCUqyIV82VEPkQ%2ByLH4sO4C0BZBrHpKMZgAIz6fRr76MLZgfoHtAXWDnZAwGxWy6wHNJFffAYyLbBemMdqvslS8s2n8Eebd2wofDqfm7toPnqGznxAMqPZ9LYJkCYZy7CruTdBra1cMhngyDOe%2BI9hhvyLs9g4wY15qRjTJGN8OH1ZVOBujk%2BvDdGP2Hsji7NZFXNQ%2FE7xC7c5cIuuHszHie1qYewiOFS0lm4lIVsCCZ0XlbB8mlDFeqWfHfXAvYrcT%2FAWRzUnNSipwoTo%2FX3sL96BWsPmhA%2FvEPfAQgp6Tu%2B8TpUO3w55Z78kK879eyKQl5gSq7F4zX58apjd4ocoi5gHfQBiW4%2FoKffexetg%2BfYcB6%2BBg6E6X2eIdcl%2FsRHAq3X3I5wWtmBbuWCqm1Ms2NKs1%2F%2FXUa3iHzXuX3wMEvLNKHj92Jv9AGO%2Bmaokin%2FSOZpZaT7bkF9yIX1EVOALNwKsX%2BSpJXTR9D4UUqVWwc26RsOcOG952Y3TZhwhcKBZf5Y%2BVZc8J3NGlukwBPWT7hvIUZCe%2B7Xvd%2BsgWE5i2f%2FL9UUiJQmQLTLV3G8k48nt5PYP61WjJ3T%2BgUwpg7Zi7DHuPV4EfXaXkSrpNkL2YeC0lcLS3%2FoPkOntO6g1QzDyG%2B8k99LgH8jE6Z%2Fkcv%2FfPnu%2Ff%2B%2F5%2BcWouOk96gdPtxb5KJrwr1FM95icm1vEbKZMdU%2BtnHSUVABk8IKGLrDEEVK8WSWscDbNYpmGYNwEsUhw51EPqJoZuoVvlsbCzmZ8Oko%2BzifQ9UwWOyjqU1mQi6HXoJ9lNNcslTQXUQV6%2FcXNEk1oKFACbpLLE5VtIV%2FFGniqU8EZATdkoODegcD7TDVNP1DnD%2BOrPXAWcYSSNmNMvuuUityCjV3CehU45c67gBKTEXKO4CrU4cizSJ1eTIYQZUbfJFmcFbAxZaxtT1y8O3udfp09%2FqbOBxusAQ4Bmfjw9kDt%2FG12%2FirE34Szfu0sJcXlH8EVG7hQzXG9PpztaHH9D036yUQ0Wezzg665Ms4TZl1sSgzV4ddZypXqeazr2bX85E6KLvO1ivtr%2BfQWIK4ZTfJG%2FTKtFcFxeBMu0J7f27aazLtytVNe7WQ73aZ9gip3LQr9FqatfJ6BIwbd6I60MfF%2BKroGJ6Np5fnuI2vycYX3dbTnI2nV%2BQ6Qr3nY5VbeYVeMPO2cxDhm8f9HMMw7sVB0Wfjzuat6DHeFBlLmAmHrkZO6QZkR07NdGWs1BU5ld63OS68b3NSg4Vna5hHThWkcLsXOSX1O3JK4pFTkSjocVr2QvpQ46dK4KXPjp7NYg7ZC5RZ2m11%2BBR7fEuptstTuEHafKYkmMGyKy%2BjVH%2B3ylSExODMOmMfHbfr9dj1S4ZMsXVLL8F22bBHUOWWnZH1jZh246CEQVn2EpgYnGnnGx6asuzXj5qiNzy0sJMX7MOD3O3AlAQd5%2BiHTBlotcYeTRMGTA3BtPN9DpmikTkZ05hpv3rUlFwtXKJdtl3mbEwkCpqO8TY6uMgFNtyM%2BrfPoSog%2BmzW2fE%2Fpzv%2BpVN5n5GEu5703zScGKm82WRfoLjTubz9eq1J5S2n1v61dDKUwqm8Uw2p6YbqS%2BXN7uMFZiccyCdz0oerkXEg524Jbg2SqVzy41Qu%2BaJIlvVUQ80lpWcjmZ6RvQTrJxkeuqPhTSaA%2BpwZ3qQaOpzN84BcIbxJK0qk1JKWPtddDHMuxQ6mye8LrQxvYuuWHlF1NLwpH7p8cjWWKE3Ta90DCGuqipM%2Bz7nYsuEJ5Zsy%2F1ePaxp3NKV8PlC5sR9nJ40PDX6YNV7pZWKoqgAZnpUf9OFTjVr5q0c5jenFsC5HOY2LL1n13s4XOFBqGKb9jOOjemjav4l4BzbLN%2Fxlg%2F9cbz%2F%2B%2F18Ds3L%2BvQR7VPtF0UHRVKDGougmqiaDI5wolDBYu2yKTg4FGu5AvCRDx9Zwtcx%2FHXfeYlG95vSOVjB07PejeZsOMXRnaYSf68KWCz1Ep9MN9JTBqxNH%2FLCXfJjx0LmmnMkl%2BT72%2B3Uocu4s%2BY%2B562DKhebwIz4wcB89PEWyTgRxp5ELMJmeY3KnUY%2FTuCR9yNZth%2FLKnyN%2FOUP%2BQ3caMj3z3FirGVESy2sM2WlkIYg7jXyAFVhzKhkFuyoU%2FyqM2hf%2FmgpNPRkQm0sEnozs9hP2tSeSW9TOjH8di6mG0oG09cW%2FsjFMz5Y%2F%2Byft9otbn8%2FnUsa5qOpMVeri1nUhqc6JUHD0EwGz%2FuHPoJPzVqNy5YzZVFvIdcaOs56T6%2FJpwz%2FMwS4zl2%2Fy0HTOrZ%2BEER%2Fx5qOsWlaKjvuSitP0fF9ydW6dsROqhTaigvx17jlYcmFsjwq49dB7cGo9F0DcZ%2BTjq8B67KX3Coe8R3RRjPc4h2NpjCsJ53UnNw9PTtq9RqkSVUlOiTX5TKpEnSQbUqXLUiWMjUS%2BqeoZVXKhMMQ0VaIUjkNsjCqpuJ2o48PbahNzv3e0lyphbCnqOVXio5kPeCm50BMdKrUqp0pOwogPe3NRVvHU4477kmpT9RO%2B5OpUCePk4xbaiPPlr%2FCIErZcJErvAVUSeg9OleQCiPuMfHwVSFURp0qIEix3%2F3qYnyOnnanVSlIsjdEl4dzuZGiJeNr4NcqXpOiSKNNaWbok1U4UsXKCLSHQAPtYtWD4kPm6N6KWelDA7xz7ht9kvT2Fnql%2Fg4st7mHcClQz4la0yUwo7OdLkjHSRU%2BlZKt40GuN1ab%2BSsacrS1kjEJPwXtOxih89ZEpF5WeJlvmj01gyzkbUxRHfGSdC7MJTwLXlDO5OhszoceCLU4PdI4GJhl82NCdx4QeIhLnAQ7eA5gI9yuJUJ3I4e4iH1jVYuG4u2jxdtCIp%2Bmxvzgd8jNIfyEK9MLNCrjYMra25yve7l6nT3evA98NmoUe7jPyZ7KDTmLWqM%2B46GmcbOVKlZTbeo%2Bh8pxlbLnQW7ydH2tkW7%2FAaCqN7gY%2BvciCDXcV%2BagadJxps67ikqd7spXboZObz%2BrzPKyULReaM%2FDPdibPBscVjR4d8FwnerjHyAWXRnMWd3GaMwNCHQ16uNAOFC11iKHI2IESJctOhfokYSo35Eu0Qc8pq624a%2Flp6RgxEExdNzZO0OgpZc9jIDQ%2ByWTLhZkYm7WMxQMhToKpxEBCT7p6vdZxRPnGL4E0nhu7KX%2FCCIO4sD%2FpeW5sjefGZsslMzd20oP078C8OlHE3UaO0PT6E53WtScl%2FNzJPSnh9C6%2BJ%2BXcALBG96TcyOldKUoKhUV3pdxE%2BA3TPgiXzeKhF3CTSYUf0fyMDmbMw%2BPf0HX3AaMCti4iRUt3FaK1SGc4L%2FUus6vQ%2BW3M%2FOTB5%2FSe83DPzEgTHtFyGvcZoQiF4ZwxoiKXGCE3jiwM1ssX73BZUvgP) o descargar el archivo PDF correspondiente en este repositorio.

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