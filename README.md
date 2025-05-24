# Base de Datos Relacional de Gestión de Flota de Coches

Este repositorio contiene el diseño, estructura y scripts SQL para una **base de datos relacional orientada a la gestión de flotas de vehículos**. El modelo está optimizado para almacenar y consultar información sobre coches, revisiones técnicas, pólizas de seguro, características técnicas y estructura de marcas.

## Archivos

```
📁 car-fleet-sql-db/
├── script_mysql.sql        → Script SQL completo para MySQL
├── script_postgresql.sql   → Versión adaptada a PostgreSQL
├── coches.csv              → Dataset con más de 80 coches
├── coches.sql              → Archivo de base de datos para MySQL
├── diagramas-drawio.pdf    → Diagrama E-R completo
└── README.md
```

## Enfoque de Negocio

La base de datos está pensada como un sistema **modular y escalable** para compañías que gestionan una flota de vehículos, como:

- Empresas de renting o leasing
- Concesionarios de automóviles
- Aseguradoras
- Talleres con flota asociada
- Plataformas de movilidad (sharing, logística, etc.)

Este sistema facilita un seguimiento detallado de:

- Vehículos y sus atributos (modelo, marca, color, grupo, kms, fecha de compra)
- Historial de revisiones con control de kilometraje, fechas e importes
- Pólizas de seguro activas por vehículo y aseguradora correspondiente
- Monedas utilizadas en las transacciones

## Modelo Relacional

La base de datos está compuesta por **9 tablas relacionales** conectadas a través de claves primarias y foráneas.

- **Coche**: Información clave de cada vehículo (matrícula, modelo, kms, etc.).
- **Revisión**: Registro de mantenimientos y revisiones, con importe y fecha.
- **Moneda**: Control multimoneda para las transacciones de revisiones.
- **Seguro**: Pólizas y fecha de alta asociadas a cada coche.
- **Aseguradora**: Catálogo de compañías aseguradoras.
- **Modelo**: Modelos específicos de vehículos.
- **Marca**: Marca a la que pertenece cada modelo.
- **Grupo**: Agrupación de marcas (conglomerados automovilísticos).
- **Color**: Catálogo de colores disponibles.

📎 Consulta el diagrama completo en [`diagrams.pdf`](./diagrams.pdf) o [en este enlace (diagrams.net)](https://viewer.diagrams.net/?tags=%7B%7D&highlight=E6E6E6&edit=_blank&layers=1&nav=1&title=diagramas.png#R7V1bc6M4Fv41rpp9SIqLufgxcSedqU22e9O9mZl96ZJBtpnGyCXjxO5fP8JcDEhgMGBzUVeqY4Qi8DmfzpE%2BHR2N5Olq9xmD9fIFmdAeSYK5G8mfRpIkqbpGfnkle79EFCTFL1lgywzKjgXfrF8wrBiUbi0TbhIVXYRs11onCw3kONBwE2UAY%2FSRrDZHdvKpa7CAVME3A9h06R%2BW6S79Ul0RjuVP0FoswyeLQnBnBcLKQcFmCUz0kSiCO%2FcROW7wil8hXgEHOi658wLwT4hHysPSdb1vejeSHsnP3Kt9u0BoYUOwtja3BlqRYmNDqjzOwcqyPTnHGroPGiKPkx9G8hQj5PqfVrsptD1lhWrw3%2Bkx424kB%2By1W%2BAPpjfv%2B%2Befgus8fchv7svL4qs2uxElv5l3YG8DAQfCcfehxKFJFBBcIuwu0QI5wH44lt5Dx7zzVEsqPLz%2Bghh9Ry%2FAId%2F8fuMC7B7vISeo%2FmiRd5M%2FiWGV4Fo43HXx%2Fs%2Fg5uHiL%2B%2FOrRJeftrFa37aB1cYbR0TmuG9neVGjZDPsTbI1bEJ7yJsgZZoIOQN2mID5ohRDjoCwAsY%2FOnqeffld2U%2F0%2F%2F64%2B3lTZen39Wnm3FQ0RNp7AmBwj5DtILkK5EKH0doRwBexmEdFmJoA9d6T3YOEAB4ETUYPeMrsg54DgzCOGwnNAe6kGzC%2F%2BrBX8XRlW5ITTYkCUqyIV82VEPkQ%2ByLH4sO4C0BZBrHpKMZgAIz6fRr76MLZgfoHtAXWDnZAwGxWy6wHNJFffAYyLbBemMdqvslS8s2n8Eebd2wofDqfm7toPnqGznxAMqPZ9LYJkCYZy7CruTdBra1cMhngyDOe%2BI9hhvyLs9g4wY15qRjTJGN8OH1ZVOBujk%2BvDdGP2Hsji7NZFXNQ%2FE7xC7c5cIuuHszHie1qYewiOFS0lm4lIVsCCZ0XlbB8mlDFeqWfHfXAvYrcT%2FAWRzUnNSipwoTo%2FX3sL96BWsPmhA%2FvEPfAQgp6Tu%2B8TpUO3w55Z78kK879eyKQl5gSq7F4zX58apjd4ocoi5gHfQBiW4%2FoKffexetg%2BfYcB6%2BBg6E6X2eIdcl%2FsRHAq3X3I5wWtmBbuWCqm1Ms2NKs1%2F%2FXUa3iHzXuX3wMEvLNKHj92Jv9AGO%2Bmaokin%2FSOZpZaT7bkF9yIX1EVOALNwKsX%2BSpJXTR9D4UUqVWwc26RsOcOG952Y3TZhwhcKBZf5Y%2BVZc8J3NGlukwBPWT7hvIUZCe%2B7Xvd%2BsgWE5i2f%2FL9UUiJQmQLTLV3G8k48nt5PYP61WjJ3T%2BgUwpg7Zi7DHuPV4EfXaXkSrpNkL2YeC0lcLS3%2FoPkOntO6g1QzDyG%2B8k99LgH8jE6Z%2Fkcv%2FfPnu%2Ff%2B%2F5%2BcWouOk96gdPtxb5KJrwr1FM95icm1vEbKZMdU%2BtnHSUVABk8IKGLrDEEVK8WSWscDbNYpmGYNwEsUhw51EPqJoZuoVvlsbCzmZ8Oko%2BzifQ9UwWOyjqU1mQi6HXoJ9lNNcslTQXUQV6%2FcXNEk1oKFACbpLLE5VtIV%2FFGniqU8EZATdkoODegcD7TDVNP1DnD%2BOrPXAWcYSSNmNMvuuUityCjV3CehU45c67gBKTEXKO4CrU4cizSJ1eTIYQZUbfJFmcFbAxZaxtT1y8O3udfp09%2FqbOBxusAQ4Bmfjw9kDt%2FG12%2FirE34Szfu0sJcXlH8EVG7hQzXG9PpztaHH9D036yUQ0Wezzg665Ms4TZl1sSgzV4ddZypXqeazr2bX85E6KLvO1ivtr%2BfQWIK4ZTfJG%2FTKtFcFxeBMu0J7f27aazLtytVNe7WQ73aZ9gip3LQr9FqatfJ6BIwbd6I60MfF%2BKroGJ6Np5fnuI2vycYX3dbTnI2nV%2BQ6Qr3nY5VbeYVeMPO2cxDhm8f9HMMw7sVB0Wfjzuat6DHeFBlLmAmHrkZO6QZkR07NdGWs1BU5ld63OS68b3NSg4Vna5hHThWkcLsXOSX1O3JK4pFTkSjocVr2QvpQ46dK4KXPjp7NYg7ZC5RZ2m11%2BBR7fEuptstTuEHafKYkmMGyKy%2BjVH%2B3ylSExODMOmMfHbfr9dj1S4ZMsXVLL8F22bBHUOWWnZH1jZh246CEQVn2EpgYnGnnGx6asuzXj5qiNzy0sJMX7MOD3O3AlAQd5%2BiHTBlotcYeTRMGTA3BtPN9DpmikTkZ05hpv3rUlFwtXKJdtl3mbEwkCpqO8TY6uMgFNtyM%2BrfPoSog%2BmzW2fE%2Fpzv%2BpVN5n5GEu5703zScGKm82WRfoLjTubz9eq1J5S2n1v61dDKUwqm8Uw2p6YbqS%2BXN7uMFZiccyCdz0oerkXEg524Jbg2SqVzy41Qu%2BaJIlvVUQ80lpWcjmZ6RvQTrJxkeuqPhTSaA%2BpwZ3qQaOpzN84BcIbxJK0qk1JKWPtddDHMuxQ6mye8LrQxvYuuWHlF1NLwpH7p8cjWWKE3Ta90DCGuqipM%2Bz7nYsuEJ5Zsy%2F1ePaxp3NKV8PlC5sR9nJ40PDX6YNV7pZWKoqgAZnpUf9OFTjVr5q0c5jenFsC5HOY2LL1n13s4XOFBqGKb9jOOjemjav4l4BzbLN%2Fxlg%2F9cbz%2F%2B%2F18Ds3L%2BvQR7VPtF0UHRVKDGougmqiaDI5wolDBYu2yKTg4FGu5AvCRDx9Zwtcx%2FHXfeYlG95vSOVjB07PejeZsOMXRnaYSf68KWCz1Ep9MN9JTBqxNH%2FLCXfJjx0LmmnMkl%2BT72%2B3Uocu4s%2BY%2B562DKhebwIz4wcB89PEWyTgRxp5ELMJmeY3KnUY%2FTuCR9yNZth%2FLKnyN%2FOUP%2BQ3caMj3z3FirGVESy2sM2WlkIYg7jXyAFVhzKhkFuyoU%2FyqM2hf%2FmgpNPRkQm0sEnozs9hP2tSeSW9TOjH8di6mG0oG09cW%2FsjFMz5Y%2F%2Byft9otbn8%2FnUsa5qOpMVeri1nUhqc6JUHD0EwGz%2FuHPoJPzVqNy5YzZVFvIdcaOs56T6%2FJpwz%2FMwS4zl2%2Fy0HTOrZ%2BEER%2Fx5qOsWlaKjvuSitP0fF9ydW6dsROqhTaigvx17jlYcmFsjwq49dB7cGo9F0DcZ%2BTjq8B67KX3Coe8R3RRjPc4h2NpjCsJ53UnNw9PTtq9RqkSVUlOiTX5TKpEnSQbUqXLUiWMjUS%2BqeoZVXKhMMQ0VaIUjkNsjCqpuJ2o48PbahNzv3e0lyphbCnqOVXio5kPeCm50BMdKrUqp0pOwogPe3NRVvHU4477kmpT9RO%2B5OpUCePk4xbaiPPlr%2FCIErZcJErvAVUSeg9OleQCiPuMfHwVSFURp0qIEix3%2F3qYnyOnnanVSlIsjdEl4dzuZGiJeNr4NcqXpOiSKNNaWbok1U4UsXKCLSHQAPtYtWD4kPm6N6KWelDA7xz7ht9kvT2Fnql%2Fg4st7mHcClQz4la0yUwo7OdLkjHSRU%2BlZKt40GuN1ab%2BSsacrS1kjEJPwXtOxih89ZEpF5WeJlvmj01gyzkbUxRHfGSdC7MJTwLXlDO5OhszoceCLU4PdI4GJhl82NCdx4QeIhLnAQ7eA5gI9yuJUJ3I4e4iH1jVYuG4u2jxdtCIp%2Bmxvzgd8jNIfyEK9MLNCrjYMra25yve7l6nT3evA98NmoUe7jPyZ7KDTmLWqM%2B46GmcbOVKlZTbeo%2Bh8pxlbLnQW7ydH2tkW7%2FAaCqN7gY%2BvciCDXcV%2BagadJxps67ikqd7spXboZObz%2BrzPKyULReaM%2FDPdibPBscVjR4d8FwnerjHyAWXRnMWd3GaMwNCHQ16uNAOFC11iKHI2IESJctOhfokYSo35Eu0Qc8pq624a%2Flp6RgxEExdNzZO0OgpZc9jIDQ%2ByWTLhZkYm7WMxQMhToKpxEBCT7p6vdZxRPnGL4E0nhu7KX%2FCCIO4sD%2FpeW5sjefGZsslMzd20oP078C8OlHE3UaO0PT6E53WtScl%2FNzJPSnh9C6%2BJ%2BXcALBG96TcyOldKUoKhUV3pdxE%2BA3TPgiXzeKhF3CTSYUf0fyMDmbMw%2BPf0HX3AaMCti4iRUt3FaK1SGc4L%2FUus6vQ%2BW3M%2FOTB5%2FSe83DPzEgTHtFyGvcZoQiF4ZwxoiKXGCE3jiwM1ssX73BZUvgP).

## Relaciones y Cardinalidad

- **1:N** → Un modelo pertenece a una marca, una marca a un grupo, etc.
- **1:1** → Un coche tiene su póliza activa más reciente (seguro actual).
- **N:M simulada** → Se pueden registrar múltiples pólizas por coche a lo largo del tiempo.
- **1:N** → Un coche puede tener múltiples revisiones (historial técnico).

## Scripts Disponibles

En la raíz del repositorio encontrarás los siguientes archivos SQL:

- `script_mysql.sql`: Script completo para la creación y carga de datos en MySQL.
- `script_postgresql.sql`: Versión adaptada para PostgreSQL (estructura y consultas).

## Datos y Consultas

Incluye más de **80 modelos de coches**, **pólizas históricas**, **colores**, **aseguradoras**, y un histórico de revisiones técnicas con importes y fechas en **varias monedas** (EUR, USD, COP, MXN).

Algunas consultas destacadas incluidas:

```sql
-- Vehículos con su marca, grupo y aseguradora actual
SELECT
  c.matricula,
  c.fecha_compra,
  m.nombre_modelo,
  ma.nombre_marca,
  g.nombre_grupo,
  col.nombre_color,
  c.kms_totales,
  s.n_poliza,
  a.nombre_aseguradora
FROM coche c
JOIN modelo m ON c.id_modelo = m.id_modelo
JOIN marca ma ON m.id_marca = ma.id_marca
JOIN grupo g ON ma.id_grupo = g.id_grupo
JOIN color col ON c.id_color = col.id_color
JOIN (
  SELECT matricula, MAX(fecha_alta_seguro) AS ultima_fecha
  FROM seguro
  GROUP BY matricula
) s_max ON s_max.matricula = c.matricula
JOIN seguro s ON s.matricula = s_max.matricula AND s.fecha_alta_seguro = s_max.ultima_fecha
JOIN aseguradora a ON s.id_aseguradora = a.id_aseguradora
ORDER BY c.matricula;
```

## Cómo usar este repositorio

1. Clona el repositorio:

```bash
git clone git@github.com:rociobenitez/car-fleet-sql-db.git
```

2. Carga el script en tu gestor de base de datos

- Para MySQL: importa `script_mysql.sql`
- Para PostgreSQL: usa `script_postgresql.sql`

3. Explora los datos

- Revisa la estructura de tablas.
- Lanza consultas predefinidas.
- Usa los datos reales del CSV `coches.csv` si quieres importarlos como tabla de referencia.
