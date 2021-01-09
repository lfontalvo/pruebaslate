<!-- TITULO DE LA ENTRADA -->
# Desmaterializacion de documentos
<!-- DESCRIPCION DE LA API -->
<aside class="notice">
Metodos y servicios para la desmaterializacion de documentos con EPIK en D1 y D2. 
</aside>
El proceso de desmaterializacion consiste de los siguientes servicios y metodos:

<!-- METODO  -->
## /DESMATERIALIZAR
<!-- url de la API con su metodo -->
> `POST api/v1/:company/epik/desmaterializar`

<!-- colocamos la peticion en el cada lenguaje , ayudar se con la opcion de postman -->

```ruby
require "uri"
require "net/http"

url = URI("https://#{api_id}.execute-api.us-east-1.amazonaws.com/api/v1/JA/epik/desmaterializar")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Content-Type"] = "application/json"
request.body = "{\r\n    \"EstudioCredito\": \"\",\r\n    \"Agencia\": \"\",\r\n    \"Clientes\": [\r\n        {\r\n            \"TipoDocumento\": \"\",\r\n            \"Documento\": \"\",\r\n            \"NombreCliente\": \"\",\r\n            \"ApellidoCliente\": \"\",\r\n            \"CiudadDocumento\": \"\",\r\n            \"DepartamentoDocumento\": \"\",\r\n            \"Correo\": \"\",\r\n            \"Telefono\": \"\",\r\n            \"IndicadorCodeudor\": \"\"\r\n        }\r\n    ],\r\n    \"Ciudad\": \"\",\r\n    \"Direccion\": \"\",\r\n    \"Barrio\": \"\",\r\n    \"Dias\": \"\",\r\n    \"Mes\": \"\",\r\n    \"Anno\": \"\",\r\n    \"Productos\": [\r\n        {\r\n            \"CodigoProducto\": \"\",\r\n            \"NombreProducto\": \"\",\r\n            \"AnnosGarantia\": \"\",\r\n            \"Cantidad\": \"\"\r\n        }\r\n    ],\r\n    \"CodigoOtp\": \"\",\r\n    \"NumCuotas\": \"\",\r\n    \"ValorCuotas\": \"\",\r\n    \"CupoOtorgado\": \"\",\r\n    \"Pais\": \"\",\r\n    \"TasaInteres\": \"\",\r\n    \"EsquemaDeFinanciacion\": [\r\n        {\r\n            \"NumCuotas\": \"\",\r\n            \"ValorCuotas\": \"\"\r\n        },\r\n        {\r\n            \"NumCuotas\": \"\",\r\n            \"ValorCuotas\": \"\"\r\n        }\r\n    ],\r\n    \"c_agr\": \"\",\r\n    \"c_est\": \"\",\r\n    \"usuario\": \"\",\r\n    \"CamposCrediJamar\": [\r\n        {\r\n            \"Agencia\": \"\",\r\n            \"Vendedor\": \"\",\r\n            \"Fecha\": \"\",\r\n            \"NoOP\": \"\",\r\n            \"Numeroconsecutivo\": \"\"\r\n        }\r\n    ],\r\n    \"documentos\": [\r\n        1,\r\n        2,\r\n        3,\r\n        4\r\n    ]\r\n}"

response = https.request(request)
puts response.read_body


```
```javascript
var myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");

var raw = JSON.stringify({"EstudioCredito":"","Agencia":"","Clientes":[{"TipoDocumento":"","Documento":"","NombreCliente":"","ApellidoCliente":"","CiudadDocumento":"","DepartamentoDocumento":"","Correo":"","Telefono":"","IndicadorCodeudor":""}],"Ciudad":"","Direccion":"","Barrio":"","Dias":"","Mes":"","Anno":"","Productos":[{"CodigoProducto":"","NombreProducto":"","AnnosGarantia":"","Cantidad":""}],"CodigoOtp":"","NumCuotas":"","ValorCuotas":"","CupoOtorgado":"","Pais":"","TasaInteres":"","EsquemaDeFinanciacion":[{"NumCuotas":"","ValorCuotas":""},{"NumCuotas":"","ValorCuotas":""}],"c_agr":"","c_est":"","usuario":"","CamposCrediJamar":[{"Agencia":"","Vendedor":"","Fecha":"","NoOP":"","Numeroconsecutivo":""}],"documentos":[1,2,3,4]});

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://#{api_id}.execute-api.us-east-1.amazonaws.com/api/v1/JA/epik/desmaterializar", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```
<!-- Respuesta de la api -->

> Respuesta Exitosa

```json
{
    "num": :id
}
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