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