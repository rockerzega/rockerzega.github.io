# Usuarios

En este apartado gestionamos el acceso otrogando un el token a los usuarios (empresas, aplicativos), ademas maneja la autentificación del middleware.

## Login

Esta peticion `POST` se la realiza a `localhost/usuarios`

## cuerpo de la petición

El `body` requiere el siguiente objeto para ejecutar satisfactoriamente la petición:

* `business` - El ID de la empresa o cliente.
* `password` - Contraseña de la empresa.
* `proyecto` - Nombre del proyecto que viene el cliente.

| Campo | Nombre | Tipo | Oblig. | Descripción |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| bussines | empresa | string | si | es el Id de la empresa o cliente |
| password | contraseña | string | si | contraseña de la empresa o cliente |
| proyecto | proyecto | string | no | nombre del proyecto del que proviene el cliente, si se omite el mensaje se digundira por todos los proyectos |

## Ejemplo de la petición

```json
{
  "business": "63f601b4384de2b4414d6a70",
  "password": "1234",
  "proyecto": "continuidad"
}
```

## Ejemplo de la respuesta

```json
"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJidXNpbmVzcyI6IjYzZjYwMWI0Mzg0ZGUyYjQ0MTRkNmE3MCIsImRhdGUiOiIyMDIyLTA3LTA2VDIzOjQxOjQ2Ljk2NVoiLCJleHBpcmF0aW9uIjoiMjAyNC0wNy0wNlQyMzo0MTo0Ni45NjJaIn0.hYE1xi-W7KtdAFOepZRaF5TLBk2_nOH11TIk2ba99L0"
```

## getAuth

Esta petición permite verificar la fecha de generación del token y su caducidad.

Esta peticion `GET` se la realiza a `localhost/usuarios`

## Ejemplo de la respuesta

```json
{
	"business": "63f601b4384de2b4414d6a70",
	"creacion": "2022-07-06T23:41:46.965Z",
	"expiracion": "2024-07-06T23:41:46.962Z"
}
```