# Asi se crea un controllador y eso retorna un hola mundo  
        public class HomeController : Controller
        {
            public IActionResult Index()
            {
                return Content("Hola, mundo");
            }
        }

# esto es otra cosita relacionada con LINQ
LINQ es un conjunto de extensiones integradas en el lenguaje C# que nos permiten trabajar de manera cómoda y rápida con colecciones de datos.

Para entender cómo funcionan las consultas LINQ, vamos a hacer un ejemplo simple. Supongamos que tenemos una lista de números, y queremos saber cuáles son los números pares.

En C# clásico, podríamos escribir el siguiente código para obtener esta información:

            C#
            // Lista de números
            int[] numeros = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

            // Obtenemos los números pares
            List<int> numerosPares = new List<int>();
            for (int i = 0; i < numeros.Length; i++) {
            if (numeros[i] % 2 == 0) {
                numerosPares.Add(numeros[i]);
            }
            }
Utiliza el código con precaución. Más información
Este código funciona, pero es un poco repetitivo y difícil de leer.

Con LINQ, podemos escribir el siguiente código para obtener el mismo resultado:

        C#
        // Lista de números
        int[] numeros = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

        // Obtenemos los números pares con LINQ
        var numerosPares = numeros.Where(x => x % 2 == 0);
        Utiliza el código con precaución. Más información
        Este código es mucho más conciso y fácil de leer.

En general, las consultas LINQ se pueden dividir en dos partes:

La expresión de consulta: Es la parte que especifica qué datos queremos obtener. En el ejemplo anterior, la expresión de consulta es numeros.Where(x => x % 2 == 0).
La implementación de la consulta: Es la parte que se encarga de ejecutar la consulta y devolver los resultados. En el ejemplo anterior, la implementación de la consulta es el método Where() del objeto IEnumerable< int>.
En el caso del ejemplo anterior, la implementación de la consulta se realiza en el compilador. Sin embargo, en algunos casos, la implementación de la consulta se puede realizar en tiempo de ejecución. Por ejemplo, si queremos ordenar los resultados de la consulta, la implementación de la consulta se realizará en tiempo de ejecución.