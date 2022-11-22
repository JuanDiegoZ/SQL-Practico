# Algebra lineal

El algebra relacional estudia las operaciones que se pueden realizar entre diversos conjuntos de datos.

No confundir las relaciones del álgebra relacional con las relaciones de una base de datos relacional.

Las relaciones de una base de datos se define como la union de dos tablas.
Las relaciones en álgebra relacional se refiere a una tabla.

- La diferencia es conceptual: Las tablas pueden tener tuplas repetidas pero en el álgebra relacional cada relación no tiene un cuerpo, no tiene un primer ni último row.

## Set up a PostgreSQL server and pgAdmin with Docker

<https://linuxhint.com/postgresql_docker/>

HAVING es una clausula también bastante usada para especificar condiciones, se usa despues de agrupar los datos

SELECT  name, SUM(sales)
FROM tabla_diaria
GROUP BY name
HAVING SUM(sales) > 100

"""sql



"""