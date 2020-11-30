# VS code

## Método abrebiado de teclado "rafcp"
Crea este código con el nombre del componente como el nombre del archivo

```
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
# VS code
```
$ lsof -i tcp:3000
$ kill -9 PID
```


# MongoDB
## importar datos
### Desde CSV

```
// método abreviado sin password ni host concreto
mongoimport --db baseDatos --collection coleccion --file fichero_a_importar --type csv

mongoimport --db baseDatos --collection coleccion --type csv --host direccion_o_ip --port 23456 --username usuario --password contraseña --file ficheroImportar.csv
```

### Desde JSON

// to import this data-set to the database named "test" and collection named "zips"
mongoimport --db test --collection "zips" --drop --type json --host "localhost:47019"  --file "c:\Users\yc03ak1\Desktop\zips.json"