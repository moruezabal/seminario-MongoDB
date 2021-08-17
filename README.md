# Seminario MongoDB
#### Actividades sobre el uso del sistema de bases de datos Mongo DB  
***

## Actividad N° 1  

1. Instalar MongoDB en ambiente local.

~~~
- Ingresar a www.mongodb.com
- Descargar MongoDB Community Server edition.
~~~

2. Conectarse a MongoDB vía CLI.

    - Configurar la variable de entorno
    - Crear la carpeta para almacenar la db:
        ~~~
        mkdir C:\data\db
        ~~~
    - Ejecutar el servidor de Mongo en la terminal
        ~~~
        mongod
        ~~~
    - Ejecutar el cliente Mongo en otra ventana de la terminal
        ~~~
        mongo
        ~~~

        
3. Crear una nueva base de datos llamada futbolfifa.
~~~
use futbolfifa
~~~
4. Crear una nueva collection llamada players.
~~~
db.createCollection("players")
~~~
5. Insertar 5 documentos en la collection players con datos básicos
(nombre, apellido, posición, fecha de nacimiento, etc).
~~~
db.players.insert([
    {name: "Lionel", surname: "Messi", position: "forward", birthdate: new Date(24,5,1987), height: 170},
    {name: "Leandro", surname: "Paredes", position: "midfielder", birthdate: new Date(29,5,1994), height: 180}, 
    {name: "Ángel", surname: "Di María", position: "midfielder", birthdate: new Date(14,1,1988), height: 180},
    {name: "Mauro", surname: "Icardi", position: "forward", birthdate: new Date(12,1,1993), height: 181},
    {name: "Keylor", surname: "Navas", position: "goalkeeper", birthdate: new Date(15,11,1986), height: 185}])
~~~
6. Listar todos los documentos de la collection players.
~~~
db.players.find()
~~~

7. Crear otras collections con documentos (ej. teams, games, etc).

~~~
db.createCollection("teams")

db.teams.insert(
    [{name: "PSG", city: "Paris", country: "France", foundation: 1970 },
    {name: "Rayo Vallecano", city: "Madrid", country: "Spain", foundation: 1924},
    {name: "Lille", city: "Lille", country: "France", foundation: 1944}])

~~~

## Actividad N° 2

1. Crear una nueva base de datos de un sistema de streaming de video (ej. Netflix, Flow, Amazon Prime) que permita almacenar movies.
~~~
use v-streaming
db.createCollection("movies")
~~~
2. Para cada movie, se debería guardar información como título
(String), year (Number), rating (Number, entre 1.0 y 5.0), genre
(String), description (String), actors (Array-String-), country
(String), income (Number), duration (Number).
~~~
{title: "The Godfather", year: 1972, rating: 5.0, genre: "Drama", "Description: "An organized crime dynasty's aging patriarch transfers control of his clandestine empire to his reluctant son.", actors: ["Marlon Brandon", "Al Pacino"], income: 150000000, duration: 175}
~~~

3. Agregar películas usando insert(), insertOne() & insertMany().

~~~
//Con insert()
db.movies.insert({title: "The Godfather", year: 1972, rating: 5.0, genre: "Drama", Description: "An organized crime dynasty's aging patriarch transfers control of his clandestine empire to his reluctant son.", actors: ["Marlon Brandon", "Al Pacino"], income: 150000000, duration: 175})

//con insertOne() - Devuelve el ID
db.movies.insertOne({title: "The Shawshank Redemption", year: 1994, rating: 4.8, genre: "Drama", Description: "Two imprisoned men bond over a number of years, finding solace and eventual redemption through acts of common decency.", actors: ["Morgan Freeman", "Bob Gunton", "Tim Robbins"], income: 100000000, duration: 142})

//con insertMany() - Devuelve los ID's insertados
db.movies.insertMany([{title: "Gladiator", year: 2000, rating: 3.8, genre: "Action", Description: "A former Roman General sets out to exact vengeance against the corrupt emperor who murdered his family and sent him into slavery.", actors: ["Russel Crowe", "Joaquin Phoenix", "Connie Nielsen"], income: 70000000, duration: 155}, {title: "Braveheart", year: 1995, rating: 3.2, genre: "Biography", Description: "Scottish warrior William Wallace leads his countrymen in a rebellion to free his homeland from the tyranny of King Edward I of England.", actors: ["Mel Gison", "Sophie Marceau", "Patrick McGoohan"], income: 200000000, duration: 158}])

~~~

4. Actualizar películas agregando el field highlighted=true a aquellas
con rating > 4.5.

~~~
db.movies.updateMany({rating: {$gte: 4.5}}, {$set :{highlighted : true}})
~~~






