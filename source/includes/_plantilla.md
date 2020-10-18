<!-- TITULO DE LA ENTRADA -->
# plantilla
<!-- DESCRIPCION DE LA API -->
<aside class="notice">
Esta es la plantilla demo para documentar las API de jamar.
</aside>
para documentar necesitaras **MARKDONW** [aqui] (https://www.markdownguide.org/cheat-sheet/) una guia.

<!-- METODO  -->
## TITULO
<!-- url de la API con su metodo -->
> `GET http://example.com/api/kittens`

<!-- colocamos la peticion en el cada lenguaje , ayudar se con la opcion de postman -->

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```
```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```
<!-- Respuesta de la api -->

> Respuesta Exitosa

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```
> Respuesta fallida

```json
[
]
```
<!-- DESCRIPCION DEL METODO -->

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum

<!-- parametros con su descriocion -->

### Parametros

Parametro | Obligatorio | Descripcion
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

### Errores conocidos

The Kittn API uses the following error codes:

Codigo | Significado
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- The kitten requested is hidden for administrators only.
404 | Not Found -- The specified kitten could not be found.
405 | Method Not Allowed -- You tried to access a kitten with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
410 | Gone -- The kitten requested has been removed from our servers.
418 | I'm a teapot.
429 | Too Many Requests -- You're requesting too many kittens! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.