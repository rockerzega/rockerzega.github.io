# Notificaciones

Permite gestionar las notificaciones, ademas del manejo que estas requieren para que se acomplen a las necesidades de los aplicativos.

## crearNotificaciones

Permite obtener todas las notificaciones de una empresa o cliente especifico

Esta petición `POST` se la realiza a `localhost/notificaciones`

## cuerpo de la petición

El `body` requiere el siguiente objeto para ejecutar satisfactoriamente la petición:

* `business` - El ID de la empresa o cliente.
* `proyecto` - Nombre del proyecto que viene el cliente.
* `tipo` - Tipo de notificacion.
* `args` - opciones adiciones que requieran cada proyecto para manejo de notificaciones.
* `revisado` - Determina si la notificacion ya ha sido revisada o no.

| Campo | Nombre | Tipo | Oblig. | Descripción |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| bussines | empresa | string | si | es el Id de la empresa o cliente |
| proyecto | proyecto | string | si | nombre del proyecto del que proviene la empresa o cliente, si se omite, la notificacion se enviara a todos los proyectos a los que esta suscrito |
| tipo | tipo | string | si | tipo de mensaje, si es general, de systema, facturas, etc, para gestionar sus comportamientos |
| args | argumentos | object | si | aqui se nombran las opciones que va a requerir la notificacion segun proyecto al que este suscrito |
| revisado | revisado | boolean | no | determina si el mensaje ya fue revisado por defecto se crea en falso |

## Ejemplo de la petición

```json
{
	"proyecto": "continuidad",
	"tipo": "mensaje",
	"args": {
		"codigo": "0001",
		"titulo": "notificacion general"
	}
}
```

## Ejemplo de la respuesta

```json
{
	"business": "63f601b4384de2b4414d6a70",
	"proyecto": "continuidad",
	"tipo": "mensaje",
	"args": "{\"codigo\":\"0001\",\"titulo\":\"notificacion general\"}",
	"revisado": false,
	"_id": "62c817ee1c103b020d996c69",
	"createdAt": "2022-07-08T11:41:34.423Z",
	"updatedAt": "2022-07-08T11:41:34.423Z",
	"__v": 0
}
```

## leerNotificacion

Permite marcar como leida una notificacion

Esta petición `PUT` se la realiza a `localhost/notificaciones/:id`

Luego de ejecutarse la petición nos retornara el objeto con el parametro revisado en true

## Ejemplo de la respuesta

```json
{
	"_id": "62c817ee1c103b020d996c69",
	"business": "63f601b4384de2b4414d6a70",
	"proyecto": "continuidad",
	"tipo": "mensaje",
	"args": {
		"codigo": "0001",
		"titulo": "notificacion general"
	},
	"revisado": true,
	"createdAt": "2022-07-08T11:41:34.423Z",
	"updatedAt": "2022-07-08T11:41:34.423Z",
	"__v": 0
}
```

## getOneNotificacion

Permite obtener una notificacion en concreto

Esta petición `GET` se la realiza a `localhost/notificaciones/:id`

Luego de ejecutarse la petición nos retornara el objeto con el parametro revisado en true

## Ejemplo de la respuesta

```json
{
	"_id": "62c817ee1c103b020d996c69",
	"business": "63f601b4384de2b4414d6a70",
	"proyecto": "continuidad",
	"tipo": "mensaje",
	"args": {
		"codigo": "0001",
		"titulo": "notificacion general"
	},
	"revisado": true,
	"createdAt": "2022-07-08T11:41:34.423Z",
	"updatedAt": "2022-07-08T11:58:01.005Z",
	"__v": 0
}
```
