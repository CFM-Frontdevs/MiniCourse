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

// TODO

### Selección de elementos HTML

// TODO

### Tags HTML - Atributos globales de evento

// TODO

### Ejemplo sencillo de formulario 'Login'

// TODO