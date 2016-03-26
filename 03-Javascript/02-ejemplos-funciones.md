###### Funciones

- [Referencia básica de Function](http://www.w3schools.com/js/js_functions.asp)

\* Recomendado: revisar los mini tutoriales de [definición de funciones](http://www.w3schools.com/js/js_function_definition.asp), [parámetros](http://www.w3schools.com/js/js_function_parameters.asp), [invocación](http://www.w3schools.com/js/js_function_invocation.asp) y [closures](http://www.w3schools.com/js/js_function_closures.asp) (parte de la mágia del javascript).

```
console.log('-------------------------------------');
console.log('---------SEPARACIÓN INICIAL----------');
console.log('-------------------------------------');

// A jugar con las funciones se ha dicho

// Creamos una variable fecha usando el contructor básico de javascript 
// NOTA: utiliza la hora del dispositivo

var fechaActual = new Date();
console.log('Variable fecha actual: ' + fechaActual);


// Definimos una función que recibe una fecha en su formato String y devuelve la misma fecha en millisegundos pasados desde el '01 Enero 1970 00:00:00 UTC'.

function fechaEnMillis (fecha){
	// Utilizamos el método 'getTime' del que disfrutan todos los objetos Date. Es una función por lo tanto la invocamos con paréntesis
	// - - - - - 
	// Utilizamos la palabra 'return' para finalizar la función y devolver un valor

	return fecha.getTime();
}

// Invocamos la función fechaEnMillis, guardamos el valor recibido y lo logamos en la consola

var fechaActualEnMillisegundos = fechaEnMillis(fechaActual);
console.log('Hemos invocado la función y recibido el siguiente valor: ');
console.log(fechaActualEnMillisegundos);
```

Podemos hacer cosas interesantes si pasamos una función a otra:

```
console.log('-------------------------------------');
console.log('---------SEPARACIÓN INICIAL----------');
console.log('-------------------------------------');

// Definimos una función que devolverá un objeto Date con la fecha actual

var nuevaFecha = function(funcionMillisegundos){
	var fecha = new Date();
	return funcionMillisegundos(fecha);
};

// Definimos una función que recibe una fecha en su formato String y devuelve la misma fecha en millisegundos pasados desde el '01 Enero 1970 00:00:00 UTC'.

function fechaEnMillis (fecha){
	// Utilizamos el método 'getTime' del que disfrutan todos los objetos Date. Es una función por lo tanto la invocamos con paréntesis
	// - - - - - 
	// Utilizamos la palabra 'return' para finalizar la función y devolver un valor

	return fecha.getTime();
}

var laFechaQuePedi = nuevaFecha(fechaEnMillis);
console.log(laFechaQuePedi);
```

Aquí lo que vemos es una función siendo pasada a otra y ejecutandose bajo demanda. También vemos un ejemplo de el uso de `return` en cascada:

1. Declaramos las funciones
2. Invocamos a la primera, enviando la segunda como parámetro, pidiendo que se guarde el resultado devuelto en la variable 'laFechaQuePedi'
3. Se crea la nueva fecha
4. RETORNAMOS una invocación! Esto implica que se ejecutará la segunda función, a la que pasamos la fecha recién creada. Lo que esta función devuelva será lo que devuelva la primera y acabe en la variable 'laFechaQuePedi'