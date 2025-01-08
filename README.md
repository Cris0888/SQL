# SQL
Conocimiento sql

VAMOS A CREAR UN CRUD Y EL CRUD SE BASA EN Crear, Leer, Actualizar y Borrar",
EMPEZEMOS CON LEER: si quieres que una tabla se muestre en SQL hay cuatro formas mostrar la tabla la completa, mostrar toda una columna, mostrar todo un registro, y mostrar un solo registro 
EJEMPLOS
EMPEZEMOS INSERTANDO DATOS:
INSERT INTO NOMBRE DE LA TABLA (???????)
VALUES es para meter los campos (?????)
EMPEZEMOS CREANDO TABLAS:
créate table nombre de la tabla (?????)
EMPEZEMOS MOSTRANDO TODA LA TABLA:
SELECT * FROM nombre de la tabla;
EMPEZEMOS MOSTRANDO UNA SOLA COLUMNA:
SELECT nombre de la columna FROM nombre de la tabla;
EMPEZEMOS MOSTRANDO TODO EL REGISTRO:
SELECT * FROM nombre de la tabla WHERE nombre de la columna = nombre del registro;
EMPEZEMOS MOSTANDO UN SOLO REGISTRO
SELECT nombre de la columna FROM nombre de la tabla WHERE nombre de la tabla que quiere que se muestre =nombre del registro;



EMPEZEMOS CON ACTUALIZAR UPDATE:
UPDATE nombre de la tabla 
SET nombre de la columna = nombre de cómo le quieres poner ejemplo 600 
WHERE nombre del pk =nombre del registro
Cuando queremos modificar mas de una columna solo ponemos coma y  la siguiente modificación



Ejemplo solo ponemos una coma y la modificacion
UPDATE nombre de la tabla 
SET nombre de la columna = nombre de cómo le quieres poner ejemplo 600 ,
Nombre = “juan”,
Edad= 12
WHERE nombre del pk =nombre del registro



EMPEZEMOS BORRANDO REGISTROS 
DELETE FROM nombre de la tabla
WHERE pk de la columna = nombre del registro


Ahora empecemos con las relaciones: 
1RELACIONES:Las relaciones son las uniones de una tabla con otras existen 2 las PK que son llaves únicas y las FK que son las llaves que hacen referencia de la pk:
Ejemplo:  tenemos 2 tablas primera tabla se llama usuarios:  y tiene un pk   que es idusuario_ nombre, apellido ,edad   y la segunda tabla se llama: consultorio medico
Y tiene un id_consulta , id_usuario ,apellido y edad ,
la relación es que la tabla usuarios tiene pk id_usuario y hace referencia a la tabla consultorio médico con la fk id-usuario en contesto la pk es la única y la fk es la misma, pero haciendo referencia ala pk de la otra tabla consultorio medico 
2 IMPORTANCIA: con el ejemplo anterior que teníamos dos tablas que eran 
Usuarios y consultorio medico con las relaciones podemos recuperar datos de esa relación ejemplo la tabla usuarios tiene un pk id_usuario nombre, apellido, edad bueno  con la relación de la tabla consultorio médico atravez de la relación de la pk id_usuario de la tabla consultorio médico podemos recuperar todos los datos de la tabla usuarios y te preguntaras porque bueno las pk tienen el privilegio de manipular los datos 


Ahora empezaremos con el ORDER BY 
el order by es para ordenar las tablas existen dos propiedades que son DESC que ordena del número más mayor al menor, y el ASC que ordena del número menor al número mayor
también funciona con caracteres y es que los organiza en orden alfabético 
EMPEZEMOS CON EL ORDER BY DESC:
Los ordena de forma descendente números los ordena con letras de forma descendente pero si queremos que nos salgan los valores nulos al comienzo ponemos la clausula NULLS FIRS
 
SELECT * FROM nombre de la tabla
ORDER BY nombre de la columna DESC
EMPEZEMOS CON EL ORDER BY ASC
Los ordena de forma ascendente y si no tenemos números los ordena con letras de forma ascendente si tenemos valores nulos nos va salir porque la clausula asc lo que menos tiene valor lo muestra primero entonces si no queremos que nos salgan los valores nulos al comienzo ponemos la clausula NULLS  LAST este comando los eliminara al comienzo pero si aparecerán pero al final de la tabla
SELECT * FROM nombre de la tabla
ORDER BY nombre de la columna ASC




Ahora empezaremos con el GROUP BY 
En específico la función que hace group by hace es  agrupar ósea  crear grupos de esas columnas y así sacar valores de los registros y hacer las clausulas SUM, COUNT, AVG, MAX, MIN
Ejemplo: este código lo que hace es mostrar la columnas nombre de la tabla clientes importe y fab de la tabla pedidos lo que hace este código es sumar el importe y como el group by lo tiene el fab y agrupa los registros y no salen repetidos da la suma de todos los registros del fab y así muestra el resultado de la suma

SELECT clientes.nombre,SUM(pedidos.importe),pedidos.fab FROM clientes,pedidos GROUP BY pedidos.fab; 
Ahora vamos con el HAVING:
El having se usa solamente con el  group by porque el group by lo que hace es  agrupar las columnas así mismo es el having es como el where solo que el  where filtra por registros pero el having filtra es por grupos  esos grupos en los que hemos hecho clusulas con el  group by como sum,avg,min,max 
En este ejemplo estamos mostrando nombre, y estamos redondeando las ventas y le estamos dando un alias de promedio después estamos  agrupando con el group by la venta que le pusimos promedio después con el having le estamos diciendo que muestre solo los que promedio supero los 305000 y me arroja solo los resultados mayores de 305000 
SELECT nombre, round(AVG(ventas)) AS promedio FROM `empleados` GROUP BY ventas HAVING promedio > 305000

EMPEZEMOS CON SUM:
El sum es una función que sirve para sumar dos tablas y dar un resultado sobre esa sumatoria 
SELECT columna, SUM (columna numérica) AS suma
FROM tabla
GROUP BY columna;
• columna" se refiere a la columna por la cual deseas agrupar los datos.
• “columna numérica" es la columna numérica en la cual deseas calcular la suma.
• “tabla" es la tabla de la cual deseas extraer los datos.
Esto es mientras se hace la consulta, pero la tabla suma no queda guardada

EMPEZEMOS CON EL COUNT: EMPEZEMOS CON LAS FEHAS EMPEZEMOS CON LOS COMETARIOS
El count es una función de SQL que lo que hace es contar cuantas filas ay en total en una columna
SELECT COUNT (nombre de la columna) AS conteo
FROM nombre de la tabla
WHERE condición que tiene que ser verdadera pero también funciona sin el where;





EMPEZEMOS CON EL AVG
AVG es una función de agregación en SQL que se utiliza para calcular el promedio de los valores en una columna numérica
Supongamos que tienes una tabla llamada "ventas" con las siguientes columnas: "producto", "vendedor" y "cantidad". Si deseas obtener el promedio de las cantidades vendidas para cada producto, puedes ejecutar la siguiente consulta:
SELECT producto, AVG(cantidad) AS promedio cantidad
FROM ventas
GROUP BY producto;
EMPEZEMOS CON EL MAX:
MAX es una función de agregación en SQL que se utiliza para obtener el valor máximo de una columna. 
Supongamos que tienes una tabla llamada "productos" con las siguientes columnas: "categoría", "producto" y "precio". Si deseas obtener el precio máximo para cada categoría de productos, puedes ejecutar la siguiente consulta:
SELECT categoría, MAX(precio) AS precio máximo
FROM productos
GROUP BY categoria;
EMPEZEMOS CON EL MIN
MIN es una función de agregación en SQL que se utiliza para obtener el valor máximo de una columna. 
Supongamos que tienes una tabla llamada "productos" con las siguientes columnas: "categoría", "producto" y "precio". Si deseas obtener el precio mínimo para cada categoría de productos, puedes ejecutar la siguiente consulta:
SELECT categoría, MIN(precio) AS precio máximo
FROM productos
GROUP BY categoria;





: EMPEZEMOS CON LAS FECHAS 
TAMBIEN ESTA PARA MOSTRAR LAS FECHAS ESTA MESES Y AÑOS MESES ES MONTH Y AÑOS ES YEAR 
EJEMPLO AÑOS
Estamos mostrando el código y el año del campo fecha pedido
SELECT codigo ,YEAR(fechapedido) AS meses 
FROM pedidos;
EJEMPLO MESES 
Estamos mostrando el código y el mes del campo fecha pedido
SELECT codigo ,MONTH(fechapedido) AS meses 
FROM pedidos;
: EMPEZEMOS CON LOS COMETARIOS

También si queremos añadir un cometario lo hacemos de esta forma
Estamos mostrando el código seguido del comentario tiene un porcentaje de y seguido del campo importe *1.15 que lo que está haciendo es mostrar un porcentaje del 15%
SELECT codigo , 'TIENE UN PORCENTAJE DEL' AS porcentaje ,(importe*1.15)
FROM pedidos;



EMPEZEMOS CON DISTINCT
El distinct se usa para elimina las repeticiones de una tabla ejemplo
Primero va el select seguido del distinct y el campo que queremos que salga sin repeticiones  
SELECT DISTINCT oficina FROM empleados;
EMPEZEMOS CON EL WHERE 
La clausula where solo se cumple si la condición es VERDADERA 
Where tiene muchos tipos de condiciones
puede ser cualquier condición válida o combinación de condiciones utilizando los operadores 
IS NOT NULL esto lo que hace es decir que salga todo menos los valores nulos
NOT (no) se usa para decir que salga todo menos esa condición que ponemos con el NOT 	ejemplo aquí dice que muestre todo menos las relaciones del 2103: SELECT * FROM `pedidos` WHERE NOT clie= 2103
AND (y)  es si se cumplen las dos ejemplo : SELECT * FROM `pedidos` WHERE pedidos.importe>600 AND pedidos.importe <56;
 OR (ó) es si se cumple algunas de las dos ejemplo : SELECT * FROM `pedidos`  WHERE pedidos.importe>600 OR pedidos.importe <56; 

consejos
1 :Si ponemos false and false= da falso porque las dos condiciones se cumplen y al cumplirse da falso 
2: si ponemos false and true = da falso porque las dos deben cumplirse y ay no se estan cumpliendo 
3: si ponemos false or true = da verdadero porque ay dice que se cumplan alguna de las dos y la verdadera se esta cumpliendo 
4: si ponemos false or false = da falso porque las dos condiciones se estan cumpliendo y al cumplirse dan falso
5 si ponemos not fase = da verdadera porque esta diciendo not false y la negación con negación da verdadera 
6:si ponemos not true = da falso porque estamos diciendo que no se cumpla la condición la estamos  negando y al negarla no se   cumple la condición 
SELECT * FROM pedidos WHERE (importe> OR  100 importe <2500) AND clie=2103
And y OR al mismo tiempo ejemplo: aqui la condición es que el importe tiene que ser mayor que mil o menor que dos mil quinientos  es si alguna de las dos se cumple y el and que es la obligatoria tiene que ser el cliente 2103
SELECT * FROM pedidos WHERE (importe> OR  100 importe <2500) AND clie=2103


= igual que 	esta condición se usa para decir que salga todo menos ese valor que pongamos en este ejemplo estamos diciendo que salga todo menos el repclie 101 =  SELECT * FROM clientes WHERE repclie != 101 
<> distinto de
 < menor que
 <= menor o igual
 > mayor que 
>= mayor o igual
puede ser cualquier condición válida o combinación de condiciones utilizando los operadores NOT (no) AND (y) y OR (ó).
y no solo puede ser con el id la con condición también se puede hacer con cualquier tabla


 WHERE BETWEEN también está el where el BETWEEN se usa para decir que algo valla desde ese rango inicial hasta ese último rango EJEMPLO
estamos mostrando una lista de los empleados desde la fecha 1989/10/12 hasta la fecha 1997/01/02
SELECT fechapedido
FROM pedidos 
WHERE fechapedido BETWEEN '1989-10-12' AND '1997-01-02'

WHERE NOT NULL el not null es para indicar que un registro no puede tener el campo vacio ejemplo
Estamos indicando muestre una lista de la las ventas que estan con información ósea que no estan vacias
SELET * 
FROM empleados
WHERE ventas IS NOT NULL

WHERE IS NULL
Es para decir que columna tiene valores vacíos o (valores nulos) ejemplo
Muéstreme una lista de las columnas oficina , contrato , cuota donde tenga valores vacíos 
SELECT oficina , contrato , cuota
FROM empleados 
WHERE oficina IS NULL;



WHERE LIKE el where like se usa para buscar una palabra que queramos buscar ejemplo 
lista de la columna region y  mostrara todos los registros que contengan la palabra ‘este’
el % porcentaje se pone para que busque en toda la tabla que otra columna contiene la palabra ‘este’
SELECT región 
FROM clientes
WHERE región LIKE ‘este%’ 

LIMIT:
El limit es para indicar que solo queremos que salga un  numero de registros como por ejemplo decirle muéstreme solo 5 registros de la tabla se hace así se pone la clausula limit y el numero que le digamos  ejemplo: 
SELECT   *  FROM `pedidos` LIMIT 5 

