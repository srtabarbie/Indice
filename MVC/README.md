1. [Introducción](#item1)
2. [Marco Teórico](#item2)
3. [MVC (Model-View-Controller)](#item3)
4. [Frameworks que utiliza el modelo MVC](#item4)
5. [Apache Struts](#item5)
6. [Ruby on Rails](#item6)
7. [Django](#item7)
8. [Ventajas del patrón MVC](#item8)
9. [Resultados](#item9)
10. [Otros modelos/frameworks de patrones de diseño](#item10)
11. [Patrón Observer](#item11)
12. [Patrón de diseño Adapter](#item12)
13. [Conclusión](#item13)

<a name= "item1"></a>
## Introducción

En este documento se pretende dar a conocer información importante sobre el patrón de diseño MVC, historia, sus principales características, ventajas, y frameworks con los que trabaja y los que son sus competidores haciendo un breve comparativo entre los diferentes patrones de diseño y finalmente llegaremos a la conclusión.

------------

<a name= "item2"></a>
## Marco Teórico

<a name= "item3"></a>
###### MVC (Model-View-Controller)

MVC se usa inicialmente en sistemas donde se requiere el uso de interfaces de usuario, aunque en la práctica el mismo patrón de arquitectura se puede utilizar para distintos tipos de aplicaciones debido a que  MVC no es un concepto nuevo, ya que el patrón fue descrito en el año 1979 por Trygve Reenskaug.
Es una propuesta de arquitectura del software utilizada para separar el código por sus distintas responsabilidades, manteniendo distintas capas o grupos de componentes en los que organiza las aplicaciones bajo este paradigma que se encargan de hacer una tarea muy concreta, lo que ofrece beneficios diversos para mantener una estructura organizada, limpia y con un acoplamiento mínimo entre las distintas capas.


**Modelo** es la encargada de gestionar el almacenamiento y recuperación de datos y entidades del dominio, es decir, incluirá mecanismos de persistencia o será capaz de interactuar con ellos. Dado que habitualmente la persistencia se delega a un motor de bases de datos, es muy frecuente encontrar en el Modelo la implementación de componentes tipo DAL (Data Access Layer, o Capa de Acceso a Datos). 

**Vista** los componentes de la vista son los responsables de generar la interfaz de nuestra aplicación, es decir, de componer las pantallas, páginas, o cualquier tipo de resultado utilizable por el usuario o cliente del sistema. 

**Controlador** realizan tareas de transformación de datos para hacer que los componentes de la Vista y el Modelo se entiendan. Así, traducirán la información enviada desde la interfaz, por ejemplo, los valores de campos de un formulario recibidos mediante el protocolo HTTP, a objetos que puedan ser comprendidos por el Modelo, como pueden las clases o las entidades del dominio.

![](https://miro.medium.com/max/1068/1*stJhKliOuTpX6S2kVuIHNw.png)


------------


<a name= "item4"></a>
###### Frameworks que utiliza el modelo MVC

<a name= "item5"></a>
•	[Apache Struts](https://struts.apache.org/index.html) 

Apache Struts es un marco MVC gratuito y de código abierto para crear aplicaciones web Java elegantes y modernas. Favorece la convención sobre la configuración, es extensible mediante una arquitectura de complementos y se envía con complementos para admitir REST, AJAX y JSON.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/7/78/Struts-logo.svg/1200px-Struts-logo.svg.png)

------------
<a name= "item6"></a>
•	[Ruby on Rails](https://api.rubyonrails.org/)

¿Qué es Rails?
Rails es un marco de aplicación web que incluye todo lo necesario para crear aplicaciones web respaldadas por bases de datos de acuerdo con el patrón Modelo-Vista-Controlador (MVC).
Comprender el patrón MVC es clave para comprender Rails. MVC divide su aplicación en tres capas: Modelo, Vista y Controlador, cada una con una responsabilidad específica.


**Modelo** representa el modelo de dominio  y encapsula la lógica empresarial específica de su aplicación. En Rails, las clases de modelos respaldadas por bases de datos se derivan de ActiveRecord :: Base. Active Record le permite presentar los datos de las filas de la base de datos como objetos y embellecer estos objetos de datos con métodos de lógica empresarial. Aunque la mayoría de los modelos de Rails están respaldados por una base de datos, los modelos también pueden ser clases de Ruby ordinarias o clases de Ruby que implementan un conjunto de interfaces proporcionadas por el módulo Active Model.


**Controlador** es responsable de manejar las solicitudes HTTP entrantes y proporcionar una respuesta adecuada. Por lo general, esto significa devolver HTML, pero los controladores Rails también pueden generar XML, JSON, PDF, vistas específicas para dispositivos móviles y más. Los controladores cargan y manipulan modelos y renderizan plantillas de vista para generar la respuesta HTTP adecuada. En Rails, las solicitudes entrantes son enrutadas por Action Dispatch a un controlador apropiado, y las clases de controlador se derivan de ActionController :: Base. Action Dispatch y Action Controller están empaquetados en Action Pack.

 **Vista** está compuesta por "plantillas" que son responsables de proporcionar representaciones adecuadas de los recursos de su aplicación. Las plantillas pueden venir en una variedad de formatos, pero la mayoría de las plantillas de vista son HTML con código Ruby incrustado (archivos ERB). Las vistas se representan normalmente para generar una respuesta de controlador o para generar el cuerpo de un correo electrónico. En Rails, la generación de vistas es manejada por Action View.

**Frameworks y bibliotecas**

Active Record, Active Model, Action Pack y Action View se pueden usar independientemente fuera de Rails. Además de eso, Rails también viene con Action Mailer, una biblioteca para generar y enviar correos electrónicos; Action Mailbox, una biblioteca para recibir correos electrónicos dentro de una aplicación Rails; Trabajo activo, un marco para declarar trabajos y hacer que se ejecuten en una variedad de backends de cola; Action Cable, un marco para integrar WebSockets con una aplicación Rails; Active Storage, una biblioteca para adjuntar archivos locales y en la nube a las aplicaciones Rails; Action Text, una biblioteca para manejar contenido de texto enriquecido; y Active Support, una colección de clases de utilidad y extensiones de biblioteca estándar que son útiles para Rails y que también se pueden usar de forma independiente fuera de Rails.	

1.	Install Rails at the command prompt if you haven't yet:
`$ gem install rails`

2.	At the command prompt, create a new Rails application:
`$ rails new myapp`
where “myapp” is the application name.

3.	Change directory to myapp and start the web server:
~~~
`$ cd myapp`
`$ rails server`
~~~
4.	Run with --help or -h for options.
Go to http://localhost:3000 and you'll see: “Yay! You're on Rails!”

5. Siga las pautas para comenzar a desarrollar su aplicación. Puede encontrar útiles los siguientes recursos:

 1.	The README file creado dentro de su aplicación.
 2.	Getting Started with Rails.
 3.	Ruby on Rails Guides.
 4.	The API Documentation.
 
 ![](https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Ruby_On_Rails_Logo.svg/1280px-Ruby_On_Rails_Logo.svg.png)

------------

<a name= "item7"></a>
•	[Django](https://www.djangoproject.com/)

Django es un marco web Python de alto nivel que fomenta un desarrollo rápido y un diseño limpio y pragmático, esta constituido por las siguientes capaz.

**La capa del modelo** Django proporciona una capa de abstracción (los "modelos") para estructurar y manipular los datos de su aplicación web.

**La capa de vista** Django tiene el concepto de "vistas" para encapsular la lógica responsable de procesar la solicitud de un usuario y devolver la respuesta

**La capa de plantilla** Proporciona una sintaxis fácil de diseñar para representar la información que se presentará al usuario.

**Formularios** Django proporciona un marco rico para facilitar la creación de formularios y la manipulación de datos de formularios.

La seguridad es un tema de suma importancia en el desarrollo de aplicaciones web y Django proporciona múltiples herramientas y mecanismos de protección:
Rendimiento y optimización 
Existe una variedad de técnicas y herramientas que pueden ayudarlo a que su código se ejecute de manera más eficiente, más rápido y con menos recursos del sistema.

**Guía de instalación rápida**

Antes de que pueda usar Django, deberá instalarlo. Contamos con una completa guía de instalación que cubre todas las posibilidades; esta guía lo guiará a una instalación mínima que funcionará mientras recorre la introducción.

**Instalar Python**

Al ser un marco web de Python, Django requiere Python. Consulte ¿Qué versión de Python puedo usar con Django? para detalles. Python incluye una base de datos liviana llamada SQLite, por lo que no necesitará configurar una base de datos todavía.
Obtenga la última versión de Python en https://www.python.org/downloads/ o con el administrador de paquetes de su sistema operativo.
Puede verificar que Python esté instalado escribiendo Python desde su shell; deberías ver algo como:
Python 3.x.y
[GCC 4.x] on linux
Type "help", "copyright", "credits" or "license" for more information.

**Configurar una base de datos**

Este paso solo es necesario si desea trabajar con un motor de base de datos "grande" como PostgreSQL, MariaDB, MySQL u Oracle. Para instalar dicha base de datos, consulte la información de instalación de la base de datos .

**Instalar Django**

Tienes tres opciones para instalar Django:
•	Instale una versión oficial . Este es el mejor enfoque para la mayoría de los usuarios.
•	Instale una versión de Django proporcionada por la distribución de su sistema operativo .
•	Instale la última versión de desarrollo . Esta opción es para entusiastas que desean las últimas y mejores funciones y no temen ejecutar un código nuevo. Es posible que encuentre nuevos errores en la versión de desarrollo, pero informarlos ayuda al desarrollo de Django. Además, es menos probable que las versiones de paquetes de terceros sean compatibles con la versión de desarrollo que con la última versión estable.
Verificando 
Para verificar que Python puede ver Django, escriba pythondesde su shell. Luego, en el indicador de Python, intente importar Django:

>>> importar django
>>> imprimir (django.get_version ())
>>>3.1

![](https://codingornot.com/wp-content/uploads/2017/10/dijango-porque-usarlo.png)

------------


<a name= "item8"></a>
## Ventajas del patrón MVC

•	La implementación se realiza de forma modular.

•	Sus vistas muestran información actualizada siempre. El programador no debe preocuparse de solicitar que las vistas se actualicen, ya que este proceso es realizado automáticamente por el modelo de la aplicación.

•	Cualquier modificación que afecte al dominio, como aumentar métodos o datos contenidos, implica una modificación sólo en el modelo y las interfaces del mismo con las vistas, no todo el mecanismo de comunicación y de actualización entre modelos.

•	Las modificaciones a las vistas no afectan al modelo de dominio, simplemente se modifica la representación de la información, no su tratamiento.

•	MVC está demostrando ser un patrón de diseño bien elaborado pues las aplicaciones que lo implementan presentan una extensibilidad y una mantenibilidad únicas comparadas con otras aplicaciones basadas en otros patrones.

------------
<a name= "item9"></a>
## Resultados

<a name= "item10"></a>
###### Otros modelos/frameworks de patrones de diseño

<a name= "item11"></a>
**Patrón Observer**

Observa los cambios de estado que tenga un sujeto u objeto para notificar sus suscripciones.

Ejemplo: Crearemos una clase para incrementar el valor númerico de su propiedad y cada vez que este valor sea alterado vamos a notificar el cambio de este estado a través de la consola.

Necesitamos definir una clase que será nuestro observador y permita suscribir o desuscribir las notificaciones para nuestro sujeto.

DEFINIENDO NUESTRA CLASE OBSERVADORA
~~~
class Observable {
    constructor() {
        this.observers = [];
    }
    // Suscribe una clase notificadora
    subscribe(c) {
        this.observers.push(c);
    }
    // Desuscribe la clase notificadora
    unsubscribe(c) {
        this.observers = this.observers.filter(observer => observer instanceof c !== true);
    }
    // Llama a todos nuestros suscriptores
    notify(model) {
        this.observers.forEach(observer => {
            observer.notify(model);
       });
	   }
}
~~~
DEFINIENDO NUESTRO SUJETO

Creemos al sujeto, que para nuestro caso será la clase con la que vamos a probar el ejercicio.
~~~
class NumberExample extends Observable {
    constructor() {
        super();
        this.value = 0;
    }
    increment() {
        this.value++;
        // Llama a los suscriptores
        this.notify(this);
    }
}
~~~

•	Dicha clase hereda de la clase Observable para que pueda suscribir a los suscriptores.

•	Cada vez que incrementamos el valor de nuestra propiedad se dispara la notificación llamando a todas las suscripciones que hayamos definido.

DEFINIENDO NUESTROS SUSCRIPTORES

Vamos a definir 2 suscriptores, el cual serán 2 clases que enviarán un mensaje a la consola del browser en español y en inglés.
~~~
class NumberExampleSpanishConsole {
    notify(model) {
        console.log(`El nuevo número es ${model.value}`);
    }
}

class NumberExampleEnglishConsole {
    notify(model) {
        console.log(`The new number is ${model.value}`);
    }
}
~~~

HORA DE SUSCRIBIR

// Instanciamos al sujeto
`let numberExample = new NumberExample();`

// Le suscribimos sus suscriptores o listeners
~~~
numberExample.subscribe(new NumberExampleEnglishConsole());
numberExample.subscribe(new NumberExampleSpanishConsole());
~~~
Cada vez que llamemos al método incrementar serán invocados los suscriptores o listeners.

`numberExample.increment();`
// El nuevo número es 1

`numberExample.increment();`
// El nuevo número es 2

`numberExample.increment();`
// El nuevo número es 3


Se pueden programar las impresiones de la consola en el método incrementar y nos olvidábamos de crear tantas clases.
Pero, el problema radica en que le daríamos muchas responsabilidades al método incrementar, ya que su objetivo del método es solo incrementar, más no imprimir.
Por eso, al plantearlo de esta manera y resolverlo a través del patrón observador creamos un módelo más escalable y fácil de mantener porque ya no programamos todo en el mismo lugar evitando de esta manera el fuerte acomplamiento y nos volvemos menos propensos a errores.
El patrón estrategia (Strategy Pattern) es un patrón de tipo comportamental es decir, se centra en definir la forma en la que se produce el intercambio de mensajes entre distintos componentes. Básicamente, su propósito es mantener un conjunto de algoritmos (estrategias) de entre los cuales el objeto cliente puede elegir aquel que le conviene e intercambiarlo dinámicamente según sus necesidades.

Hay 4 actores diferenciados en este patrón:

**Cliente** Es quien solicita la acción, también es quien fija la estrategia a utilizar. 

**Contexto** Es la clase que alberga la información necesaria para ejecutar las estrategias y también la clase que hace uso de ellas. Al contexto debemos de informarle de la estrategia a utilizar mediante un setter u otro mecanismo.

**Interfaz de la estrategia** Es el contrato que debe de cumplir cada estrategia que queramos implementar. Este contrato permite al contexto conocer y estandarizar el uso de las estrategias, no teniendo que conocer la implementación final de cada una para tener que ejecutarlas.

Hay una forma alternativa al uso de la Interfaz de la Estrategia, que es simplemente pasarle el contexto a las estrategias concretas. En ese caso obviamente no sería necesario definir una interfaz.

**Interfaz concreta** Es una implementación del contrato de la interfaz, si pensamos en alguno de los casos anteriores de ejemplo, es quien define cómo se mueve un peón, quién sabe cómo se calcula una ruta en bici, quién sabe cómo formatear un texto centrado o cómo formatear un PDF a exportar.

Ejemplo
~~~
<?php declare(strict_types=1);

namespace App;

use App\Strategy\FormatContext;
use App\Strategy\HtmlFormatStrategy;
use App\Strategy\MarkdownFormatStrategy;

$context = new FormatContext();

$context->setStrategy(new HtmlFormatStrategy());
echo $context->format('Hi!');

$context->setStrategy(new MarkdownFormatStrategy());
echo $context->format('Hi!');

<?php declare(strict_types=1);

namespace App\Strategy;

class FormatContext
{
    private $strategy;
    private $message;
    
    public function setStrategy(Strategy $strategy): void
    {
        $this->strategy = $strategy;
    }
    
    public function format(string $message): string
    {
        if (null === $this->strategy) {
            throw new RuntimeException('Missing strategy');    
        }
        
        return $this->strategy->execute($message);   
    }
}

<?php declare(strict_types=1);

namespace App\Strategy;

interface FormatStrategy
{
    public function execute(string $message): string;
}

<?php declare(strict_types=1);

namespace App\Strategy;

class HtmlFormatStrategy implements FormatStrategy
{
    public function execute(string $message): string
    {
        return '<html><body><h1>' . $message . '</h1></body></html>';
    }
}

<?php declare(strict_types=1);

namespace App\Strategy;

class MarkdownFormatStrategy implements FormatStrategy
{
    public function execute(string $message): string
    {
        return '# ' . $message;    
    }
}
~~~
<a name= "item12"></a>
**Patrón Adapter**

Es utilizado cuando tenemos interfaces de software incompatibles, las cuales a pesar de su incompatibilidad tiene una funcionalidad similar. Este patrón es implementado cuando se desea homogeneizar la forma de trabajar con estas interfaces incompatibles, para lo cual se crea una clase intermedia que funciona como un adaptador. Esta clase adaptador proporcionará los métodos para interactuar con la interface incompatible
Los componentes que conforman el patrón son los siguientes:

•	Client: Actor que interactua con el Adapter.

•	Target: Interface que nos permitirá homogenizar la forma de trabajar con las interfaces incompatibles, esta interface es utilizada para crear los Adapter.

•	Adapter: Representa la implementación del Target, el cual tiene la responsabilidad de mediar entre el Client y el Adaptee. Oculta la forma de comunicarse con el Adaptee.

•	Adaptee: Representa la clase con interface incompatible.

•	El Client invoca al Adapter con parámetros genéricos.

•	El Adapter convierte los parámetros genéricos en parámetros específicos del Adaptee.

•	El Adapter invoca al Adaptee.

•	El Adaptee responde.

•	El Adapter convierte la respuesta del Adaptee a una respuesta genérica para el Client.

•	El Adapter responde al Client con una respuesta genérica.

Ejemplo
~~~
package com.arquitecturajava.ejemplo2;

public class Principal {

  public static void main(String[] args) {
    
    Conectable l1= new Lampara();
    encenderAparato(l1);
    
    Conectable o1= new Ordenador();
    encenderAparato(o1);
    Conectable l2= new AdaptadorLampara();
    encenderAparato(l2);

  }

  private static void encenderAparato(Conectable l1) {
    l1.encender();
    System.out.println(l1.estaEncendida());
  }

}
~~~


<a name= "item13"></a>
## **Conclusión**
El patron MVC es una excelente opción para organizar ya que hace que se nos facilite la creación de nuestra aplicación y de esta manera todos los desarrolladores puedan tener acceso a ella de manera que puedan entender como fue el desarrollo de la aplicación, y si bien es necesaria alguna modificación se pueda lograr sin errores.
