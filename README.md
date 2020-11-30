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