<!-- Headings -->

# Title h1
## My title h2
### My title h3
#### My title h4
##### My title h5
###### My title h6

<!-- decoraciones de texto -->

this is an *italic* text

this is an **strong** text

esto es un ~~texto~~ tachado

<!-- <ul> Se puede escrib¡ir html o con asteriscos -->
<ul>
<li>Item 1</li>
</ul>

* otro item
  * otro item dentro

1. Apple
  
2. Orange
<ol>
<li>Apple</li>
  <ol>
    <li>Apple 2</li>
  </ol>
<li>Orange</li>
</ol>


<!-- Enlaces -->
<a href="https://google.es">Google</a>

[Google](https://google.es "Custom title")


<!-- Citas -->
> this is a quote

<!-- Lineas -->
---
___

<!-- Código -->
`console.log('Hello world')`

```javascript
bloque de código
const fruit = {
  nombre: "Manzana"
}
```

```html
<h1>Hello world</h1>
```

<!-- Tablas -->
| Tables  | Are         | Cool  |
| -       | :-:         |    -: |
| col 3   | right       | $445  |
| col 3   | centered    | $445  |
| col 3   | right       | $445  |

<!-- Imágenes -->

<img src="https://user-images.githubusercontent.com/674621/71187801-14e60a80-2280-11ea-94c9-e56576f76baf.png" width="200" />

<!-- GITHUB markdown -->

  <!-- Todo list -->

* [x] Tarea 1
* [ ] Tarea 2

<!-- Nombrer usuarios -->
@Izquiano

<!-- Lista de emojis -->
:smiley:
:+1:



# VS code

## Método abrebiado de teclado "rafcp"
Crea este código con el nombre del componente como el nombre del archivo

```javascript
import React from 'react'
import PropTypes from 'prop-types'

const CounterApp = props => {
  return (
    <div>
      
    </div>
  )
}

CounterApp.propTypes = {

}

export default CounterApp

```



# Cerrar proceso en un puerto

```shell
$ lsof -i tcp:3000
$ kill -9 PID
```


# MongoDB
## importar datos
### Desde CSV

```shell
// método abreviado sin password ni host concreto


$ mongoimport --type csv -d nombreDeLaBaseDeDatos -c nombreDeLaColeción --headerline --drop dump/nombreDelArchivo.csv

$ mongoimport --db baseDatos --collection coleccion --type csv --host direccion_o_ip --port 23456 --username usuario --password contraseña --file ficheroImportar.csv
```

### Desde JSON

// to import this data-set to the database named "test" and collection named "zips"
```shell
$ mongoimport --db test --collection "zips" --drop --type json --host "localhost:47019"  --file "c:\Users\yc03ak1\Desktop\zips.json"
```

### Setear la carpeta donde mongo guarda los datos
* The databases are stored in the /usr/local/var/mongodb/ directory
* The mongod.conf file is here: /usr/local/etc/mongod.conf
* The mongo logs can be found at /usr/local/var/log/mongodb/
* The mongo binaries are here: /usr/local/Cellar/mongodb/[version]/bin
```shell
$ mongod --dbpath /usr/local/var/mongodb
```


# Git
```shell
$ git init
$ git add .
$ git status -s 
$ git commit -m "Mensaje"
$ git push -u origin master
$ git pull
$ git clone https://github.com/Izquiano/nombre-repo.git
$ git config --global user.email "your@email.com"
$ git config --global user.name "Your Name"
$ git log  // muestra todos los commits
$ git checkout -- index.html  // descarta los cambios en un archivo no añadido
$ git diff index.html  // muestra las diferencias entre versiones
$ git branch  // muestra las ramas que tenemos
$ git branch login  // crea una nueva rama 'login'
$ git checkout login // nos pasamos a la rama login
$ git remote add origin https://github.com/Izquiano/nombre-repo.git  // setea el repositorio de git donde se guardan los cambios
```


# Docker
## Crear un contenedor para Node
Creamos un archivo con el nombre
> Dockerfile

sin extensión. y añadimos estas lineas 
```docker
FROM node:12

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

CMD ["npm","start"]
```

en el package.json creamos un script 
```json
"start": "node src/index.js"
```
y en la consola escribimos
```shell
$ docker build -t node-restapi . 
```
Creará la imagen y listamos los contenedores cn el comando:
```shell
$ docker images
```

para ejecutar la imagen escribimos:
>Nota que -it es para que sea interactivo y -p es para que el puerto interno del contenedor sea el 3000 (lo definimos en el index.js) y 4000 el exterior para acceder desde el navegador
```shell
docker run -it -p 4000:3000 node-restapi
````
Ahora podemos acceder a la aplicación a traves de 

> http://localhost:4000/

Para acceder a la imagen y que no sea interactivo 
```shell
$ docker run -p 4000:3000 node-restapi
```

Listar procesos de Docker
```shell
$ docker ps
```

Parar procesos
```shell
$ docker stop idContenedor
```
Ver histórico de procesos
```shell
$ docker ps -a
````

# Webpack

Se inicializa un proyecto de NodeJs
```shell
$ npm init -y
````
instalamos el paquete de webpack y webpack-cli
```shell
npm i webpack
npm i webpack-cli
npm i webpack-dev-server -dev

````
instalamos los plugins necesarios
```shell
npm i html-webpack-plugin
npm i style-loader css-loader
npm i sass-loader node -sass
````



En la raiz del proyecto creamos un archivo <b>webpack.config.js</b>
```javascript
// los css se importan en el app.js

const HtmlWebPackPlugin = require('html-webpack-plugin')

module.exports = {
  entry: './src/app.js',
  output: {
    path: __dirname + 'build',
    filename: 'bundle.js',
  },
  devServer: {
    port: 5000
  },
  module: {
    rules: [
      {
        test: /\.scss$/,
        use: [
          { loader: 'style-loader' },
          { loader: 'css-loader' },
          { loader: 'sass-loader' }
        ]
      }
      

    ]
  },
  plugins: [
    new HtmlWebPackPlugin({
      template: './src/index.html'
    })
  ]
}
```
En la consola
```shell
npx webpack-dev-server
```

