## Intro al HTML

En este capitulo veremos a muy bajo nivel las opciones que nos ofrece el HTML, con el que definiremos la estructura básica de una página Web.

### ¿Que pasa cuando accedemos a una URL?

El Browser, al acceder a una URL, realiza una petición a un servidor. De entre otras muchas cosas que pueden pasar, la más común es recibir un archivo HTML que nuestro Browser interpretará.

La estructura más básica que podemos encontrar en un archivo HTML es la siguiente:

```	
	<!DOCTYPE html>
	<html>
		<head>
			<title>Page Title</title>
		</head>
		<body>
			
		</body>
	</html>
```

El HTML se compone con tags (<> </>), con apertura y cierre, anidados. Con este lenguaje de ['markup'](https://es.wikipedia.org/wiki/Lenguaje_de_marcado) damos estructura al contenido que vamos a representar. 


### HTML Tags

Cada tag disponible en HTML nos ofrece una serie de propiedades, adjuntas al elemento que se crea. Ya que solo vamos a raspar la superficie del desarrollo front, os dejo el links a:

- [Tutoriales HTML de w3school.com](http://www.w3schools.com/html/)

	Con ver por encima los tutoriales desde 'HTML Introduction' hasta 'HTML Layouts', va que chuta. Son muy utiles, de páginas cortas (lectura fácil de seccionar), tiene ejemplos ... 

- [Referencia de tags HTML de w3school.com](http://www.w3schools.com/tags/default.asp)

	No dejéis que os abrume. Es solo para que os hagáis una idea de la cantidad de cosas que ofrece el HTML.


El primer tag que vemos en el ejemplo, `<!DOCTYPE html>`, le dice al browser que vamos a utilizar HTML5.

A cotinuación abrimos nuestra página HTML con tags `<html></html>`. Dentro siempre tendremos un `<head></head>` y un `<body></body>`. Dentro del *head* incluiremos metadatos y enlaces a dependecias que tengamos para que se precargen o inicien una carga asíncrona. En el *body* tendremos la estructura que será representada.

Como hemos dicho, cada elemento que creamos tiene una serie de propiedades. Podemos acceder a muchas de ellas a través del tag. A estas propiedades se les llama 'atributos'. Estos atributos dan a cada elemento un contexto y un 'significado'. 

Existen atributos globales, globales de evento y específicos del tag utilizado:

- [Globales](http://www.w3schools.com/tags/ref_standardattributes.asp)
- [Globales de Evento](http://www.w3schools.com/tags/ref_eventattributes.asp)

Lo atributos globales se pueden utilizar sobre CUALQUIER tag que metamos en nuestra estructura. Os resultará muy común ver todo tipo de tags con `id="......"`, `name="........"`, `alt="........."`, `class="......."` o `onclick="......."`.

Si tuviese que listar las 5 tags y los 5 atributos que más utilizo serían:

* Tags
	* div
	* p
	* ul y li (para listas)
	* input (a menudo con form)
	* button
* Atributos
	* id
	* onclick
	* class
	* ... y luego algunos específicos de tags: href, value, ...

HTML ofrece una gran variedad de elementos con los que representamos: video, audio, imagenes, formularios, botones, bloques, ...

Podéis ver ejemplos de tags básicos si abrís el archivo [02-a-basicTags.html](/01-HTML/02-a-basicTags.html) con el chrome. 

\* Nota: Buscad el javascript ;)

Aprovechando el ejemplo, he copiado y pegado el código en [02-b-basicTagsWithBootstrap.html](/01-HTML/02-b-basicTagsWithBootstrap.html). El único cambio realizado ha sido incluir un tag `<link ...>` con el que pediremos al browser que descarga y ponga a disposición de la página una librería CSS. En este caso [Bootstrap](http://getbootstrap.com/getting-started/). 

Ahora no, pero ya miraremos en mayor detenimiento el CSS y las librerías en las que podéis apoyaros para hacer del desarrollo una labor más agradable a la vista de todos en mucho menos tiempo. Por ahora basta con que veáis como se pueden importar archivos desde CDNs (pueden ser CSS o JavaScript). En este caso, la librería CSS aplica algún que otro retoque a las cabeceras, la letra y, si os fijáis, aplica margenes laterales al div con id="bloque-1". Esto es algo que hace bootstrap al reconocer un elemento con clase 'container'. 
