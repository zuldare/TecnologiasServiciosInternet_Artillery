# Tecnologías y Servicios de Internet - Artillery
Practica para la asignatura _Tecnologías y Servicios de Internet_ del master MasterCloudApps of the URJC.
Pruebas con _Artillery_

# Enunciado
Se desea definir las pruebas de carga de la API REST de una aplicación que gestiona una
librería (proporcionada como Artillery_enunciado). Concretamente, se pide la elaboración
de un Test Script que contenga la configuración necesaria para poder hacer las pruebas de
carga con el toolkit Artillery junto a los resultados de su ejecución.

## Requisitos/Especificaciones
- Se establecerá una única fase de 40 segundos en la que habrá una tasa de 5
  usuarios/segundo.
- Solo se permitirán 8 conexiones simultáneas a la API.
- Se establecerá como requisito que el 95% de las peticiones no supere los 100ms de
  latencia
- Se establecerá como requisito un 0% de tasa de error.

*NOTA 1:* No es necesario que la ejecución cumpla estos requisitos (podemos tener distintas
máquinas con recursos más o menos limitados), solo hay que definirlos correctamente.

## Escenarios
A continuación se detallan los escenarios que se pretenden probar (se valorará darle nombre al escenario):
- Escenario 1: Consulta del primer Libro. Un usuario sin logear recupera todos los libros y pide el primero para ver más información
- Escenario 2: Creación de un Libro. Un usuario logueado crea un libro y después lo pide para comprobarlo.
- Escenario 3: Borrado de un Libro El administrador crea un libro, pero tras comprobarlo, lo borra y comprueba que ya no existe

*NOTA 2:* En los casos dónde un escenario realice acciones que requieran de autenticación, se realizará una petición de logIn previa.
  
*NOTA 3:* Para simular un comportamiento lo más parecido a la realidad, se fijará la probabilidad de que un usuario realice un escenario:
    - Escenario 1 (70%)
    - Escenario 2 (20%)
    - Escenario 3 (10%)
  
*NOTA 4:* Para las peticiones realizadas en cada escenario, se pide verificar los códigos de
  estado (HTTP) de la respuesta.

## Entregables
Los ficheros entregables serán los siguientes:
- solucion.yml -> Fichero con toda la configuración del Test Script
- output.json -> Fichero que contiene los resultados de una ejecución del test de carga (Fichero de salida)
- Ficheros adicionales que contengan datos que utilicen nuestro Test Script (en el caso de utilizarlos).
  

# Ayuda
- Se proporciona junto al código de la aplicación un fichero CSV:
    - books.csv: Contiene una colección de libros utilizables para generar algunos escenarios.

- A la hora de capturar el primer elemento de una lista (ya sea del cuerpo de la petición o de un atributo) puede realizarse usando una sintaxis similar a la de otras
  librerías de testing:
    - Ejemplo 1: “$[0].atributo”
    - Ejemplo 2: “$.atributoLista[0].atributo
 

# Uso

## Lanzar artillery
```script shell
    $ artillery run solucion.yml
    $ $ artillery run -e staging solucion.yml
```
# Author

👤 **Jaime Hernández Ortiz**

* Github: [@zuldare](https://github.com/zuldare)

Se debe tener[instalar JDK 8](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html) y [Maven](https://maven.apache.org/install.html) y
[artillery](https://artillery.io/)
