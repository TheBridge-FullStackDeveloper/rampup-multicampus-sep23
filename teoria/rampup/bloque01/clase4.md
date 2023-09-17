# 4. Entidades, símbolos y accesibilidad

## Entidades
***
Dado que en HTML existen caracteres reservados que se utilizan para escribir código (por ejemplo: <>, &, ' ') nació lo que llamamos entidades, las cuales se utilizan para mostrar esos caracteres. Su sintaxis puede escribirse con letras: &nombre-de-la-entidad; o números: &#numero-de-la-entidad; .

A continuación puedes ver una lista de las entidades que se pueden utilizar en HTML en el siguiente enlace: http://www.manualweb.net/html/entidades-html/ . Como ves, puedes utilizar el código numérico con la sintaxis señalada anteriormente, o puedes utilizar el nombre de la entidad. Sin embargo, hay algunos caracteres que no tienen nombre, pero sí código numérico, por lo que, según el carácter que tengas que poner, utilizarás uno u otro. 


#### Recursos

- [W3S - Entidades](https://www.w3schools.com/html/html_entities.asp)
- [Manual Web- Entidades](http://www.manualweb.net/html/entidades-html/)

## Símbolos
***
Además con las entidades, podemos representar símbolos matemáticos y técnicos. Para ello utilizaremos la nomenclatura asignada para dichos símbolos. Incluso todos los caractéres, letras y número, pueden representarse con esta nomenclatura. 

A continuación, te adjuntamos la lista de caracteres que puedes utilizar en HTML: https://ascii.cl/es/ 


#### Recursos

- [W3S - Símbolos](https://www.w3schools.com/html/html_symbols.asp)
- [Código ascii - Símbolos](https://ascii.cl/es/)


## Accesibilidad
***
Entendemos la accesibilidad web como la capacidad de una página de llegar al mayor número de personas, independientemente de sus capacidades. Una web es accesible cuando se utilizan las herramientas adecuadas para que lo sea, y ahí es donde entran en juego las etiquetas semánticas en HTML. Estas etiquetas al ser de fácil identificación y definir el elemento o elementos que contiene, beneficia tanto al usuario, al rendimiento en móviles y al SEO de nuestra página, que tendrá un mejor posicionamiento. 

Utilizar etiquetas semánticas hará que los lectores de pantalla sean capaces de leer de forma eficaz e identificar los distintos elementos que hay en la página. Gracias a la semántica, los lectores de pantalla llevarán a cabo el comportamiento adecuado, siendo esta herramienta de más utilidad para el usuario. 

Recordemos que las etiquetas semánticas son: nav, aside, main, header, footer, section, article... Y debemos intentar utilizarlas en la medida de lo posible, sustituyendo a aquellas etiquetas que no aportan contenido, como son los div. Respecto al contenido multimedia, debemos utilizar textos alternativos bajo el atributo alt, para describir o definir el contenido con la mayor veracidad posible. En el caso de que las imágenes tengan solo un fin decorativo y solo en ese caso, el texto alternativo puede aparecer vacío, así el lector de pantalla ignorará esa imagen. 

Existen herramientas que podemos utilizar para analizar la accesibilidad de nuestra página, los posibles fallos y cambios que deberíamos llevar a cabo, para que nuestra web sea más accesible. 

La primera es *Wave Evaluation Tool*, una extensión de Chrome que hace un análisis rápido sobre los errores más importantes, las zonas donde se encuentran, lo que considera alertas y las buenas prácticas utilizadas. También contamos con la herramienta de *Axe DevTools - Web Accesibility Testing* que tras analizar la página nos da un informe detallado sobre todos los fallos y errores que hay respecto a la accesibilidad y la posible forma en que se solucionaría esos problemas que nos ha señalado.

#### Recursos

- [W3S - Accesibilidad](https://www.w3schools.com/html/html_accessibility.asp)
- [MDN - Accesibilidad](https://developer.mozilla.org/es/docs/Learn/Accessibility/HTML)



