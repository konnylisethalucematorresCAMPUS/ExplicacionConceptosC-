# ¿Que es LINQ?

<p>LINQ Es un conjunto de extensiones integradas en el lenguaje C#, que nos permite trabajar de manera cómoda y rápida con colecciones de datos, como si de una base de datos se tratase.</p>

# 
El primer paso es especificar el origen de datos. En C#, como en la mayoría de los lenguajes de programación, se debe declarar una variable antes de poder usarla. Por ejemplo, si queremos trabajar con una colección de objetos de tipo Customer, declararíamos una variable de tipo ``` IEnumerable< Customer > ```

<h2>Que es IEnumerable< Customer > </h2>

   - <p>IEnumerable< Customer > es un tipo de dato en C# que se utiliza para representar una colección o conjunto de elementos, en este caso, de tipo "Customer" (clientes). Puedes pensar en IEnumerable< Customer > como una lista de clientes en la que puedes realizar diferentes operaciones, como recorrer la lista, buscar elementos o filtrarlos</p>

    <h4>Ejemplo</h4>
   - Por ejemplo, imagina que tienes una tienda en línea y quieres mantener una lista de tus clientes. Puedes crear una variable llamada "listaDeClientes" de tipo IEnumerable< Customer > para almacenar todos los clientes que se registran en tu tienda en línea. 

            IEnumerable<Customer> listaDeClientes = new List<Customer>
            {
                new Customer { Nombre = "Juan", Edad = 30 },
                new Customer { Nombre = "María", Edad = 25 },
                new Customer { Nombre = "Pedro", Edad = 35 }
            };

    - En este ejemplo, hemos creado una lista de clientes donde cada cliente tiene un nombre y una edad. Ahora puedes usar LINQ y IEnumerable< Customer > para hacer cosas como buscar clientes con ciertas edades o imprimir la lista de clientes en un orden específico, lo que facilita la manipulación de datos.  


# ¿como utilizar LINQ?
<p>Para usar LINQ, primero debes decirle de dónde vienen tus datos. En C# y en muchos otros lenguajes de programación, necesitas decirle al programa qué tipo de datos estás manipulando antes de poder trabajar con ellos. Por ejemplo, si estás trabajando con una lista de clientes, primero declararías una variable para decirle al programa que estás trabajando con una colección de objetos de tipo "Customer"</p>


# continuacion de LINQ
<p>Una vez que tenemos el origen de datos, podemos empezar a escribir nuestra consulta LINQ. Las consultas LINQ se componen de una serie de cláusulas, cada una de las cuales realiza una operación específica sobre los datos.

La cláusula más importante de LINQ es la cláusula from. Esta cláusula especifica el origen de datos que queremos consultar. Por ejemplo, la siguiente cláusula from especifica que queremos consultar la colección de objetos Customers:</p>
<h4>ejemplo</h4>

        var customers = new List<Customer>
        {
            new Customer { Id = 1, Name = "John Doe" },
            new Customer { Id = 2, Name = "Jane Doe" },
            new Customer { Id = 3, Name = "Peter Parker" }
        };

        // LINQ query
        var customersQuery = from customer in customers select customer;


Una vez que hemos especificado el origen de datos, podemos utilizar otras cláusulas LINQ para filtrar, ordenar y transformar los datos. Algunas de las cláusulas más comunes son:

Where: Filtra los datos en función de una condición. Por ejemplo, la siguiente cláusula where filtra la colección de clientes a aquellos cuyo nombre es "John Doe":

<h4>ejemplo</h4>

        var customersQuery = from customer in customers where customer.Name == "John Doe" select customer;

Order by: Ordena los datos en función de una o varias propiedades. Por ejemplo, la siguiente cláusula orderby ordena la colección de clientes por su nombre:

<h4>ejemplo</h4>

        var customersQuery = from customer in customers orderby customer.Name select customer;

Select: Transforma los datos en una nueva colección. Por ejemplo, la siguiente cláusula select crea una nueva colección que contiene los nombres de los clientes:

<h4>ejemplo</h4>

        var customerNamesQuery = from customer in customers select customer.Name;


<p>Podemos combinar varias cláusulas LINQ para crear consultas complejas. Por ejemplo, la siguiente consulta filtra la colección de clientes a aquellos cuyo nombre es "John Doe" y ordena la colección por su nombre:</p>
<h4>Ejemplo</4>

        var customersQuery = from customer in customers where customer.Name == "John Doe" orderby customer.Name select customer;

<p>Una vez que hemos escrito nuestra consulta LINQ, podemos ejecutarla utilizando el método ToList(). Este método devuelve una nueva colección que contiene los resultados de la consulta. Por ejemplo, para ejecutar la consulta anterior y obtener una lista de clientes cuyo nombre es "John Doe" ordenados por su nombre, utilizaríamos el siguiente código:</p>
<h4>Ejemplo</4>


        var customers = customersQuery.ToList();

<h3>LINQ es una herramienta muy poderosa para trabajar con colecciones de datos en C#. Nos permite escribir consultas complejas de forma sencilla y elegante.</h3>

Ejemplo completo: El siguiente código muestra un ejemplo completo de cómo utilizar LINQ para consultar una colección de datos:

 <h4>Ejemplo completo</h4>

        using System;
        using System.Collections.Generic;

        public class Customer
        {
            public int Id { get; set; }
            public string Name { get; set; }
        }

        public class Program
        {
            public static void Main(string[] args)
            {
                // Create a list of customers
                var customers = new List<Customer>
                {
                    new Customer { Id = 1, Name = "John Doe" },
                    new Customer { Id = 2, Name = "Jane Doe" },
                    new Customer { Id = 3, Name = "Peter Parker" }
                };

                // LINQ query
                var customersQuery = from customer in customers where customer.Name == "John Doe" orderby customer.Name select customer;

                // Execute the query
                var customers = customersQuery.ToList();

                // Print the results
                foreach (var customer in customers)
                {
                    Console.WriteLine(customer.Name);
                }
            }
        }

<h4>Este código produce la siguiente salida:</h4>

            John Doe

<p>Aqui finaliza el ejemplo y explicacion</p>

# PALABRAS MUY IMPORTANTES QUE SON Y QUE HACEN 
var: "Var" es una forma de declarar una variable en programación sin decir exactamente qué tipo de dato es. El programa deducirá automáticamente el tipo de dato basándose en el valor que le asignas a la variable. Se utiliza para hacer que la declaración de variables sea más flexible y menos repetitiva.

from: "From" se usa en LINQ para especificar la fuente de datos, es decir, de dónde vienen los datos con los que quieres trabajar. Puedes pensar en ello como decirle al programa de dónde tomará la información que necesitas.

where: "Where" se utiliza en LINQ para filtrar los datos de la fuente. Le dices al programa que solo deseas los datos que cumplan con ciertas condiciones. Es como crear un conjunto de reglas para seleccionar los datos que te interesan.

select: "Select" se usa en LINQ para decidir qué información específica deseas obtener de los datos que has seleccionado previamente. Puedes elegir las propiedades o valores que te interesan y obtener solo esos, en lugar de todo el conjunto de datos.

Order by: "Order by" se utiliza para ordenar los datos en un cierto orden, por ejemplo, de manera ascendente o descendente. Puedes usarlo para organizar tus datos de una manera específica, como ordenar una lista de clientes alfabéticamente por sus nombres.

En resumen, estas palabras clave se utilizan en LINQ para hacer consultas y manipulaciones en colecciones de datos de manera más sencilla y organizada. "Var" es para declarar variables de manera más flexible, "from" indica de dónde provienen los datos, "where" filtra los datos según condiciones, "select" elige qué información obtener, y "Order by" se utiliza para ordenar los datos. Esto facilita la búsqueda y manipulación de datos en programación.

# 
<p></p>



# 
<p></p>


# 
<p></p>