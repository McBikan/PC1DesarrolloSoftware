Pregunta:¿Cuáles son las dos diferencias principales que has visto anteriormente y lo que ves en un navegador web 'normal'? ¿Qué explica estas diferencias?

1.- La imagen no carga como archivo; pues la imagen esta siendo redireccionada de otra fuente

2.- La programación es estática, la palabra aleatoria no cambia.

(base) pcs5@pcs5-HP-EliteDesk-800-G4-SFF:~$ curl 'http://randomword.saasbook.info'

(base) pcs5@pcs5-HP-EliteDesk-800-G4-SFF:~/Documentos/Trabajo1$ curl 'http://randomword.saasbook.info' >Trabajo1.html
  
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 
                                 Dload  Upload   Total   Spent    Left  Speed

100   480  100   480    0     0   1651      0 --:--:-- --:--:-- --:--:--  1655

Pregunta: Suponiendo que estás ejecutando curl desde otro shell ¿qué URL tendrás que pasarle a curl para intentar acceder a tu servidor falso y por qué?

Tendré que pasarle el local host 8081 para que se conecte a ese servidor falso; para que de esa manera acceda a la web mediante un servidor (esto provocará que el archivo html sea dinámico, de esta forma las palabras si cambiaran y la imagen cargará.

Pregunta: La primera línea de la solicitud identifica qué URL desea recuperar el cliente. ¿Por qué no ves http://localhost:8081 en ninguna parte de esa línea?

Porque el servidor falso y el lugar desde donde se ejecuta , estan en el mismo computador (y esto sería redundante).

Pregunta: Según los encabezados del servidor, ¿cuál es el código de respuesta HTTP del servidor que indica el estado de la solicitud del cliente y qué versión del protocolo HTTP utilizó el servidor para responder al cliente?

(base) pcs5@pcs5-HP-EliteDesk-800-G4-SFF:~/Documentos/Trabajo1$ curl -i 'http://randomword.saasbook.info'
HTTP/1.1 200 OK 
Connection: keep-alive
Content-Type: text/html;charset=utf-8
Content-Length: 481
X-Xss-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Frame-Options: SAMEORIGIN
Server: WEBrick/1.4.2 (Ruby/2.6.6/2020-03-31)
Date: Mon, 25 Sep 2023 16:43:28 GMT
Via: 1.1 vegur

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" crossorigin="anonymous">
    <title>Random Word Generator</title>
  <body class="container">
    <div id="image">
      <img src="esaas.png">
    </div>
    <div id="word">
      consist
    </div>
  </body>
</html>

Respueta:
El código que indica la respuesta HTTP del servidor que indica el estado de la solicitud del cliente: HTTP/1.1 200 OK 
Version del protocolo HTTP: 1.1 

Pregunta: Cualquier solicitud web determinada puede devolver una página HTML, una imagen u otros tipos de entidades. ¿Hay algo en los encabezados que crea que le dice al cliente cómo interpretar el resultado?.

TTP/1.1 200 OK 
Connection: keep-alive
Content-Type: text/html;charset=utf-8
Content-Length: 481
X-Xss-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Frame-Options: SAMEORIGIN
Server: WEBrick/1.4.2 (Ruby/2.6.6/2020-03-31)
Date: Mon, 25 Sep 2023 16:43:28 GMT
Via: 1.1 vegur

Respuesta:
Si, le dice que devolvera un archivo texto, con 481 caracteres; que esta hecho en ruby.

Las cookies son seguras mediante el protocolo de seguridad HTTPS:
