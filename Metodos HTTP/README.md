1.[Introducción](#item1)

2.[GET](#item2)

3.[HEAD](#item3)

4.[POST](#item4)

5.[PATCH](#item5)

6.[PUT](#item6)

7.[DELETE](#item7)

8.[OPTIONS](#item8)

9.[Encabezados HTTP](#item9)

10.[Ejemplos de principales Headers](#item10)

11.[Tipos de mensajes de las peticiones HTTPs ](#item11)



<a name= "item1"></a>
# Introducción

HTTP define un conjunto de métodos de petición para indicar la acción que se desea realizar para un recurso determinado. Aunque estos también pueden ser sustantivos, estos métodos de solicitud a veces son llamados HTTP verbs. Cada uno de ellos implementan una semántica diferente, pero algunas características similares son compartidas por un grupo de ellos: ej. un request method puede ser safe, idempotent, o cacheable.

![](https://libro.cursohtml5desdecero.com/images/client-server.png?token=aGhrYW9zOmNjZWEzYzUwLTdlNWItNGVjOC05MzA0LTkxZDdhMWUxOGZhOA%3D%3D)
<a name= "item2"></a>
#### GET
El método GET  solicita una representación de un recurso específico. Las peticiones que usan el método GET sólo deben recuperar datos.
<a name= "item3"></a>
#### HEAD
El método HEAD pide una respuesta idéntica a la de una petición GET, pero sin el cuerpo de la respuesta.
<a name= "item4"></a>
#### POST
El método POST se utiliza para enviar una entidad a un recurso en específico, causando a menudo un cambio en el estado o efectos secundarios en el servidor.
<a name= "item5"></a>
#### PATCH
El método PATCH  es utilizado para aplicar modificaciones parciales a un recurso.
<a name= "item6"></a>
#### PUT
El modo PUT reemplaza todas las representaciones actuales del recurso de destino con la carga útil de la petición.
<a name= "item7"></a>
#### DELETE
El método DELETE borra un recurso en específico.
<a name= "item8"></a>
#### OPTIONS
El método OPTIONS es utilizado para describir las opciones de comunicación para el recurso de destino.

------------



<a name= "item9"></a>
# Los encabezados HTTP
Permiten al cliente y al servidor pasar información adicional con una solicitud o respuesta HTTP. Un encabezado HTTP consta de su nombre que no distingue entre mayúsculas y minúsculas seguido de dos puntos ( :) y luego su valor. Se ignora el espacio en blanco antes del valor.
Los encabezados propietarios personalizados se han utilizado históricamente con un X-prefijo, pero esta convención quedó obsoleta en junio de 2012 debido a los inconvenientes que causó cuando los campos no estándar se convirtieron en estándar en RFC 6648 ; otros están incluidos en un registro de la IANA , cuyo contenido original se definió en RFC 4229 . IANA también mantiene un registro de nuevos encabezados HTTP propuestos .

Los encabezados se pueden agrupar según sus contextos:
•	Los encabezados generales se aplican tanto a las solicitudes como a las respuestas, pero sin relación con los datos transmitidos en el cuerpo.
•	Los encabezados de solicitud contienen más información sobre el recurso que se va a buscar o sobre el cliente que solicita el recurso.
•	Los encabezados de respuesta contienen información adicional sobre la respuesta, como su ubicación o sobre el servidor que la proporciona.
•	Los encabezados de entidad contienen información sobre el cuerpo del recurso, como la longitud del contenido o el tipo MIME .
<a name= "item10"></a>
### Ejemplos:

#### GET

Cuando escribes una url en la barra de direcciones, tu navegador envía una solicitud HTTP y puede verse como esto:
~~~
GET /tutorials/other/top-20-mysql-best-practices/ HTTP/1.1
Host: net.tutsplus.com
User-Agent: Mozilla/5.0 (Windows; U; Windows NT 6.1; en-US; rv:1.9.1.5) Gecko/20091102 Firefox/3.5.5 (.NET CLR 3.5.30729)
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-us,en;q=0.5
Accept-Encoding: gzip,deflate
Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7
Keep-Alive: 300
Connection: keep-alive
Cookie: PHPSESSID=r2t5uvjq435r4q7ib3vtdjq120
Pragma: no-cache
Cache-Control: no-cache
~~~
La primer línea es la "Línea Solicitud" la cual contiene algo de información básica sobre la solicitud. Y el resto son cabeceras HTTP.
Luego de esa solicitud, el navegador recibe una respuesta HTTP que puede verse como lo siguiente:
~~~
HTTP/1.x 200 OK
Transfer-Encoding: chunked
Date: Sat, 28 Nov 2009 04:36:25 GMT
Server: LiteSpeed
Connection: close
X-Powered-By: W3 Total Cache/0.8
Pragma: public
Expires: Sat, 28 Nov 2009 05:36:25 GMT
Etag: "pub1259380237;gz"
Cache-Control: max-age=3600, public
Content-Type: text/html; charset=UTF-8
Last-Modified: Sat, 28 Nov 2009 03:50:37 GMT
X-Pingback: https://net.tutsplus.com/xmlrpc.php
Content-Encoding: gzip
Vary: Accept-Encoding, Cookie, User-Agent
 ~~~
 ~~~
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Top 20+ MySQL Best Practices - Nettuts+</title>
<!-- ... rest of the html ... -->
~~~

La primer línea es la "Línea de Estado", seguida por "Cabeceras HTTP", hasta la línea blanca. Luego de eso, el "contenido" comienza (en este caso, una salida HTML).


------------

#### HEAD

El método HEAD es muy similar al GET (funcionalmente hablando), a excepción de que el servidor responde con líneas y headers, pero no con el body de la respuesta.
~~~
GET /index.html HTTP/1.1  
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Accept-Encoding: gzip, deflate
Connection: Keep-Alive
~~~

A lo que el servidor nos respondería algo como:

~~~
HTTP/1.1 200 OK
Date: Mon, 27 Jul 2009 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT
ETag: "34aa387-d-1568eb00"
Vary: Authorization,Accept
Accept-Ranges: bytes
Content-Length: 88
Content-Type: text/html
Connection: Closed
~~~

------------





#### POST

Las solicitudes POST son más comúnmente enviadas por formularios web. 
~~~
<form method="POST" action="foo.php">
 
First Name: <input type="text" name="first_name" /> <br />
Last Name: <input type="text" name="last_name" /> <br />
 
<input type="submit" name="action" value="Submit" />
 
</form>
~~~
Al enviar ese formulario se crea una solicitud HTTP como esta:
~~~
POST /foo.php HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows; U; Windows NT 6.1; en-US; rv:1.9.1.5) Gecko/20091102 Firefox/3.5.5 (.NET CLR 3.5.30729)
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-us,en;q=0.5
Accept-Encoding: gzip,deflate
Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7
Keep-Alive: 300
Connection: keep-alive
Referer: http://localhost/test.php
Content-Type: application/x-www-form-urlencoded
Content-Length: 43
 
first_name=John&last_name=Doe&action=Submit
~~~

Hay 3 cosas importantes a notar aquí:

•	La ruta en la primera línea es simplemente /foo.php y ya no hay una cadena de consulta.
•	Las cabeceras Content-Type y Content-Length han sido agregadas, las cuales proveen información sobre los datos que están siendo enviados.
•	Todos los datos son ahora enviados luego de las cabeceras, con el mismo formato que la cadena de consulta.
•	Solicitudes de método POST pueden también hacerse vía AJAX, aplicaciones, cURL, etc. Y todos los formularios para subir archivos requieren que usen el método POST.

------------




#### PATCH
Petición
~~~
PATCH /file.txt HTTP/1.1 
Host: www.example.com
Content-Type: application/example
If-Match: "e0023aa4e"
Content-Length: 100
[description of changes]
~~~
Respuesta

Una respuesta exitosa es indicada con un código de respuesta 204, porque la respuesta no tiene mensaje en el body. (el cual tendría una respuesta con el código 200). Tenga en cuenta que también se pueden utilizar otros códigos.
~~~
HTTP/1.1 204 No Content
Content-Location: /file.txt
ETag: "e0023aa4f"

~~~

------------


#### PUT 

El método PUT es usado para solicitar que el servidor almacene el cuerpo de la entidad en una ubicación específica dada por el URL.
Se solicita al servidor que guarde el cuerpo de la entidad dada en index.htm en la raíz del servidor:

~~~
PUT /index.htm HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Connection: Keep-Alive
Content-type: text/html
Content-Length: 182

<html>
<body>
<h1>Howdy, Michelle!</h1>
</body>
</html>
~~~
Y el servidor por su parte, responde con lo siguiente al cliente (habiendo ya guardado el cuerpo de la entidad en el archivo index.htm):

~~~
HTTP/1.1 201 Created
Date: Mon, 27 Nov 2017 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Content-type: text/html
Content-length: 30
Connection: Closed

~~~

------------


#### DELETE 
Este método es utilizado para solicitar al servidor que elimine un archivo en una ubicación específica dada por la URL. En otras palabras más simples, este método elimina un recurso determinado.
Se le solicitará al servidor eliminar el archivo hello.htm en la ruta raíz del servidor:
~~~
DELETE /hello.htm HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Connection: Keep-Alive
~~~

El servidor por su parte responderá eliminando dicho archivo y respondiendo al cliente lo siguiente:
~~~
HTTP/1.1 200 OK
Date: Mon, 27 Jul 2009 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Content-type: text/html
Content-length: 30
Connection: Closed
 
<html>
<body>
<h1>URL deleted.</h1>
</body>
~~~

------------


#### OPTION
Se necesita saber cuáles métodos de solicitud soporta el servidor de nuestra profesora, podemos utilizar curl y una solicitud OPTIONS:
~~~
curl -X OPTIONS https://yosoy.dev -i
Para lo cual el servidor podría contestar algo como lo siguiente:
HTTP/1.1 200 OK
Date: Wed, 8 Nov 2017 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Allow: GET,HEAD,POST,OPTIONS,TRACE
Content-Type: httpd/unix-directory

~~~

------------



<a name= "item11"></a>
# Tipos de mensajes de las peticiones HTTPs 

El primer dígito del código de estado especifica uno de los 5 tipos de respuesta, el mínimo para que un cliente pueda trabajar con HTTP es que reconozca estas 5 clases.
La Internet Assigned Numbers Authority (IANA) mantiene el registro oficial de códigos de estado HTTP.
Indice de contenido

1.	1XX Respuestas informativas
2.	2XX Peticiones correctas
3.	3XX Redirecciones
4.	4XX Errores del cliente
5.	5XX Errores de servidor

- Errores del intervalo 100-199

**100 Continue**.
El servidor ha recibido los headers del request y el cliente debería proceder a enviar el cuerpo de la respuesta.

Tengo un servicio web de un API REST que carga vídeos a un servidor, los vídeos se carga a Cloudinary mediante código de backend. El problema es que después de hacer la petición desde la app cliente, pasados unos segundos se vuelve a recibir la misma petición (cómo si se se hubiera enviado de nuevo desde el mismo cliente).
Ambas peticiones se ejecutan normal (sin problemas), pero después de volver de la petición que ejecuta el SDK de cloudinary para cargar el vídeo de la primera petición, sin importar que haya funcionado o no, no me deja responder al host cliente, y me lanza el error: Error: Can't set headers after they are sent, aunque no se haya respondido nada. Después de unos segundos, el servidor donde está el API responde con una respuesta vacía. Luego de otros segundos, regresa de subir el mismo vídeo de la segunda petición y de nuevo, aunque haya funcionado, no responde correctamente, aunque esta vez ya no me lanza el error anterior.
Las cosas que he intentado es dar más tiempo de vida (TTL) a la petición dandole hasta 1 hora para esperar, pero aún así no funciona.

**101 Switching Protocols.** 
El requester ha solicitado al servidor conmutar protocolos.

I created android app for my mobile and i'm using app from google play as a server I open my hotspot and user can access my wifi with ip and port for example: `192.168.xxx.xxx:8080`
He will see my website. There i'm using websockets to pass data between javascript and android java.
In Firefox and Explorer it works fine, but in Chrome it tells me: "Websocket connection to `'ws://192.168.xxx.xxx:9999/' `failed: Error during websocket handshake: Status line does not end wit CRLF".
I used the code from here: Writing a WebSocket Server (See file below "EDIT").
Also i read [RFC 6455]( https://tools.ietf.org/html/rfc6455) and i do exactly as wrote there.
~~~
This example of the ClientSession:
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.PrintWriter;
import java.net.Socket;

public class ClientSession {

    private Socket socket;

    public ClientSession(Socket socket) {
        System.out.println("new ClientSessionTest()");
        this.socket = socket;
        initClientListener();
    }

    private void initClientListener() {
        System.out.println("initClientListener()");
        Thread t = new Thread(new Runnable() {

            @Override
            public void run() {
                try {
                    BufferedReader socketReader = new BufferedReader(
                            new InputStreamReader(socket.getInputStream()));
                    final PrintWriter socketWriter = new PrintWriter(socket
                            .getOutputStream(), true);
                    String clientKey = null;
                    String responseKey = null;
                    while (true) {
                        String line = socketReader.readLine();
                        if (line == null) {
                            System.out.println("received null from client - closing connection");
                            break;
                        } else if (line.isEmpty()) {
                            System.out.println("empty line");

                            String _01 = "HTTP/1.1 101 Switching Protocols";
                            String _02 = "Upgrade: websocket";
                            String _03 = "Connection: Upgrade";
                            String _04 = "Sec-WebSocket-Accept: " + responseKey;
                            String _05 = "Sec-WebSocket-Protocol: chat";
                            String _06 = "Content-Encoding: identity";

                            System.out.println(_01);
                            System.out.println(_02);
                            System.out.println(_03);
                            System.out.println(_04);
                            System.out.println(_05);
                            System.out.println(_06);
                            System.out.println("");

                            socketWriter.println(_01);
                            socketWriter.println(_02);
                            socketWriter.println(_03);
                            socketWriter.println(_04);
                            socketWriter.println(_05);
                            socketWriter.println(_06);
                            socketWriter.println("");

                            //********************data from client*********************

                            try {
                                byte[] buff = new byte[100];
                                int length = socket.getInputStream().read(buff);

                                byte[] bstr = new byte[length];
                                System.arraycopy(buff, 0, bstr, 0, length);
                                System.out.println(new String(bstr));
                                for (byte b : bstr) {
                                    System.out.print(((int) b) + " ");
                                }
                                System.out.println();
                                System.out.println();
                                String str = new String(decodeFrame(buff),"UTF-8");
                                System.out.println(str);
                            } catch (Exception e) {
                                System.out.println(e.getMessage());

                            //********************************************************

                        }
                        } else if (line.startsWith("Sec-WebSocket-Key:")) {
                            clientKey = line.replace("Sec-WebSocket-Key: ", "");
                            responseKey = ResponseGenerator
                                    .toResponseKey(clientKey);
                        } else {
                            System.out.println("" + line);
                            //socketWriter.println("lala");
                        }

                    }
                } catch (IOException e) {
                    e.printStackTrace();
                }

            }
        });
        t.start();
    }
~~~
 I changed the line String _01 = "HTTP/1.1 101 Switching Protocols"; to String _01 = "HTTP/1.1 101 Switching Protocols\r\n"; and its remove the error (CRLF) i wrote above but the onopen method from the javascript code (below) is not firing and after that also Firefox and Explorer are not working.
Javascript:
~~~
<html>
<head>

<script type="text/javascript" >

var websocket;
var url = "ws://localhost:1234";

function init(){
        try{
                websocket = new MozWebSocket(url, "chat");
        }catch(e){
                websocket = new WebSocket(url, "char");
        }

        websocket.onopen = function(evt) { onOpen(evt) };
        websocket.onclose = function(evt) { onClose(evt) };
        websocket.onmessage = function(evt) { onMessage(evt) };
        websocket.onerror = function(evt) { onError(evt) };
}

var count = 0;
function loop(){
        var message = "lala\n";
        websocket.send(message);
        count++;

        setTimeout(loop, 500);
}

function onOpen(event){  
    alert("Socket has been opened!" + ('5' + 3) + ('5' - 3));  

    loop();
}  

function onMessage(evt){  
    alert(evt);  
}  

function onClose(event){  
    alert("socket closed");  
}

function onError(event){
        alert(event.data);
}

window.addEventListener("load", init, false);


</script>

</head>
<body>



</body>
</html>
~~~



**102 Processing (WebDAV; RFC 2518).**
Usado en requests para reanudar peticiones PUT o POST abortadas.

Problem: Provide progress info over HTTP
I am writing an application where I would like to provide progress information for long(er) running requests. I would like the client to be able to report progress (e.g. percent completed) and a message to the user.
HTTP 1xx responses
My intention is to accomplish this using HTTP 1xx responses before the final HTTP response.
According to RFC2616 section 10.1 on “Informational 1xx” responses any compliant HTTP 1.1 client must be able to “accept one or more 1xx status responses prior to a regular response”.

**100 Continue**
**102 Processing (defined in RFC 2518)**
Using “100 Continue” for this purpose seems to be (at least) a violation of the intention of this status code as it is described in RFC 2616 section 8.2.3.
This leaves us with “102 Processing” which was originally defined for WebDAV but seems perfect for this purpose.

------------



- Errores del intervalo 200-299

**200 OK.**
El request es correcto. Esta es la respuesta estándar para respuestas correctas.

I have implemented an Ajax request on my website, and I am calling the endpoint from a webpage. It always returns 200 OK, but jQuery executes the error event.
I tried a lot of things, but I could not figure out the problem. I am adding my code below:

jQuery Code
~~~
var row = "1";
var json = "{'TwitterId':'" + row + "'}";
$.ajax({
    type: 'POST',
    url: 'Jqueryoperation.aspx?Operation=DeleteRow',
    contentType: 'application/json; charset=utf-8',
    data: json,
    dataType: 'json',
    cache: false,
    success: AjaxSucceeded,
    error: AjaxFailed
});
function AjaxSucceeded(result) {
    alert("hello");
    alert(result.d);
}
function AjaxFailed(result) {
    alert("hello1");
    alert(result.status + ' ' + result.statusText);
}

C# code for JqueryOpeartion.aspx
protected void Page_Load(object sender, EventArgs e) {
    test();
}
private void test() {
    Response.Write("<script language='javascript'>alert('Record Deleted');</script>");
}
~~~

I need the ("Record deleted") string after successful deletion. I am able to delete the content, but I am not getting this message. Is this correct or am I doing anything wrong? What is the correct way to solve this issue?


**201 Created.**
El request se ha completado y se ha creado un nuevo recurso.

We have created scripted rest API with post method which creates records in the table . On triggering API from postman ,it returns 200 ok and not 201 created .How do we get 201 Created and not 200Ok.

**202 Aceptada.**
El request se ha aceptado para procesarlo, pero el proceso aún no ha terminado.

**203 Non-Authoritative Information.**
El request se ha procesado correctamente, pero devuelve información que podría venir de otra fuente.

While calling a REST API for Azure DevOps I am getting an error 203 Non-Authoritative Information. Actually I want to trigger a release pipeline line with the help of REST API.

**204 No Content**.
El request se ha procesado correctamente, pero no devuelve ningún contenido.

For a PUT request: HTTP 200 or HTTP 204 should imply "resource updated successfully".
For a DELETE request: HTTP 200 or HTTP 204 should imply "resource deleted successfully". HTTP 202 can also be returned which would imply that the instruction was accepted by the server and the "resource was marked for deletion".

PUT
If an existing resource is modified, either the 200 (OK) or 204 (No Content) response codes SHOULD be sent to indicate successful completion of the request.

DELETE
A successful response SHOULD be 200 (OK) if the response includes an entity describing the status, 202 (Accepted) if the action has not yet been enacted, or 204 (No Content) if the action has been enacted but the response does not include an entity.

------------



- Errores del intervalo 300-399

**300 Multiple Choices.**
Es una lista de enlaces. El usuario puede seleccionar un enlace e ir a esa dirección. Hay un máximo de cinco direcciones.

I've got a problem with my website, or more specfically the navigation.
First off the problem;

300 multiple pages; It does this to the url
   http://mysite.co.uk/services.phpdiamond-plus.php
   http://mysite.co.uk/services.phpdiamond/
  
should be;
   http://mysite.co.uk/services/diamond-plus.php
   http://mysite.co.uk/services/diamond.php
   
my file structure;
~~~
root/services/diamond-plus.php
root/services/diamond.php
~~~
Doesn't matter what direcory or level I am in when selecting diamond-plus.php, it just brings up this page with the url as it is above, I've got a similar url which happens to the both of them.
I include my navigation and use relative urls like so;

`/services/diamond-plus.php`

Orignally there was a services.php page in directory above, I've changed that. I didsabled my .htaccess file aswell to test, the problem still persists.

**301 Moved Permanently**. 
La página solicitada se ha movido permanentemente a una nueva URI.

**302 Found.** 
La página solicitada se ha movido temporalmente a una nueva URI.

cURL give me this page :
302 Found
The document has been temporarily moved to here.
for some websites, but in browser that site load perfect. how can i fix it?

**303 See Other.**
La página solicitada se puede encontrar en una URI diferente.

I'm using httplib to make a post to a server. I'm getting back a 303 See Other. How do I see what the redirect message is '303 See Other' does not really help.
Thanks

~~~
conn1 = httplib.HTTPSConnection(url, 443, timeout=30)
            headers = {"Content-type": "application/text",
                   "Accept": "2"}

conn1.set_debuglevel(1)
conn1.request("POST", '', body.encode('utf8'), headers)
response = conn1.getresponse()
print response.status, response.reason
~~~

**304 Not Modified**.
Indica que la página solicitada no se ha modificado desde la última petición.

How are "304 Not Modified" responses generated?
How does a browser determine whether the response to an HTTP request is 304?
Is it set by the browser or sent from the server?
If sent by the server, how does the server know the data available in cache, also how does it set 304 to an image?
My guess, if it's generated by the browser:
~~~
function is_modified()
{
    return get_data_from_cache() === get_data_from_url();
}

function get_data_from_cache()
{
    return some_hash_or_xxx_function(cache_data);
}

function get_data_from_url()
{
     return some_hash_or_xxx_function(new_data);
}

function some_hash_or_xxx_function(data)
{
     // Do something with the data.
     // What is that algorithm?
     return result;
}

console.log(is_modified());
~~~

I am relying on a third party API provider to get data, parse & push it to my database. The data may or may not change during every request, but the header always sends 200. I do not want to parse, check the last Unique ID in DB and so on... to determine the change in data, nor compare the result directly rather I md5(), sha1() and crc32() hashed the result and works fine, but I'm wondering about the algorithm to determine 304.
I want to use the same kind of algorithm to determine the change in my data.

------------


- Errores del intervalo 400-499

**Error 401 (Unauthorized).**
Informa que el recurso solicitado necesita autenticación.La cabecera de la respuesta es del tipo www-Authenticate para que se pueda iniciar el proceso.

 want get picture of internet and insert into word .
I use this code .
~~~
MainDocumentPart mainPart = wordprocessingDocument.MainDocumentPart;
System.Net.WebRequest request = 
    System.Net.HttpWebRequest.Create("http://spsdev2:1009");

System.Net.WebResponse response = request.GetResponse();
ImagePart imagePart = mainPart.AddImagePart(ImagePartType.Jpeg);
//Send an HTTP request and get the image at the URL as an HTTP response
HttpWebRequest myReq = (HttpWebRequest)WebRequest.Create(fileName);
WebResponse myResp = myReq.GetResponse();

//Get a stream from the webresponse
Stream stream = myResp.GetResponseStream();
I get error in myReq.GetResponse();
~~~
Error :The remote server returned an error: (401) Unauthorized.

**Error 403 (Forbidden).**
Indica que el servidor no puede responder con el recurso solicitado porque se ha denegado el acceso, aunque el navegador haya realizado la petición correctamente. Está entre uno de los errores más comunes.

For a web page that exists, but for which a user does not have sufficient privileges (they are not logged in or do not belong to the proper user group), what is the proper HTTP response to serve?
401 Unauthorized?
403 Forbidden?
Something else?
What I've read on each so far isn't very clear on the difference between the two. What use cases are appropriate for each response?


**Error 404 (Not Found).**
Se puede clasificar como el error más común de todos, e informa que el servidor no puede encontrar el recurso y no puede especificar si esta ausencia será de manera permanente o temporal.

I just transfered my magento installation from one local machine server to another. Now, I cannot login to admin panel. When I go to the admin login url, I get the following error message:-
"Error: 404 Not Found"
Some of my module's pages also show this error.
Can anyone please figure out the problem?


**Error 405 (Method Not Allowed).** 
Indica que el servidor no puede obtener el recurso porque el método que está utilizando el navegador para acceder al archivo no está permitido.

I am getting
Error 405: Method not allowed
~~~
MessageEnd.java:
package com.example.wordcount;

import javax.ws.rs.Consumes;
import javax.ws.rs.GET;
import javax.ws.rs.PUT;
import javax.ws.rs.Path;
import javax.ws.rs.PathParam;
import javax.ws.rs.Produces;
import javax.ws.rs.core.MediaType;
import javax.ws.rs.core.Response;

@Path("/jersey")
public class MessageEnd {

    @GET
    @Path("/getvalue/{word}")
    @Produces(MediaType.TEXT_PLAIN)
    public Response sayHello(@PathParam("word") String word){

        String output = " Count of word " + word;
        return Response.status(200).entity(output).build();
    }

    @PUT
    @Path("/sendvalue/{msg}")
    @Consumes(MediaType.TEXT_PLAIN)
    @Produces(MediaType.TEXT_PLAIN)
    public Response sendMsg(@PathParam("msg") String msg){

        String output = "Received message= " + msg;
        return Response.status(200).entity(output).build();
    }

}
~~~
FYI, GET is working fine.






**Error 406 (Not Acceptable).**
Informa que el archivo solicitado existe pero no se puede utilizar porque tiene un formato que no es aceptable por el navegador.

In my Ruby on Rails application I tried to upload an image through the POSTMAN REST client in Base64 format. When I POST the image I am getting a 406 Not Acceptable Response. When I checked my database, the image was there and was successfully saved.
What is the reason for this error, is there anything I need to specify in my header?
My request:
URL ---` http://localhost:3000/exercises.json`
Header:
~~~
Content-Type  -  application/json
Raw data:
{
    "exercise": {
        "subbodypart_ids": [
            "1",
            "2"
        ],
        "name": "Exercise14"
    },
    "image_file_name": "Pressurebar Above.jpg",
    "image":"******base64 Format*******"
}
~~~

**Error 408 (Request Timeout).**Aunque el navegador puede realizar nuevas peticiones cuando quiera este código indica que el navegador ha tardado demasiado tiempo en realizar su petición y por ello el servidor ya no espera esa petición.

------------



- Errores en el intervalo 500-599

**Error 506 (Variant Also Negotiates).**
Informa de la detección de un error de configuración interna por parte del servidor al procesar la parte de la negociación del contenido de la petición realizada por el navegador.

**Error 507 (Insufficient Storage (WebDAV)).**
Indíca que no hay suficiente espacio de almacenamiento libre para que el servidor pueda  modificar o crear el recurso solicitado.

I develop small program that looping to send request to a website. For get some information that i need from web page, then store to my database.
It is about 1400 requests.
I run it on both developing machine and Windows Azure VM.
At first, it work well on both machine (first day). But after i run it next day on Windows Azure VM. It's throw exception like this.
~~~
Web Exception: System.Net.WebException: The remote server returned an error: (507) Insufficient Storage. at System.Net.WebClient.OpenRead(Uri address) at System.Net.WebClient.OpenRead(String address) at StockChecker.MainWindow.Worker_DoWork(Object Sender, DoWorkEventArgs e)
~~~
But on developing machine it's no problem.
What happened with it. Is target website detected as bot? How to fix this issue.
Here is my code.
~~~
WebClient client = new WebClient();

List<tbmProduct> prodList = // Get data from my database;

foreach (var prod in prodList)
{
    string content;
    string link = prod.SupplierUrl;

    try
    {
        using (StreamReader reader = new StreamReader(client.OpenRead(link)))
        {
            content = reader.ReadToEnd();

            // Do something. Update my database.
        }
    }
    catch (WebException ex)
    {
        // write log
    }
    catch (Exception ex)
    {
        // write log
    }
}

~~~

**Error 508 (Loop Detected (WebDAV)).**  
Este error aparece cuando se ha encontrado un bucle infinito cuando el servidor intenta procesar la petición. Este código indica que se ha producido un error en toda la operación.

I call an AJAX to check DB if there is new notif every 3 or 10 seconds with the same query from 4 different browsers at the same time. But at some point after loop 100+, the server returns Error 508 (Loop Detected). This is just simple site so I don't think I need VPS server.
I added timestamp in SELECT as query differentiator, put unset, flush, mysqli_free_result, pause, mysqli_kill, mysqli_close, but error still occurs. Entry Processes hit 20/20.

**Error 510 (Not Extended).**
Informa de que es necesario añadir más extensiones a la petición del navegador para que el servidor pueda procesarla.

My server fired every week a 510 HTTP error. After reboot the apache, the problem was solve. But this is more a workaround as a solution for this problem.
Any ideas, how to solve this problem?

**Error 511 (Network Authentication Required).** Este error aparece cuando es necesario que el navegador se autentifique para realizar las peticiones.


