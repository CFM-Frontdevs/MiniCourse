## HTML + CSS + JS

Repasemos lo fundamental visto hasta ahora de HTML y CSS:

- Nuestro 'punto de acceso' a la web será un archivo `.html` (por ejemplo, index.html) que tendrá la estructura de la web

	```
	<!DOCTYPE html>
	<html>
		<head>
			<title>CFM Rocks</title>
		</head>
		<body>
			<h1>Welcome to CFM</h1>
			<p>
				Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsum velit debitis amet veritatis, dignissimos consequuntur totam harum modi sunt soluta nulla laborum unde a itaque animi dolores earum esse eos.
			</p>
		</body>
	</html>
	```

- Utilizaremos CSS para seleccionar elementos HTML y darles estilos
- Introduciremos el CSS vinculando un archivo `.css` externo (por ejemplo, myStyle.css) con un tag `<link>` en el 'head' del documento

	```
	// Link a archivo en nuestro proyecto
	<link rel="stylesheet" href="01-basicTags.css">

	// Link a archivo CDN de librería de terceros
	<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous">
	```

- Los archivos CSS contienen definiciones de estilos, con sintaxis `selector { propiedad: valor; propiedad: valor; ... }`

	```
	body{
		margin: 0 40px;
	}

	img{
		width: 250px;
	}

	p{
		font-family: "Comic Sans MS", cursive, sans-serif;
	}

	p.gordo{
		font-weight: bold;
	}

	.txt-azul{
		color: blue;
	}

	.descomunal{
		font-size: 100px;
	}
	```

Ahora toca completar la mezcla con un toque de Javascript aquí y allá.

### Insertar Javascript en el proyecto

En nuestro proyecto web, la manera principal con la que meter el Javascript es con el tag `<script></script>`. Este puede ser incluido tanto en el 'head' como en el 'body' del HTML. [En este link](http://www.w3schools.com/js/js_whereto.asp) tenéis una explicación rápida y con ejemplos de este tag.

```
<!DOCTYPE html>
<html>
	<head>
		<title>CFM Rocks</title>
		<script>
			function miFuncion (){
				/* código */
			}
			var miVariableGlobal = {
				utilidad1 : function(){
					/* código */
				},
				propiedad1 : function(){
					/* código */
				}
			};
			console.log('Código lanzado desde el head! ');
			console.log('Se lanza antes que el que encontramos en el body ya que al leer el archivo HTML es evaluado antes.');
			console.log('En este punto todavía no se ha cargado el HTML del body de la página. No podemos interactuar con el directamente (hay solución, que veremos)');
		</script>
	</head>
	<body>
		<h1>Welcome to CFM</h1>
		<p>
			Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsum velit debitis amet veritatis, dignissimos consequuntur totam harum modi sunt soluta nulla laborum unde a itaque animi dolores earum esse eos.
		</p>
		<script>
			function miFuncion2 (){
				/* código */
			}
			var miVariableGlobal2 = {
				utilidad1 : function(){
					/* código */
				},
				propiedad1 : function(){
					/* código */
				}
			};
			console.log('Código lanzado desde el body! ');
			console.log('En este punto ya se ha cargado todo el HTML de la web. ESTO ES IMPORTANTE SI QUEREMOS INTERACTUAR CON EL. No podemos seleccionar un elemento que no existe, ¿verdad?');
		</script>
	</body>
</html>
```

Otra forma de introducir código Javascript es desde archivos externos, de manera similar a como importamos dependencias CSS. Utilizamos el tag script: 

```
<script src="miCodigo.js"></script>
```
Donde src es el path al archivo que queremos importar. Al igual que en los ejemplos anteriores podemos introducir el tag en el 'head' y en el 'body'.

Utilizaríamos el tag de la misma manera para importar una librería de terceros desde un CDN. Por ejemplo, el tag para importar ember a nuestro proyecto sería:

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/ember.js/2.4.3/ember.min.js"></script>
```

### Selección de elementos HTML. Intro al DOM

Lo primero que hay que entender es que el poder de Javascript para hacer HTML dinámico y webs reactivas viene del DOM (leer ! [Document Object Model](http://www.w3schools.com/js/js_htmldom.asp)). De esto hay que quedarse con 'Document' y con 'Object'. 

Podemos acceder a este 'documento' con Javascript en cualquier momento. Existe en la variable global `document` y, sorpresa sorpresa, es un **objeto javascript**. Tiene propiedades, métodos que podemos utilizar y contiene TODO el HTML de la web y herramientas para:
- Crear/modificar/destruir elementos HTML
- Crear/modificar/destruir atributos de elementos HTML
- Crear/modificar/destruir propiedades CSS aplicadas a elementos HTML

¡Y lo más importante! Nos permite reaccionar ante 'eventos' de los elementos HTML. Estos eventos pueden ser considerados como mensajes que nos envían los elementos de la web para mantenernos informados de su estado. Por ejemplo:
- Me han pulsado!
- Mi valor ha cambiado!
- El usuario ha pulsado una tecla
- He cargado todos los elementos correctamente!
- El usuario lleva aplastándome un rato ...
- He terminado de cargar la foto
- ...

Existe una larga lista de eventos HTML y veremos como sacarles partido. Por ahora, nos centraremos en utilizar el DOM para seleccionar elementos HTML y en que podemos hacer con el objeto seleccionado.

### Eventos

// TODO

### Ejemplo sencillo de formulario 'Login'

// TODO