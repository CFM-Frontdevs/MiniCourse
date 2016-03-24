## Intro to CSS

Confieso. No soy diseñador. Lo que veremos aquí serán meras pinceladas de CSS con las que entender su objetivo principal y como lo lleva acabo. 

Con CSS describimos la presentación que ofreceremos. Definimos como queremos que se rendericen los elementos HTML (o XML) en la pantalla.

### Estructura básica

Los archivos CSS (Cascading Style Sheets) son procesadas de arriba a abajo y en el orden en que son importados los archivos. La descripción más básica que se puede hacer consta de dos partes: el selector del elemento que 'retocaremos' y las características que queremos que tenga. Podéis ver un tutorial rápido de sintaxis de CSS [aquí](http://www.w3schools.com/css/css_syntax.asp).

```
	body{
		width: 100%;
		height: 300px;
		background: red;
		font-size: 40px;
		...
	}
```

En este caso vemos como selector `body{}` seguido de unas llaves. Dentro definimos las características del elemento. En este caso: el ancho (ejemplo de uso de porcentajes), alto (ejemplo de pixels), color de fondo ([se pueden usar otros colores](http://www.w3schools.com/css/css_colors.asp) por palabra o por rgb/rgba...) y tamaño de letra en pixels.


### Ya tengo mi archivo .html, ¿Donde va el CSS?

El código CSS se puede 'meter' en la web de varias formas. Se recomienda siempre utilizar archivos .css, dejando el código separado del HTML. No obstante, existen otras formas.

##### The horror ...

La primera, y más despreciada por los diseñadores que conozco, es lo que se llama *estilo offline*. Utilizamos el atributo `style`, compartido por los elementos HTML, para insertar características CSS en el elemento. Ejemplo de estilo offline en un párrafo:

```	
	<!DOCTYPE html>
	<html>
		<head>
			<title>Page Title</title>
		</head>
		<body>
			<div>
				<h1>Titulo</h1>
				<hr class="divisor">
				<p style="background: red; font-size: 20px; width: 50%; margin-left: 20%">
					Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae illum suscipit magni perferendis temporibus, quos sed unde. Minus consequatur animi, vel eos! Earum possimus doloribus ea numquam obcaecati, mollitia cumque.
				</p>
			</div>
		</body>
	</html>
```

La descripción `style="background: red; font-size: 20px; width: 50%; margin-left: 20%"` se aplicaría al elemento. Uno de los mayores problemas que presenta este sistema es su falta de modularidad y su claro destino a la repetición de código por todas partes.

##### Interno

El sistema de estilos como 'hoja' interna se aplica utilizando la etiqueta HTML `<style>` dentro del `<head>` de nuestro HTML. Tampoco es muy recomendado contenedor de los estilos de una web, ya que un diseño complejo puede tener cientos, si no miles, de lineas.

```	
	<!DOCTYPE html>
	<html>
		<head>
			<title>Page Title</title>
			<style>
				#parrafo-especial{
					background: red;
					font-size: 20px; 
					width: 50%; 
					margin-left: 20px;
				}
				.divisor{
					color: yellow;
				}
				h1{
					font-size: 60px;
				}
			</style>
		</head>
		<body>
			<div>
				<h1>Titulo</h1>
				<hr class="divisor">
				<p id="parrafo-especial">
					Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae illum suscipit magni perferendis temporibus, quos sed unde. Minus consequatur animi, vel eos! Earum possimus doloribus ea numquam obcaecati, mollitia cumque.
				</p>
			</div>
		</body>
	</html>
```

##### Externo

En este utilizamos el elemento `<link>` en el `<head>` para indicar la dependecia de un archivo externo y que vaya  cogerlo. El atributo `href` apuntará a nuestro archivo, como 'path' de referencia desde el archivo HTML, o a una URL (nuestra o de terceros). Este es el método más común para importar CSS a nuestra página. Vemos el archivo HTML:

```	
	<!DOCTYPE html>
	<html>
		<head>
			<title>Page Title</title>
			<link rel="stylesheet" type="text/css" href="mystyle.css">
		</head>
		<body>
			<div>
				<h1>Titulo</h1>
				<hr class="divisor">
				<p id="parrafo-especial">
					Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae illum suscipit magni perferendis temporibus, quos sed unde. Minus consequatur animi, vel eos! Earum possimus doloribus ea numquam obcaecati, mollitia cumque.
				</p>
			</div>
		</body>
	</html>
```

Y el archivo "mystyle.css" (que en este caso estaría ubicado en la misma carpeta que el HTML):

```	
	#parrafo-especial{
		background: red;
		font-size: 20px; 
		width: 50%; 
		margin-left: 20px;
	}
	.divisor{
		color: yellow;
	}
	h1{
		font-size: 60px;
	}
```

Para una referencia completa sobre como importar CSS, leer este [tutorial](http://www.w3schools.com/css/css_howto.asp).


### Seleccionar elementos HTML

Los elementos HTML se pueden seleccionar de muchas formas: directa, anidadas, por clase, por clase y padre y ..... Las selecciones básicas más comunes son:

- Selección por elemento: `p{}, body{}, h1{}, img{}, ...`
- Selección por ID: `<h1 id="portada"></h1>   -->  #portada{}`
- Selección por clase: `<h1 class="portada"></h1>   -->  .portada{}`

La gran diferencia entre ID y clase residen en que el ID de elemento ha de ser único en el arbol HTML. Sin embargo, una clase de se puede ver repetida en varios elementos. 

La selección de elementos sin embargo puede hacerse de maneras mucho más complejas, juntando estos conceptos. Por ejemplo, podemos seleccionar todos los elementos `<p>` (parrafo) que tengan la clase `rojo` y aplicarle estilos:

```
	p.rojo{
		background: red;
	}
```

Se pueden aplicar estilos a varios elementos a la vez:

```
	h1, h2, h3, h4, #portada-top{
		font-family: "Times New Roman", Times, serif;
	}
```

Para entrar más en detalle sobre como seleccionar elemento, revisad [la guía de Selectores CSS](http://www.w3schools.com/cssref/css_selectors.asp) de w3school.


### ¿Más?

Si sois artistas, magos del color y del detalle al pixel, entiendo que esto os sepa a poco. Sabed que con CSS se hacen autenticas virguerías. *Animaciones, formas, efectos de sobreados, pantallas resposivas al cambio de tamaño del dispositivo o navegador, ...* y un sin fin de cosas más. 

En los [tutoriales](http://www.w3schools.com/css/default.asp) de CSS de w3school encontraréis una gran guía con la que entender, solo con ver el índice, lo mucho que se puede hacer. 

Si por el contrario no encuentras una idea única que plasmar, ¡no te preocupes! Hay un sin fin de librerías CSS de terceros que utilizaremos para tener en pantalla elementos bonitos, estandard, aceptados por el usuario a simple vista y configurables. * Botones, acordeones animados, animaciones, ...* 