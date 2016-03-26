## Intro to Javascript

Si bien el Javascript nació como en lenguaje para el servidor, para muchos el primer encontronazo con Javascript llega cuando quieren interactuar con el HTML y hacer interactivo, reactivo. Por ejemplo, hacer que 'algo' pase cuando se pulsa un botón. Lanzar un proceso de petición de datos cuando se accede a una URL. Animar la pantalla ante las acciones del usuario o de llegada de nuevos datos desde el servidor. ¡Todo lo divertido, vaya!

El mundillo del javascript es cada vez más grande. Más estricto o fino, si queréis. Pero no hace falta ser limpio para jugar. El lenguaje permite flexibilidad de desarrollo y es muy comodo trabajar con código de terceros que hará nuestra vida mucho más facil. 

Empezaremos con las bases más básicas, inherentes a casi todo lenguaje de programación:

- [Creación de variables y los tipos](#declaración-de-variables)
- [Funciones y encadenado](#funciones-y-encadenado)
- [Un poquito sobre contexto](#un-poquito-sobre-contexto)
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

// DECLARACIÓN DE UNA FUNCIÓN

function nombreDeLaFuncion (argumentosQueRecibe) { /*código aquí*/ };

// Función asginada a una variable. Lo llamado 'function expresion'
// El nombreDeLaFuncion es opcional, aunque recomendado.
var miFuncion = function nombreDeLaFuncion (argumentos) { /*código aquí*/ };
```

Cada tipo de variable tiene sus propias característias y métodos privados (funciones con las que haremos cosas como ordenar, recortar, filtrar, ...).

**IMPORTANTE:** cualquier variable o función que declaremos en javascript debemos considerarla *UN OBJETO JAVASCRIPT*. Los objetos en javascript tienen un nombre, propiedades y métodos. Podremos acceder al objeto por su nombre, aunque ya veremos que dependiendo de donde estemos en el código tendrémos acceso a unas variables u otras. 

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

Todos [estos ejemplos](/03-Javascript/01-ejemplos-variables.md) se pueden copiar y pegar en la consola Javascript del navegador, como ya hemos visto con el ejemplo de `console.log()`.



### Funciones y encadenado

Una función:
- Es un bloque de código con una misión
- Retorna algo, aunque sea 'nada'
- Puede recibir parámetros
- Ha de ser invocada para ser ejecutada
- Puede ser pasada como parámetro a otra función

Ya hemos visto que podemos crear funciones de varias maneras:

```
console.log('-------------------------------------');
console.log('---------SEPARACIÓN INICIAL----------');
console.log('-------------------------------------');

// Declaración

function myFuncion (parametro1, parametro2) {
	// Hago algo ...
	console.log('Parámetro 1: ' + parametro1);
	console.log('Parámetro 2: ' + parametro2);
}

// Expresión de una función (asignada como valor de una variable)

var otraFuncion = function (parametro1, parametro2) {
	// Hago algo ...
	console.log('Parámetro 1: ' + parametro1);
	console.log('Parámetro 2: ' + parametro2);
}

// Como valor de un objeto

var funciones = {
	myFuncion: function (parametro1, parametro2) {
		// Hago algo ...
		console.log('Parámetro 1: ' + parametro1);
		console.log('Parámetro 2: ' + parametro2);
	},
	otraFuncion: function (parametro1, parametro2) {
		// Hago algo ...
		console.log('Parámetro 1: ' + parametro1);
		console.log('Parámetro 2: ' + parametro2);
	}
};
```

En todos estos casos, ninguna de las funciones se ejecuta. Solo se declaran. Podemos comprobar estos copiando y pegando el código en la consola javascript del navegador. Veremos que no se presenta ningún log en la consola.

No obstante, ahora tenemos a nuestra disposición estas funciones. Lo comprobamos **llamando** a las funciones a través de su nombre o ruta de claves en el objeto *seguido de unos _paréntesis_*: `nombreDeLaFuncion()`. Dentro de los paréntesis podemos pasar todos los parámetros que queramos con los valores que sea. Freedom +!!!

Vemos ejemplos de llamadas y envio de parámetros, utilizando las funciones recién creadas:

```
console.log('-------------------------------------');
console.log('---------SEPARACIÓN INICIAL----------');
console.log('-------------------------------------');

// Llamada básica, sin valores. Parámetros recibidos = 'undefined'
console.log('Funciones llamadas sin pasar parámetros: ');
myFuncion();
otraFuncion();
funciones.myFuncion();
funciones.otraFuncion();

// Envio de parámetros a una función. Pueden ser de todo tipo
// Nulos, undefined, ...
console.log('Llamada con valores nulos o no definidos: ');
myFuncion(null, undefined);

// Números, strings, ...
console.log('Llamada con números o strings: ');
otraFuncion(89236, 'no soy undefined');

// Arrays, Objetos
console.log('Llamada con Arrays u Objetos: ');
var arr = [1,2,3,4,5];
var obj = {nombre: 'Fer', apellido: 'Bordallo'};
funciones.myFuncion(arr, obj);

// Funciones!
console.log('Llamada con funciones: ');
var func = function(){
	// Código que le pasamos a otra funcion para que la ejecute más tarde (o no)
	// Cuando se pasa una función a otra para que esta la ejecute en un futuro se le dá el nombre de 'CALLBACK'.
}
funciones.otraFuncion(func);

// Más parámetros de los que acoje la función. No habrá errores ni quejas ... sencillamente no se utilizarán
console.log('Llamada con parámetros de más: ');
funciones.otraFuncion(1,2,3,4,5,6);
```

Las funciones contienen código y devuelven un valor (objeto javascript de algún tipo). Pueden devolver DE TODO: undefined, null, object, function, array, string, number, boolean, ... creo que no hay más. Si los hay, pueden ser devueltos como resultado.

Esta respuesta tendrá propiedades y métodos, como todo objeto javascript, y podemos llamarlos de forma **encadenada**. Por ejemplo, sabemos TODOS los objetos javascript tienen un método `toString()` que podemos invocar sobre ellos y que nos devolverá el valor del objeto como un string:

```
var objeto = {
	name: 'fer',
	apellido: 'bor',
	altura: 160,
	familia: [1,2,3,4,5,6]
};
// Vereís que lo devuleto no es especialmente interesante en este caso
objeto.toString();
```

Supongando que tenemos una función que nos al ser invocada devuelve este objeto. Podríamos encadenar el método `toString()` con la invocación de la función. Quedaría así:

```
function pedirObjeto(){
	return objeto = {
		name: 'fer',
		apellido: 'bor',
		altura: 160,
		familia: [1,2,3,4,5,6]
	};
}

pedirObjeto().toString();
```

##### Ejemplos de uso

Aquí tenéis [ejemplos](/03-Javascript/02-ejemplos-funciones.md) básicos de uso de funciones. Se pueden copiar y pegar en la consola Javascript del navegador.


### Un poquito sobre contexto

El contexto, o **Scope**, es el alcance que tienen nuestras funciones y variables. Dependiendo de en que lugar se esté ejecutando nuestro código o desde donde ha sido invocado, tendremos acceso a una serie de variables u otras. 

Existen dos contexto principales: *local* y *global*. [Aquí](http://www.w3schools.com/js/js_scope.asp) tenéis una breve introducción con ejemplos de los contextos local y global. 

Una forma útil de ver el contexto en el que nos encontramos es la palabra reservada `this`. Vemos como dependiendo de donde estemos, 'this' tiene un valor u otro.

```
// 'this' contiene el contexto global. Si esto se ejecuta directamente en la consola del navegador con about:blank, this = window.

console.log(this);

// 'this' dentro de la función es el global ya que la función ha sido ejecutada desde global

function unaFunction (parametro){
	console.log(this);
}

unaFunction();


// 'this' dentro de la función declarada como un valor de un objeto contiene el objeto
var objeto = {
	nombre: 'fer',
	apellido: 'bor',
	combinado: function(){
		return this.nombre + ' ' + this.apellido;
	},
	funcion: function() {
	    return this;
	}
};

console.log(objeto.funcion());
```

Para más información sobre la palabra reservada 'this', os recomiendo [este link](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Operadores/this) que tiene ejemplos y entra en más detalle. 

\* Aviso: Es posible que con el tema de contexto alguno se enfrente a perder la cordura en algún momento xD ... Pasiensia ...

Os enseño un ejemplo de como se pude acceder a otros contextos de forma rápida, aunque muy poco recomendada:

```
// Guardamos una referencia al 'this' global, en este caso de nuestro interés por las funciones en el el declaramos

var that = this;

console.log(this);

// Función declarada a nivel de contexto global (el 'this' actual y que hemos guardado en 'that')

function nombreCompleto(nombre, apellido){
	return nombre + ' ' + apellido;
}

// 'this' dentro de la función declarada como un valor de un objeto contiene el objeto. Esto nos da acceso a todas su propiedades

var objeto = {
	nombre: 'fer',
	apellido: 'bor',
	combinado: function(){
		return that.nombreCompleto(this.nombre, this.apellido);
	},
	funcion: function() {
	    return [this, that];
	}
};

// Llamamos a las distintas funciones que contiene nuestro objeto y vemos como 'this' y 'that' contienen contextos distintos
console.log(objeto.funcion());
console.log(objeto.combinado());
```


