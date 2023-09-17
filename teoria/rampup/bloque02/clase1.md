# 1. Selectores y propiedades de texto

## *Introducción*

Durante este bloque estudiaremos lo que conocemos como Cascadign StyleSheets o CSS, que es un lenguaje que se utiliza para dar estilos a nuestras páginas. Anteriormente, se aplicaban los estilos directamente en nuestros documentos de HTML, por ello, este lenguaje de marcado nació para poder hacer una distinción entre los documentos de HTML y los documentos que aplican estilo a dichas páginas. 

Para vincularlos, pondremos una etiqueta en el head de nuestro documento HTML. Se posiciona dentro de la cabecera para que los estilos de CSS estén disponibles a la hora de renderizarse la página y que se muestre toda la estructura de HTML. 
La etiqueta que utilizaremos para vincularlos es la etiqueta link, que tiene la siguiente sintáxis: 
            
    <link rel="stylesheet" href="style.css" />

Esta etiqueta presenta el atributo rel, con el valor stylesheet, el cual le indica que lleva asociado un archivo de estilos y en href se le indica la ruta donde se encuentra ese archivo.

La sintáxis básica en CSS es la siguiente: 

    etiqueta {
        estilos que buscamos aplicar; 
    }

Como ya veremos más adelante, podemos utilizar distintos tipos de selectores para seleccionar el elemento del documento de HTML al que buscamos aplicar el estilo deseado. Al utilizar el selector debemos poner una llave de apertura y una llave de cierre, y por cada estilo que apliquemos, debemos separarlo con un punto y coma (; ).

Al igual que en HTML, existe una versión moderna de CSS que es la que nosotros estudiaremos: CSS3, la cual ha introducido nuevos bondades que podremos utilizar en nuestro día a día.

## *Teoría*

## Selectores
***
Los selectores de texto seleccionan elementos de HTML para poder aplicar estilo a la etiqueta seleccionada. Existen distintos tipos de selectores, los cuales utilizaremos según nuestras necesidades. Los tipos de selectores más utilizados son:

- Selectores simples
- Selectores combinados
- Selectores de pseudo-class selectors
- Selectores de pseudo-elementos
- Selectores de atributo

### Selectores simples
***

Podemos utilizar este tipo de selector para seleccionar por etiqueta, id, clase, conjunto de etiquetas...

- **Selectores por etiqueta:**
***
Podemos seleccionar etiquetas a las que queremos aplicar un estilo en concreto. Podemos seleccionar etiquetas por separado, o si queremos que el estilo se aplique a distintas etiquetas, también se pueden seleccionar, separadas por una coma.

#### ¿Cómo escribirlo en código?
Ejemplo: Las etiquetas h2 deben tener un color(color) de texto marrón(brown) y un tamaño(font-size) de 12px. La forma de escribirlo sería la siguiente
```css
    h2 {
        color: brown;
        font-size: 12px;
    }
```
Ejemplo: La etiqueta p debe tener un color de fondo(background-color) gris(grey) y todo el texto debe estar alineado(text-align) en el centro(center)
```css
    p {
        background-color: grey;
        text-align: center;
    }
```
Ejemplo: Todos los h4 tendrán un color de fondo(background-color) rosa(pink) y el color de la letra(color) será blanco(white)
```css
    h4{
        background-color: pink;
        color: white;
    }
```
Ejemplo: Queremos que todos los h2, las p y los h4 tengan un color blanco(white) y un fondo(background-color) negro(black):
```css
    h2, p, h4 {
        color: white;
        background-color: black
    }
```
#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo1.png)


- **Selectores por id:**
***
Este selector se utiliza cuando queremos seleccionar una etiqueta que tenga el atributo id, el cual lleva asociado el valor que le hayamos dado. Este atributo es único, por lo que ese atributo con ese valor solo se podrá utilizar en una etiqueta. La forma de utilizar el selector por id en css será con una almohadilla, seguida del valor que le hayamos dado a dicho id.

#### ¿Cómo escribirlo en código?

Ejemplo: Tenemos la siguiente etiqueta: \<h1 id="title">El título de mi página\<h1>. Queremos que su color de fondo(background-color) sea verde(green) y su tamaño(font-size) de 20px.
```css
    #title {
      background-color: aquamarine;
      font-size: 20px
      }
```
Ejemplo: Tenemos la siguiente etiqueta: \<p id="danger-information">Información peligrosa\<p>. Queremos que su color de fondo(background-color) sea rojo(red) y su color(color) blanco(white).

```css
    #danger-information {
    background-color: red;
    color: white;
    }
```
#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo2.png)


- **Selectores por clase:**
***
Este selector se utiliza cuando queremos seleccionar una etiqueta que tenga el atributo class, el cual lleva asociado el valor que le hayamos dado. El atributo class con el mismo valor se puede utilizar cuantas veces queramos, por lo que es una forma práctica de aplicar el mismo estilo a distintas etiquetas. La forma de utilizar el selector por class en css será con una punto, seguida del valor que le hayamos dado a dicho id.

#### ¿Cómo escribirlo en código?

Tenemos las siguientes etiqueta: 
    
```html
    <h1 class="cool-style">El título de mi página<h1> 
    <h2 class="cool-style">El subtítulo mi página<h2> 
    <p class="cool-style">Aquí un texto</p> 
```
Ejemplo: Queremos que su color de fondo(background-color) sea amarillo(yellow) y su color sea negro(black).
```css
    .cool-style {
        background-color: yellow;
        color: black;
    }
```
#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo3.png)

- **Selector universal:**
***
Utilizamos este selector cuando queremos que todos los elementos que hay en HTML tengan este estilo. Se representan con un asterisco.

#### ¿Cómo escribirlo en código?

Ejemplo: Queremos que el tamaño(font-size) por defecto de todos los textos sea de 15px y su color de fondo (background-color) sea gris(grey)
```css
    * {
        background-color: grey;
        font-size: 15px;
    }
```
#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo4.png)

### Selectores combinados

Los selectores combinados permiten seleccionar etiquetas, clases, id, que presentan una relación entre ellas.

Existen distintas relaciones que pueden existir entre las etiquetas:

- Selector de descendiente (se representa con un espacio)
- Selector de hijo (se representa con un >)
- Selector de hermano adyacente (se representa con un +)
- Selector general de hermano(se representa con un ~)

Dependiendo de lo que necesitemos, utilizaremos uno u otro

- **Descendant selector:**
***
Este selector se utiliza para seleccionar todos los elementos de una etiqueta que hemos especificado. Se representa con un espacio entre el nombre de la etiqueta que hemos seleccionado y el tipo de elemento que es su descendiente.

#### ¿Cómo escribirlo en código?

Por ejemplo, tenemos el siguiente código:

```html
    <article>
        <p>Texto 1</p>
        <p>Texto 2</p>
        <p>Texto 3</p>
        <section>
          <p>Texto 4</p>
        </section>
    </article>
```

Para seleccionar todos los p que son descendientes de article y ponerles un fondo(background-color) verde palo, se escribiría así:

```css
    article p {
        background-color: palegreen;
    }
```

Este estilo afectaría a texto 1, texto 2, texto 3 y texto 4, ya que existe una relación de descendencia entre ellos, y aunque el texto 4 esté envuelto en una section, p sigue siendo descendiente de article.

#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo5.png)


- **Child selector:**
***
Este selector se utiliza para seleccionar todos los elementos que tiene dentro una etiqueta que hemos especificado. Su relación de parentesco sería la de padre e hijo. Se representa con un mayor que (>) entre el nombre de la etiqueta que hemos seleccionado y sus hijos. Todas las etiquetas que no tengas relación directa, no se verán afectados por este tipo de relación.

#### ¿Cómo escribirlo en código?

Por ejemplo, tenemos el siguiente código:

```html
    <article>
        <p>Texto 1</p>
        <p>Texto 2</p>
        <p>Texto 3</p>
        <article>
            <p>Texto 4</p>
        </article>
    </article>
```

Para seleccionar todos los p que son hijos de article y ponerles un tamaño(font-size) de 20px, se escribiría así:

```css
    article > p {
    font-size: 20px;
    }
```

Este estilo solo afectaría a texto 1, texto 2 y texto 3, ya que el texto 4, no es descendiente directo de article.

#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo6.png)

- **Adjacent Sibling Selector:**
***

Este selector se utiliza para seleccionar aquellos elementos que estén a la misma altura que otros. Su relación de parentesco sería de hermanos, sin embargo, este selector se refiere a aquel hermano que está después de él. Se representa con un mayor que (+) siendo el primer elemento el hermano que está por encima (adyacente).

#### ¿Cómo escribirlo en código?

Por ejemplo, tenemos el siguiente código:

```html
    <article>
        <p>Texto 1</p>
        <p>Texto 2</p>
    </article>

    <p>Texto 3</p>
    <p>Texto 4</p>

    <article>
        <p>Texto 5</p>
        <p>Texto 6</p>
    </article>
    <p>Texto 7</p>
```

Para seleccionar los p que tienen una relación de hermano adyacente con article, y que queramos que tengan un color tomato lo escribiríamos así

```css
    article + p {
    color: tomato;
    }
```


Este estilo solo afectaría a texto 3 y a texto 7, ya que son sus hermanos adyacentes.

#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo7.png)

- **General Sibling Selector:**
***
Este selector se utiliza para seleccionar aquellos elementos que estén a la misma altura que otros. Su relación de parentesco sería de hermanos, y selecciona a todos sus hermanos, no solo a su adyacente. Se representa con una cercilla (~) siendo el primer elemento el hermano que queremos seleccionar y el segundo elemento, todos los elementos hermanos que queremos seleccionar.

#### ¿Cómo escribirlo en código?

Por ejemplo, tenemos el siguiente código:

```html
    <article>
        <p>Texto 1</p>
        <p>Texto 2</p>
    </article>

    <p>Texto 3</p>
    <p>Texto 4</p>

    <article>
        <p>Texto 5</p>
        <p>Texto 6</p>
    </article>
    <p>Texto 7</p>
```

Para seleccionar los p que tienen una relación de hermano con article, y que queramos que tengan un color tomato lo escribiríamos así

```css
    article ~ p {
        color: tomato;
    }
```

Este estilo solo afectaría a texto 3, texto 4 y a texto 7, ya que son sus hermanos.

#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo8.png)


### Selectores de pseudo-classes
***
Las pseudoclases se utilizan para definir un estado especial del elemento, por ejemplo, cuando el elemento es clickado o ha sido visitado. Es muy útil cuando queremos que nuestra página tenga más interactividad gracias al comportamiento del usuario.

Para utilizar una pseudoclase, en primer lugar debemos utilizar el selector al que queremos aplicar la pseudoclase, dos puntos, y la pseudoclase. Es decir: 

    selector:pseudoclase{
        estilos
    }

Existen muchos ejemplos de pseudoclases. Aquí te adjuntamos un enlace donde aparecen todas las pseudoclases que puedes utilizar: https://www.w3schools.com/css/css_pseudo_classes.asp.
Nos centraremos en aquellas pseudoclases que nos permiten tomar varios elementos u etiquetas.

- **:first-child**: esta pseudoclase permite seleccionar todos los primeros hijos del elemento que hayamos seleccionado.

- **:last-child**: con esta pseudoclase seleccionaremos los últimos hijos. Para ello debemos indicar cual será el elemento hijo.

- **:first-of-type**: utilizando esta pseudoclase, debemos especificar el elemento a seleccionar. Seleccionará el primer elemento que aparezca que tenga un padre que le preceda.

- **:last-of-type**: utilizando esta pseudoclase, debemos especificar el elemento a seleccionar. Seleccionará el último elemento que aparezca que tenga un padre que le preceda.

- **:nth-child(n)**: selecciona cada elemento que ocupa la posición que le hemos señalado (en la n) p:nth-child(2) Selecciona cada p que es el segundo hijo de su padre. 

- **:nth-last-child(n)**: selecciona cada elemento que ocupa la posición señalada, contando a partir del último hijo.

- **:nth-last-of-type(n)**: selecciona cada elemento que ocupa la posición señalada, contando a partir del último elemento.

- **:nth-of-type(n)**: selecciona cada elemento del número que le hemos señalado.

#### ¿Cómo escribirlo en código?

```html
    <article>
        <p>1 párrafo</p>
        <p>2 párrafo</p>
        <p>3 párrafo</p>
        <p>4 párrafo</p>
        <p>5 párrafo</p>
        <p>6 párrafo</p>
    </article>
```
```css
    p:first-child {
        color: tomato;
    } 
```

#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo9.png)

#### ¿Cómo escribirlo en código?

```css
    p:last-child {
        color: tomato;
    } 
```

#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo10.png)

#### ¿Cómo escribirlo en código?

```css
    p:first-of-type {
        color: tomato;
    } 
```

![img](../../../assets/bloque02/clase1-ejemplo11.png)

```css
    p:last-of-type {
        color: tomato;
    } 
```

![img](../../../assets/bloque02/clase1-ejemplo12.png)

#### ¿Cómo escribirlo en código?
```css
    p:nth-child(2) {
        color: tomato;
    } 
```

![img](../../../assets/bloque02/clase1-ejemplo13.png)

#### ¿Cómo escribirlo en código?
```css
    p: nth-last-child(3) {
        color: tomato;
    } 
```
![img](../../../assets/bloque02/clase1-ejemplo14.png)

#### ¿Cómo escribirlo en código?
```css
    p: nth-last-of-type(2) {
        color: tomato;
    }
```
![img](../../../assets/bloque02/clase1-ejemplo15.png)

#### ¿Cómo escribirlo en código?
```css
    p: nth-of-type(2) {
        color: tomato;
    } 
```
![img](../../../assets/bloque02/clase1-ejemplo16.png)


### Selectores de pseudo-elementos
***
Los pseudo-elements se utilizan para seleccionar una parte específica del elemento. Por ejemplo, podemos querer seleccionar la primera letra del elemento, seleccionar los puntos que nos aparecen al pintar una lista, un elemento que queramos insertar antes o después de la etiqueta especificada...

A continuación veremos los pseudo-elementos más comunes, los cuales se representan con el elemento seleccionado, dos veces dos puntos y la pseudoclase. selector::pseudo-elemento.

- **::after**: con él se le puede añadir al elemento seleccionado con este pseudoelemento, cualquier cosa, como una imagen, una frase... al finalizar cada elemento seleccionado.

- **::before**: con él se le puede añadir al elemento seleccionado con este pseudoelemento, cualquier cosa, como una imagen, una frase... antes de cada elemento seleccionado.

- **::first-letter**: este pseudo-element sirve para seleccionar la primera letra del elemento seleccionado.

- **::first-line**: este pseudo-element sirve para seleccionar la primera línea del elemento seleccionado.

- **::marker**: se utiliza para seleccionar los marcadores de las listas. No necesita un elemento al que adherirse, al ser algo tan específico.

- **::selection**: aplica el estilo que le hayamos señalado, al seleccionar el usuario con el cursor esa porción de texto.

#### ¿Cómo escribirlo en código?

```html
    <h2>Primer h2</h2>
    <h2>Segundo h2</h2>
    <p>Primer párrafo<br/>
    Este sigue siendo el primer párrafo</p>
    <p>Segundo párrafo</p>
```
```css
    h2::after {
    content: "- The Bridge";
    }

    p::before {
    content: "Aquí tenemos un ejemplo";
    color: teal;
    }

    p::first-letter {
    font-size: 25px;
    }

    p::first-line {
    color: red;
    }

    ::marker {
    color: green;
    }

    ::selection {
    background-color: yellow;
    }
```

#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo17.png)

### Selectores de atributo
***
Utilizamos estos selectores para seleccionar un atributo de la etiqueta html que queramos seleccionar. La forma de escribirlo es con el elemento seleccionado seguido de dos corchetes, que llevan dentro el atributo que queremos seleccionar. Es decir, elemento[atributo]. Aunque en ocasiones, podemos no señalar el elemento, entonces se aplicaría a todos aquellos atributos que hemos señalado, independientemente del elemento.

Las diferencias que pueden existir al seleccionarlo se encuentran a la hora de escribir el elemento, que según el signo de puntuación que lleve al final, significará una u otra cosa. Pogamos varios ejemplos:

- **a[target="_parent"]**: selecciona todos los elementos que tengan el atributo target con el valor"\_parent"

- **[id~=bridge]**: selecciona aquellos elementos que su atributo id, contenga, entre otras palabras, la palabra bridge.

- **[class|="big"]**: con este signo de puntuación le indicamos que seleccione todos aquellas clases que comiencen por la palabra big.

- **[class^="bo"]**: con este signo de puntuación le indicamos que seleccione todos aquellas clases que comiencen por las letras bo.

- **[class*="ey"]**: con este signo de puntuación le indicamos que seleccione todos aquellas clases que contengan dentro de la palabra esas letras.

#### ¿Cómo escribirlo en código?
```html
    <a href="www.google.es" target="_blank">Enlace con target blanck</a>
    <a href="https://www.w3schools.com" target="_parent"
      >Enlace con target parent</a>

    <p id="bridge">Esta es una frase con un id que tiene la palabra bridge</p>
    <p class="big-trouble">
      Esta es una frase con tiene la clase big como primera palabra
    </p>
    <p class="bo">
      Esta es una frase con una clase que comienza con las letras bo
    </p>
    <p class="volleys">
      Esta es una frase que contiene en su clase las letras ey
    </p>
```
```css
    a[target="_parent"] {
        background-color: aquamarine;
    }

    [id~="bridge"] {
        background-color: palegreen;
    }

    [class|="big"] {
        background-color: palevioletred;
    }

    [class^="bo"] {
        background-color: gold;
    }

    [class*="ey"] {
        background-color: violet;
    }
```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo18.png)

#### Recursos

- [CSS](https://developer.mozilla.org/es/docs/Web/CSS)
- [Selectores](https://www.w3schools.com/css/css_selectors.asp)
- [Selectores combinados](https://www.w3schools.com/css/css_combinators.asp)
- [Selectores de pseudoclases](https://www.w3schools.com/css/css_pseudo_classes.asp)
- [Selectores de pseudoelemento](https://www.w3schools.com/css/css_pseudo_elements.asp)
- [Selectores de atributo](https://www.w3schools.com/css/css_attribute_selectors.asp)

## Estilos en CSS:
***
En CSS podemos modificar una gran cantidad de propiedades de la web. Las más utilizados son las siguientes:

### Colores de texto:
***
Para cambiar los colores del texto utilizamos la propiedad _color_. Existen distintas formas en que podemos especificar el color, siendo los más utilizados los siguientes:

- **El color al que nos queremos referir**: podemos utilizar el nombre del color, por ejemplo, red, blue, purple, pink, grey...

- **Color hexadecimal**: se expresa con una almohadilla seguida de seis letras o números. El valor de cada letra debe estar entre 00 y FF. La composición es la siguiente: #RRGGBB, RR es red, GG es gren y BB es blue. Para seleccionar el color que queremos jugaremos con todos estos elementos. 

- **Colores RGB**: se expresa de la siguiente manera: rgb(red, green, blue). Donde red, green y blue, deben ser cada uno un número entre 0 y 255. Según el color que queramos, pondremos más de un color que de otro, hasta obtener el color deseado. 

- **Colores RGBA**, se expresan de la misma manera que los anteriores, sin embargo, presenta un parámetro más, rgba(red, green, blue, alpha), que especifica la transparencia. Este valor alpha va de 0.0 a 1.0, siendo 0.0 totalmente transparente y 1.0 totalmente opaco.

No solo podemos darle color al texto, si no también un color de fondo al texto, el cual se expresará con la propiedad _background-color_, donde señalaremos el color que queremos ponerle. Esta propiedad acepta las distintas formas anteriormente señaladas de especificar el color.

#### ¿Cómo escribirlo en código?
```html
    <p>Primer párrafo</p>
    <p>Segundo párrafo</p>
    <p>Tercer párrafo</p>
    <p>Cuarto párrafo</p>
```
Para color:
```css
    - El color al que nos queremos referir: 
        p:nth-child(1) {
            color: white
        } 
    - Color hexadecimal: 
        p:nth-child(2) {
            color: #ffffff
        }
    - Color RGB: 
        p:nth-child(3) {
            color: rgb(255, 255, 255)
        }

    - Color RGBA: 
        p:nth-child(4) {
            color: rgb(255, 255, 255,1)
        }
```
Para fondo:
```css
    - El color al que nos queremos referir: 
        p:nth-child(1) {
            background-color: blue
        }
    - Color hexadecimal: 
        p:nth-child(2) {
            background-color: #0000ff
        }
    - Color RGB: 
        p:nth-child(3) {
            background-color: rgb(0,0,255)
        }
    - Color RGBA: 
        p:nth-child(4) {
            background-color: rgba(0,0,255, 0.5)
        }
        //Al poner que la opacidad sea de 0.5, el color se vería semitransparente
        }
```

#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo19.png)

#### Recursos

[Colores de texto](https://www.w3schools.com/css/css_text.asp)

### Font-family:
***
Para seleccionar la fuente que queremos aplicar en el texto de nuestra web, utilizamos la propiedad _font-family_. Existen distintos tipos de fuentes, según el estilo que lleven, el cual habrá que señalar a la hora de utilizarla:

- **serif**: presentan pequeños trazos en los bordes de las letras. 

- **sans-serif**: al contrario que serif, la caligrafía con estas fuentes es limpia, ya que no tiene trazos en ningún borde. 

- **monospace**: todas las letras tienen el mismo ancho. 

- **cursive**: estas fuentes por defecto son en cursiva, no hace falta aplicarles ya el efecto de cursiva. 

- **fantasy**: son fuentes decorativas.

Font-family es un caso especial en cuanto a propiedad, ya que hay que señalar varios nombres de fuentes alternativas para que todos los navegadores y sistemas operativos lo reconozcan. Debemos señalar en primer lugar la fuente que queremos y acabar con una fuente genérica. Esta variedad de fuentes nos la suele sugerir el editor de código cuando ponemos la fuente. Podemos poner fuentes externas que nos provea google fonts. En dicha página nos indicará como utilizar la fuente selecionada en nuestros archivos de html y de css.

#### ¿Cómo escribirlo en código?
```html
    <p>Primer párrafo</p>
    <p>Segundo párrafo</p>
    <p>Tercer párrafo</p>
    <p>Cuarto párrafo</p>
```
```css
    - serif: 
        p:nth-child(1) {
            font-family: "Times New Roman", Times, serif;
        }

    - sans-serif: 
        p:nth-child(2) {
            font-family: Arial, Helvetica, sans-serif;
    }

    - monospace: 
        p:nth-child(3) {
            font-family: "Lucida Console", "Courier New", monospace
        }
```
#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo20.png)


#### Recursos

[Font-family](https://www.w3schools.com/css/css_font.asp)

### Font-size:
***
Podemos especificar el tamaño de la fuente con la propiedad _font-size_. El tamaño de la fuente se puede expresar en valores absolutos, valores relativos y en tamaños.

- **Valores absolutos**: se utilizan las unidades de medida absolutas (mm, cm, in, pt, pc). Actualmente no se suelen utilizar, salvo los px, que es la forma de expresar los píxeles.

- **Valores relativos**: estas medidas son relativas ya que se adaptan al tamaño de la pantalla. Existen varias unidades relativas que podemos utilizar en nuestra hoja de estilos:

- porcentaje(%): define el ancho que ocupará el contenedor respecto al total.  

- em: esta medida hace referencia al tamaño en pixeles que tendrá el contenedor. Según la pantalla se verá más grande o más pequeño, y un 1em es equivalente a 16px.

- vh: utilizamos esta medida para referirnos al alto de la pantalla. Dado que el 100% del alto de la pantalla sería el alto de la pantalla, un vh sería el 1% del alto de la pantalla.

- vw: utilizamos esta medida para referirnos al ancho de la pantalla. Dado que el 100% del ancho de la pantalla sería el ancho de la pantalla, un vh sería el 1% del ancho de la pantalla.

- vmin: se usa para referirse al valor mínimo de vh.

- vmax: se usa para referirse al valor máximo de vh.

- vmw: se usa para referirse al valor mínimo de vw.

-**Tamaños**: podemos expresarlo en tamaños: xx-small, x-small, small, medium, large, x-large, xx-large, smaller, larger, length, %, initial, inherit...

#### ¿Cómo escribirlo en código?
```html
    <p class="p-1">1 párrafo</p>
    <p class="p-2">2 párrafo</p>
    <p class="p-3">3 párrafo</p>
    <p class="p-4">4 párrafo</p>
    <p class="p-5">5 párrafo</p>
    <p class="p-6">6 párrafo</p>
    <p class="p-7">7 párrafo</p>
    <p class="p-8">8 párrafo</p>
    <p class="p-9">9 párrafo</p>
    <p class="p-10">10 párrafo</p>
    <p class="p-11">11 párrafo</p>
```
```css
    px: 
        .p-1 {
            font-size: 5px;
    }

    %: 
        .p-2 {
            font-size: 5%;
        }

    em: 
        .p-3 {
            font-size: 2m;
        }

    vh: 
        .p-4 {
            font-size: 5vh;
        }

    vw: 
        .p-5 {
            font-size: 2vw;
        }

    vmin: 
        .p-6 {
            font-size: 5vmin;
        }

    vmax: 
        .p-7 {
            font-size: 2vmax;
        }

    vmw: 
        .p-8 {
            font-size: 5vmw;
        }

    xx-small: 
        .p-9 {
            font-size: xx-small
        }

    medium: 
        .p-10 {
            font-size: medium
        }

    xx-large: 
        .p-11 {
            font-size: xx-large
        }
```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo21.png)


#### Recursos

[Font-size](https://www.w3schools.com/cssref/pr_font_font-size.asp)

### Font-weight:
***
Esta propiedad de CSS define el grosor de la fuente. Sería lo que comunmente llamamos como negrita. Los valores que puede tener son los siguientes:

- **normal**: es el grosor por defecto que tiene el texto.

- **bold**: define una fuente con un grosor más grueso que el que tiene por defecto.

- **bolder**: tiene un grosor más grueso que el que tiene por bold.

- **lighter**: con un grosor más delgado que el que tiene por defecto.

- **100 o 200 o 300 o 400 o 500 o 600 o 700 o 800 o 900**: dependiendo del número, va aumentando el grosor de la fuente.

- **initial**: le da el grosor inicial que tuviera la fuente por defecto.

- **inherit**: toma el valor de font-weight que tuviera el padre.

#### ¿Cómo escribirlo en código?
```html
    <p class="p-1">1 párrafo</p>
    <p class="p-2">2 párrafo</p>
    <p class="p-3">3 párrafo</p>
    <p class="p-4">4 párrafo</p>
    <p class="p-5">5 párrafo</p>
    <p class="p-6">6 párrafo</p>
    <p class="p-7">7 párrafo</p>
```
```css
    p:nth-child(1) {
        font-weight: normal;
    }

    p:nth-child(2) {
        font-weight: bold;
    }

    p:nth-child(3) {
        font-weight: bolder;
    }

    p:nth-child(4) {
        font-weight: lighter;
    }

    p:nth-child(5) {
        font-weight: 400;
    }

    p:nth-child(6) {
        font-weight: initial;
    }

    p:nth-child(7) {
        font-weight: inherit;
    }
```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo22.png)


#### Recursos

[Font-weight](https://www.w3schools.com/cssref/pr_font_weight.asp)

### Text-align:
***
Esta propiedad define la alineación que tomará el texto respecto al ancho. El texto podrá estar alineado a la izquierda, derecha, centro...

- **left**: el texto se alineará a la izquierda del contenedor en el que está.

- **rigth**: el texto se alineará a la derecha del contenedor en el que se encuentra.

- **center**: el texto se situará en el centro del contenedor que lo contiene.

- **justify**: el texto se ajustará al ancho del contenedor y se esparcirá por este.

- **initial**: el texto se ajusta a su propiedad por defecto.

- **inherit**: toma la propiedad de su padre.

#### ¿Cómo escribirlo en código?
```html
    <div>
        <p class="p-1">1 párrafo</p>
        <p class="p-2">2 párrafo</p>
        <p class="p-3">3 párrafo</p>
        <p class="p-4">4 párrafo</p>
        <p class="p-5">5 párrafo</p>
        <p class="p-6">6 párrafo</p>
        <p class="p-7">7 párrafo</p>
    </div>
```
```css
    p:nth-child(1) {
        text-align: left;
    }

    p:nth-child(2) {
        text-align: right;
    }

    p:nth-child(3) {
        text-align: center;
    }

    p:nth-child(4) {
        text-align: justify;
    }

    p:nth-child(5) {
       text-align: initial;
    }

    p:nth-child(6) {
        text-align: inherit;
    }
```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo23.png)


#### Recursos

[Text-align](https://www.w3schools.com/cssref/pr_text_text-align.asp)

### Line-height:
***
Esta propiedad define la separación que hay entre líneas. A continuación veremos los posibles valores que le podemos dar a esta propiedad:

- **normal**: la separación que le da por defecto el navegador.

- **number**: le daremos un número por defecto. Este multiplicará ese valor por el tamaño de la fuente para establecer la altura.

- **length**: el valor que le damos se expresa en px, pt, pt, cm... Es decir, medidas absolutas.

- **%**: expresando el valor en porcentaje, este porcentaje tomará el tamaño actual de la fuente para calcular el alto de línea.

- **initial**: toma el tamaño que se le dió por defecto.

- **inherit**: toma el tamaño de su padre.

#### ¿Cómo escribirlo en código?
```html
    <p>1 párrafo</p>
    <p>2 párrafo</p>
    <p>3 párrafo</p>
    <p>4 párrafo</p>
    <p>5 párrafo</p>
    <p>6 párrafo</p>
```
```css
    p:nth-child(1) {
        line-height: normal
    }

    p:nth-child(2) {
        line-height: 2
    }

    p:nth-child(3) {
        line-height: 2px
    }

    p:nth-child(4) {
        line-height: 2%
    }

    p:nth-child(5) {
        line-height: initial
    }

    p:nth-child(6) {
        line-height: inherit
    }
```

#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase1-ejemplo24.png)


#### Recursos

[Line-height](https://www.w3schools.com/cssref/pr_dim_line-height.asp)

### Text-decoration:
***
Esta propiedad sirve para subrrayar el texto que hayamos seleccionado. Dependiendo del valor que le pongamos, la línea se situará en distinto lugar:

- **overline**: la decoración (línea) se situará por encima del texto.

- **line-through**: la decoración tacha el texto.

- **underline**: la decoración se pone por debajo del texto, lo subraya.

Podemos poner más de un valor:

- **underline overline**: en el texto aparecerán una línea por encima y otra por debajo.

También, podemos poner otras características de estilo, para ello la estructura es la siguiente:

_text-decoration: text-decoration-line text-decoration-color text-decoration-style|initial|inherit_

Es decir, se pondrá en primer lugar las propiedades de línea, que hemos visto, después el color que le queremos dar y por último, el estilo, que puede ser:

- **solid**: es su valor por defecto, pone una línea.

- **wavy**: con él pondrás una doble línea.

- **dotted**: este valor hace que la línea sea de puntos.

- **dashed**: este valor hace que la línea sea de pequeñas líneas.

- **wavy**: la línea que aparece presenta picos arriba y abajo.

- **initial**: toma el valor por defecto.

- **inherit**: toma el valor de su padre.

En definitiva, estos valores se puede combinar, como veremos a continuación en los ejemplos.

#### ¿Cómo escribirlo en código?
```html
    <p>1 párrafo</p>
    <p>2 párrafo</p>
    <p>3 párrafo</p>
```
```css
    p:nth-child(1){
        text-decoration: overline blue wavy
    }

    p:nth-child(2){
        text-decoration: line-through red dotted
    }

    p:nth-child(3){
        text-decoration: underline green wavy
    }
```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo25.png)


#### Recursos

[Text-decoration](https://www.w3schools.com/cssref/pr_text_text-decoration.asp)

### Vertical-align:
***
Esta propiedad define el alineamiento vertical que tendrá el elemento al que se lo apliquemos respecto al contenedor en el que está.

Los valores que puede tener esta propiedad son los siguientes:

- **baseline**: este es su comportamiento por defecto. El texto se alinea con la línea de su padre.

- **length**: acepta unidades relativas y absolutas. Sube o baja un elemento la distancia que le hayamos señado. También admite valores negativos.

- **%**: toma la separación entre líneas que le hemos indicado en "line-height" y le aplica el porcentaje correspondiente según el valor que le demos.

- **sub**: con este valor, el elemento toma la línea de abajo del padre y ubica a partir de esa línea el elemento.

- **super**: con este valor, el elemento toma la línea de encima del padre y ubica a partir de esa línea el elemento.

- **top**: el elemento se alinea con la línea que tiene el padre por encima y lo ubica desde esa posición para abajo.

- **text-top**: el elemento se alinea con la parte superior de la fuente del elemento principal.

- **middle**: el elemento se coloca en el medio del elemento padre.

- **bottom**: el elemento se alinea con la línea que tiene el padre por debajo y lo ubica desde esa posición par encima.

- **text-bottom**: el elemento se alinea con la parte inferior de la fuente del elemento principal.

- **initial**: toma su valor predeterminado.

- **inherit**: hereda la propiedad de su padre.

#### ¿Cómo escribirlo en código?
```html
    <p class="one">
      1 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="one" />
    </p>
    <p class="two">
      2 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="two" />
    </p>
    <p>
      3 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="three" />
    </p>
    <p>
      4 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="four" />
    </p>
    <p>
      5 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="five" />
    </p>
    <p>
      6 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="six" />
    </p>
    <p>
      7 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="seven" />
    </p>
    <p>
      8 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="eight" />
    </p>
    <p>
      9 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="nine" />
    </p>
    <p>
      10 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="ten" />
    </p>
    <p>
      11 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="eleven" />
    </p>
    <p>
      12 párrafo <img src="apuntes-web-app/src/img/cerezo.png" class="twelve" />
    </p
```
```css
    img.one {
        vertical-align: baseline;
    }

    img.two {
        vertical-align: 10px;
    }

    img.three {
        vertical-align: 50%;
    }

    img.four {
        vertical-align: sub;
    }

    img.five {
        vertical-align: super;
    }

    img.six {
        vertical-align: top;
    }

    img.seven {
        vertical-align: text-top;
    }

    img.eight {
        vertical-align: middle;
    }

    img.nine {
        vertical-align: bottom;
    }

    img.ten {
        vertical-align: text-bottom;
    }

    img.eleven {
        vertical-align: initial;
    }

    img.twelve {
        vertical-align: inherit;
    }

```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo26.png)


#### Recursos

[Vertical-align](https://www.w3schools.com/cssref/pr_pos_vertical-align.asp)

### Word-spacing:
***
Esta propiedad define el espacio que hay entre cada palabra del elemento seleccionado. Su valor puede ser:

- **normal**: define el espacio por defecto entre palabras, que es de 0.25 em.

- **length**: el espacio por defecto entre palabras se puede expresar con unidades relativas o absolutas como px, pt, cm, em... Se pueden utilizar valores negativos.

- **initial**: toma el valor de su propiedad por defecto.

- **inherit**: toma el valor que hereda de su padre.

#### ¿Cómo escribirlo en código?
```html
    <p>1 párrafo</p>
    <p>2 párrafo</p>
    <p>3 párrafo</p>
    <p>4 párrafo</p>
    <p>5 párrafo</p>
```
```css
    p:nth-child(1) {
        word-spacing: normal
    }

    p:nth-child(2) {
        word-spacing: 10px
    }

    p:nth-child(3) {
        word-spacing: 10vh
    }

    p:nth-child(4) {
        word-spacing: initial
    }

    p:nth-child(5) {
    word-spacing: inherit
    }
```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo27.png)


#### Recursos

[Word-spacing](https://www.w3schools.com/cssref/pr_text_word-spacing.asp)

### Writing-mode:
***
Define cómo se escribirá el texto (si de forma horizontal o vertical, y de que lado, si de izquierda a derecha o derecha a izquierda). Los valores que puede llevar asociados son:

- **horizontal-tb**: la escritura será de forma horizontal de izquierda a derecha y de arriba a abajo.

- **vertical-rl**: la escritura será de forma vertical de derecha a izquierda y de arriba a abajo.

- **vertical-lr**: la escritura será de forma vertical de izquierda a derecha y de arriba a abajo.

#### ¿Cómo escribirlo en código?
```html
    <p>1 párrafo</p>
    <p>2 párrafo</p>
    <p>3 párrafo</p>
```
```css
    p:nth-child(1) {
        writing-mode: horizontal-tb
    }

    p:nth-child(2) {
        writing-mode: vertical-rl
    }

    p:nth-child(3) {
        writing-mode: vertical-lr
    }
```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo28.png)


#### Recursos

[Writing-mode](https://www.w3schools.com/cssref/css3_pr_writing-mode.asp)

### Word-wrap:
***
Esta propiedad define si las palabras al no caber en el contenedor que las contiene por su tamaño, si deben bajar a la siguiente línea, o pueden separarse con un guion. Los valores que puede tener son los siguientes:

- **normal**: es el valor que tiene por defecto el cual indica que la palabra debe bajar a la siguiente línea.

- **break-word**: permite que las palabras se separen con un guion en el caso de que no quepan por el espacio del contenedor.

- **initial**: toma la propiedad por defecto.

- **inherit**: toma la propiedad de su padre.

#### ¿Cómo escribirlo en código?
```html
    <div>
      <p class="one">
        Este es el primer de los primeros de iwerjiowejrioweroirwjioerjiowojirw
      </p>
    </div>
    <div>
      <p class="two">
        Este es el segundo de los segundos de iwerjiowejrioweroirwjioerjiowojirw
      </p>
    </div>
    <div>
      <p class="three">
        Este es el tercero de los terceros de iwerjiowejrioweroirwjioerjiowojirw
      </p>
    </div>
    <div>
      <p class="four">
        Este es el cuarto de los cuartos de iwerjiowejrioweroirwjioerjiowojirw
      </p>
    </div>
```
```css
    div {
        width: 100px;
    }

    p.one {
        word-wrap: normal;
    }

    p.two {
        word-wrap: break-word;
    }

    p.three {
        word-wrap: initial;
    }

    p.four {
        word-wrap: inherit;
    }

```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase1-ejemplo29.png)


#### Recursos

[Word-wrap](https://www.w3schools.com/cssref/css3_pr_word-wrap.asp)

## Comentarios:
***
La estructura de los comentarios en css es la siguiente: /_ El comentario que queremos poner. _/

#### ¿Cómo escribirlo en código?

```css
p {
color: blue \/\*Maybe we will change later\*/
}
```

#### ¿Cómo se vería representado?

Dado que los comentarios los escribiremos en nuestro editor de código, no se verá representado en el navegador. 

#### Recursos

[Comentarios](https://www.w3schools.com/css/css_comments.asp)


