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

SELECT *
FROM tabla_one
GROUP BY marca;


"""

## Limit.

para ver los valores en un intervalo determinado. Por ejemplo los 10 primeros.

## OFFSET

permite elegir desde que valor ver la consulta, por ejemplo muestrame desde el valor 10, lo puedes combinar con el LIMIT para por ejemplo ver desde el elemento 10 hasta el 20.

### El segundo mayor

----
SELECT *
FROM platzi.alumnos
WHERE colegiatura = (
	SELECT DISTINCT colegiatura
	FROM platzi.alumnos
	WHERE tutor_id = 20
	ORDER BY colegiatura DESC
	LIMIT 1 OFFSET 1
);
### La mitad de registros
----

SELECT *
FROM platzi.alumnos 
OFFSET(SELECT (COUNT(id)/2)
	  FROM platzi.alumnos);
### IN en SQL
----
SELECT *
FROM platzi.alumnos
WHERE id IN (1,2,5,6,7);

### DATES IN SQL 
----
SELECT EXTRACT(YEAR FROM fecha_incorporacion), EXTRACT( MONTH FROM fecha_incorporacion)
FROM platzi.alumnos;
### Minutos Fecha, hora.
----
SELECT EXTRACT(HOUR FROM fecha_incorporacion), EXTRACT( MIN FROM fecha_incorporacion),EXTRACT( SECOND FROM fecha_incorporacion)
FROM platzi.alumnos;