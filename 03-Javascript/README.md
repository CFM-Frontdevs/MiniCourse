## Intro to Javascript

Si bien el Javascript nació como en lenguaje para el servidor, para muchos el primer encontronazo con Javascript llega cuando quieren interactuar con el HTML y hacer interactivo, reactivo. Por ejemplo, hacer que 'algo' pase cuando se pulsa un botón. Lanzar un proceso de petición de datos cuando se accede a una URL. Animar la pantalla ante las acciones del usuario o de llegada de nuevos datos desde el servidor. ¡Todo lo divertido, vaya!

El mundillo del javascript es cada vez más grande. Más estricto o fino, si queréis. Pero no hace falta ser limpio para jugar. El lenguaje permite flexibilidad de desarrollo y es muy comodo trabajar con código de terceros que hará nuestra vida mucho más facil. 

Empezaremos con las bases más básicas, inherentes a casi todo lenguaje de programación:

- [Creación de variables y los tipos](#declaracion-de-variables)
- Funciones y encadenado
- Lógica básica
- Búcles
- Interacción con el HTML

Esto nos dará la puntita del iceberg, pero suficientes herramientas para hacer cosas interesantes. Para ver todo esto y MUCHO MÁS, os recomiendo que vayáis directos a los [tutoriales de Javascript](http://www.w3schools.com/js/default.asp) de w3school. Si os vale con un resumen rápido de unos cuantos conceptos, seguíd leyendo.

Después veremos como valernos de librerías de terceros, investigando más a fondo el potencial que le podéis sacar al JS. 


### LA CONSOLA - Chrome Dev Tools

No veo mejor sitio para empezar que la consola Javascript que nos ofrecen prácticamente todos los navegadores. Accedéd a la url `about:blank`. Una página en blanco. Hecho esto, solo hay que abrir las herramientas de desarrollador del navegador. 

Hay varias formas. En chrome conozco:
- F12
- Botón derecho sobre la pantalla >> seleccionar 'Inspeccionar'
- Ir al botón de menu del navegador >> 'Más Herramientas' >> 'Herramientas de Desarrollador'

Y después seleccionando la pestaña 'Consola' o 'Console' de la barra superior:

![alt text][img-about-blank-console]

[img-about-blank-console]: https://github.com/CFM-Frontdevs/MiniCourse/blob/RC/03-Javascript/img/about-blank-and-tools.png?raw=true "About blank with Console open"

\* Tip: Aunque no es lo más aconsejable para muchas cosas, si es muy útil. El uso de  `console` os podrá ayudar mucho en el proceso de desarrollo. Básicamente se puede llamar a la API de console para mostrar mensajes en la consola Javascript. [Link a más info sobre console ...](https://developer.mozilla.org/en-US/docs/Web/API/Console/log).

Recomiendo aprender a usar: 

```
console.log()
console.info()
console.time() && console.timeEnd()
console.error()
console.warn()
```

##### Ejemplo de console

Copia y pega esto en la consola de Chrome (abierta en about:blank) y pulsa enter:

```
console.log('CFM is Awesome!')
```

La consola te responderá con el mensaje que hemos introducido.

### Declaración de variables

Declararemos nuevas variables con la palabra reservada `var`. Podemos hacerlo sin valor inicial ni tipo inicial, con un tipo inicial y con valor inicial:

```
// Declaración sin más para uso futuro de la variable. Esta variable verdaderamente SI tiene valor y tipo. 'undefined'.
var paLuego;

// Declaración con tipo inicial

var objeto = {};
var vectorArray = [];
var stringDeCaracteres = '';
var numero = 0; // Esta declaración da tipo y valor incial;
var nulo = null;
var funcion = function(){}; // Con esta nos estamos adelantando un poco 
```

Cada tipo de variable tiene sus propias característias y métodos privados (funciones con las que haremos cosas como ordenar, recortar, filtrar, ...).

IMPORTANTE: cualquier variable o función que declaremos en javascript debemos considerarla *UN OBJETO JAVASCRIPT*. Los objetos en javascript tienen un nombre, propiedades y métodos. Podremos acceder al objeto por su nombre, aunque ya veremos que dependiendo de donde estemos en el código tendrémos acceso a unas variables u otras. 

Probad a acceder al objeto `window` desde la consola en de chrome. Para acceder a sus propiedades y métodos pondremos un punto `.` seguido del nombre de la propiedad o método. Este a su vez puede contener un *objeto* o *valor*. Por ejemplo:

```
console.log(window);
// Esto pinta en la consola el objeto window. Si lo desplegais podréis ver todas sus propiedades

console.log(window.length);
// La propiedad 'length' contiene el valor de la longitud del objeto. Al no ser un array, es igual a 0.

console.log(window.Audio);
// El objeto window.Audio contiene un método que forma parte de la API Web de los navegadores para trabajar con Sonido.

```

##### Ejemplos de uso

Todos estos ejemplos se pueden copiar y pegar en la consola Javascript del navegador, como ya hemos visto con el ejemplo de `console.log()`.


###### Número

- [Referencia del objeto Número](http://www.w3schools.com/jsref/jsref_obj_number.asp)
- [Referencia del objeto Math para trabajo con números](http://www.w3schools.com/jsref/jsref_obj_math.asp)

```
console.log('-------------------------------------');
console.log('---------SEPARACIÓN INICIAL----------');
console.log('-------------------------------------');

var numero = 0;
console.log('Nuestro número inicial:');
console.log(numero);

// Podemos reasignar la variable a otro valor y realizar operaciones aritméticas básicas
// Asignación
numero = 5;
console.log('Número reasignado a 5:')
console.log(numero);

// Suma a si mismo (+)
numero = numero + 5;
console.log('Número más 5:');
console.log(numero);

// Resta (-)
numero = numero - (14 + 25);
console.log('Número menos la suma de 14 y 25:');
console.log(numero);

// Multiplicación (*)
numero = numero * 3;
console.log('Número por 3:');
console.log(numero);

// División
numero = numero / 11;
console.log('Número dividido por 11:');
console.log(numero);

// ---- USO DEL OBJETO 'MATH' PARA TRABAJO CON NÚMEROS ----

// Redondeo hacia abajo (también lo hay hacia arriba y nuetro)
numero = Math.floor(numero);
console.log('Número redondeado hacia abajo:');
console.log(numero);
```

###### String (cadena de caracteres)

- [Referencia al objeto String](http://www.w3schools.com/jsref/jsref_obj_string.asp)

```
console.log('-------------------------------------');
console.log('---------SEPARACIÓN INICIAL----------');
console.log('-------------------------------------');


var string = 'Cadena inicial';
console.log('Nuestra cadena de caracteres inicial:');
console.log(string);

// Concatenación de strings
var string2 = ': más caracteres';
string = string.concat(string2);
console.log('Cadena de caracteres alargada:');
console.log(string);

// Longitud de cadena
console.log('Longitud de nuestra cadena:');
console.log(string.length);

// Acceso a una posición de la cadena. La primera posición es '0'
console.log('Letra ubicada en la posición 5 (sexta letra) de la cadena:');
console.log(string.charAt(5));

// Buscar si en la cadena existe una combinación de uno o más caracteres
console.log('Preguntamos si existe en la cadena la combinación de letras "ract".');
console.log('Nos devuelve un valor booleano: true o false');
console.log(string.includes('ract'));

// Separar la cadena en un Array de strings. Muy interesante muy a menudo
console.log('Separamos la cadena por cada caracter:');
console.log(string.split(''));

console.log('Separamos la cadena por el simbolo de los dos puntos:');
console.log(string.split(':'));
console.log('*** Nota: esto quita del resultado el caracter utilizado para hacer la separación.');
```


###### Array

- [Referencia al objeto Array](http://www.w3schools.com/jsref/jsref_obj_array.asp)

```
console.log('-------------------------------------');
console.log('---------SEPARACIÓN INICIAL----------');
console.log('-------------------------------------');


var array = [1, 2, 3, 4, 5];
console.log('Nuestro array inicial: ');
console.log(array);

// Introducir nuevo número al array
array.push(6);
console.log('Array ampliado con un 6:');
console.log(array);

// Borrar el último elemento del array
array.pop();
console.log('Array menos el 6:');
console.log(array);

// Borrar el primer elemento del array
array.shift();
console.log('Array menos el 1:');
console.log(array);

// Introducir nuevo número en la primera posición del array
array.unshift(1);
console.log('Array ampliado con un 1:');
console.log(array);

// Longitud del array (número de elementos). Es una propiedad de todo array
// Podemos guardar la longitud en otra variable, representarla en consola, utilizarla para lanzar un búcle de longitud definida, ...
array.length;
console.log('Longitud del array:');
console.log(array.length);
var longitudArray = array.length;

// Acceder a posiciones del Array. La primera posición es la '0', la segunda la '1' y así sucesivamente.
console.log('Primer número en el array: ');
console.log(array[0]);
```


