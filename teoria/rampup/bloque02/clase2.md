# 2. Transform, transiciones y animaciones

## Transform
***
Podemos hacer que los elementos de nuestra página puedan moverse de un lado para otro, rotar... Es decir, cambiar su estado que le hayamos indicado por otro. Se aplicará cada vez que se recargue la página o utilicemos alguna propiedad que le indique que debe hacerlo cuando pase algo (como clickar en él o pasar el ratón por encima).

- **translate()**: este método mueve el elemento seleccionado desde su posición actual tantas unidades de medida (suelen ser píxeles), que pongamos en el eje x y en el eje y.

- **rotate()**: con este método rotaremos el elemento seleccionado los grados(deg) que le señalemos (estos van de 0 a 365).

- **scaleX()**: con este método incrementamos el ancho de un elemento. Dentro de los paréntesis tendremos que ponerle el valor por el que queremos multiplicarlo.

- **scaleY()**: este método incrementa la altura de un elemento. Dentro de los paréntesis debemos señalar el valor por el que queremos que se multiplique.

- **scale()**: con este método podemos incremental el ancho y el alto del elemento seleccionado. Dentro del paréntesis, el primer parámetro es el ancho y el segundo, la altura.

- **skewX()**: este método hace que el elemento se sesgue a partir del eje x, los grados que le indiquemos.

- **skewY()**: este método hace que el elemento se sesgue a partir del eje y, los grados que le indiquemos.

- **skew()**: este método hace que el elemento se sesgue tanto a partir del eje x como del eje y, los grados que le indiquemos.

- **matrix()**: este método aúna todos los métodos vistos anteriormente, en este orden: matrix (scaleX (), skewY (), skewX (), scaleY (), translateX (), translateY ())


#### ¿Cómo escribirlo en código?
```html
    <img src="apuntes-web-app/src/img/cerezo.png" class="one" />
    <img src="apuntes-web-app/src/img/cerezo.png" class="two" />
    <img src="apuntes-web-app/src/img/cerezo.png" class="three" />
    <img src="apuntes-web-app/src/img/cerezo.png" class="four" />
    <img src="apuntes-web-app/src/img/cerezo.png" class="five" />
    <img src="apuntes-web-app/src/img/cerezo.png" class="six" />
    <img src="apuntes-web-app/src/img/cerezo.png" class="seven" />
    <img src="apuntes-web-app/src/img/cerezo.png" class="eight" />
```
```css
    img {
        width: 100px;
        height: 100px;
    }

    img.one {
        transform: traslate(20px, 40px);
    }

    img.two {
        transform: rotate(50deg);
    }

    img.three {
        transform: scaleX(0.5);
    }

    img.four {
        transform: scale(0.5, 1.5);
    }

    img.five {
        transform: skewX(20deg);
    }

    img.six {
        transform: skewY(20deg);
    }

    img.seven {
        transform: skewX(20deg, 30deg);
    }

    img.eight {
        transform: matrix(1, 0.5, 0, 1, 0, 0);
    }

```

#### ¿Cómo se vería representado?

![img](../../../assets/bloque02/clase2-ejemplo1.png)

#### Recursos

- [CSS Transform](https://www.w3schools.com/css/css3_2dtransforms.asp)


## Transitions
***

Las transiciones son una propiedad de css que permite dar un efecto especial al elemento seleccionado durante una duración determinada. Existen varias propiedades que llevan transition. Dependiendo de nuestras necesidades, utilizaremos una u otra o incluso las combinaremos.

La propiedad transition debe llevar mínimo, la propiedad a la que queremos aplicar el efecto (por ejemplo width) y la duración (expresada en segundos).

Las más utilizadas son:

- **transition**: esta propiedad engloba todas las transiciones que señalaremos a continuación. Es decir, en él se especificará el delay, la duración, la propiedad y el timing. Siendo su sintaxis: 

        transition: property duration timing-function delay|initial|inherit;

- **transition-property**: esta propiedad especifica el nombre de la propiedad de CSS en la que se va a producir la transición. Sus valores pueden ser: _none_ que especifica que no se aplicará la transición, _all_, si todas las propiedades tendrán esa transición, _la propiedad que queremos cambiar_ como por ejemplo, el width o el height, _initial_ que toma la propiedad en su valor predeterminado y _inherit_ que hereda el valor de su padre.

- **transition-duration**: el valor que le damos será el número de segundos o milisegundos que tarda en completarse la transición. Los valores que puede llevar son _el tiempo que queremos que dure_ que por defecto es 0, y se expresa en s o milisegundos, _initial_ que toma el valor por defecto e _inherit_ que toma el valor que hereda de su padre.

- **transition-timing-function**: esta propiedad determina la curva de velocidad que tomará la transición. Sus valores pueden ser: _ease_, empieza lento, luego rápido y acaba lento, _linear_, que siempre tenga la misma velocidad, _ease-in_, que sería una transición con un efecto lento al empezar, _ease-in-out_, que sería una transición con un efecto lento al acabar, _step-start_, que lleva directamente al paso final al empezar la transición, _step-end_, que lleva directamente al paso final al acabar la transición, _steps(int,start|end)_ que especifica los pasos que llevará a cabo, _cubic-bezier(n,n,n,n)_ le indicamos la velocidad según el momento de la transición (los valores van de 0 a 1), _initial_ que toma su valor por defecto e _inherit_ que hereda la propiedad de su padre.

- **transition-delay**: el valor que le demos determinará el tiempo que tardará en empezar la transición desde que se cargue el navegador. Los valores pueden ser _el tiempo que queremos que tarda en empezar_ que por defecto es 0, y se expresa en segundos o milisegundos, _initial_ que toma el valor por defecto e _inherit_ que toma el valor que hereda de su padre.

Una transición se suele producir cuando el usuario pasa el cursor por elemento. Para ello utilizaremos el selector :hover.

#### ¿Cómo escribirlo en código?

```html
    <div class="one"></div>

    <div class="two"></div>

    <div class="three"></div>
```

```css
div {
  width: 100px;
  height: 100px;
  background-color: cornflowerblue;
  margin-top: 5px;
}

div.one {
  width: 100px;
  transition: width 3s linear 1s;
}

div.one:hover {
  width: 300px;
}

div.two {
  height: 100px;
  transition: widht 2s height 2s ease-in 3s;
}

div.two:hover {
  height: 300px;
}

div.three {
  width: 100px;
  transition: width 0.5 step-start initial;
}

div.three:hover {
  height: 300px;
}
```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase2-ejemplo2.gif)


#### Recursos

- [CSS Transitions](https://www.w3schools.com/css/css3_transitions.asp)


## Animations
***
Esta propiedad permite aplicar animaciones a elementos que hayamos seleccionado. Cambian las propiedades de su estilo a otras. Debemos tener en cuenta que las animaciones se repetirán las veces que le indiquemos. Una propiedad que siempre será obligatoria en las animaciones son las @keyframes ya que especifican los pasos que seguirá la animación respecto al estilo. Así que, veamos las propiedades que puede tener una animación:

- **@keyframes**: en esta propiedad se le especifica su estado inicial y su estado final. Su estado inicial se indicará con esta sintaxis: 

    *from {propiedad a cambiar: el valor de la propiedad} to {propiedad por la que cambia: el valor de la propiedad}*. 
    
    Podemos poner también porcentajes, en vez de la anterior sintaxis, indicándole en qué momento de la animación se encuentra, por ejemplo:   
    
    *0%   {background-color: red;} 25%  {background-color: yellow;}   50%  {background-color: blue;}  100% {background-color: green;}*

- **animation-name**: es el nombre que le daremos a la animación, y por lo tanto, el nombre que usaremos en @keyframes. 

- **animation-duration**: con él indicamos el tiempo que tardará la animación en hacerse cada vez.

- **animation-delay**: es el tiempo que tardará en empezar la animación. 

- **animation-iteration-count**: especifica el número de veces que se reproducirá la animación.

- **animation-direction**: determina como debe reproducirse una animación, si de atrás a adelante, de adelante a atrás, en ciclos... Sus valores pueden ser: *normal* (la animación se reproduce por su forma por defecto), *reverse* (la animación se reproduce en la dirección contraria a la especificada), *alternate* (la animación se reproduce primero hacia adelante y luego hacia atrás), *alternate-reverse* (la animación se reproduce primero hacia atrás y luego hacia adelante).

- **animation-timing-function**: con él le indicamos la velocidad que tomará en cada momento la animación. Sus valores, como vimos con las transiciones pueden ser: *ease* (la animación empieza lenta, después rápida y acaba lenta), *linear* (la velocidad de animación siempre es la misma), *ease-in* (la animación comienza con un inicio lento), *ease-out* (la animación termina de forma lenta), *ease-in-out* (la animación empezará de forma lenta y acabará de forma lenta), *cubic-bezier(n,n,n,n)* con él le indicamos los valores que queremos que tome. 

- **animation-fill-mode**: especifica en qué momentos la animación va a reproducirse. 

- **animation**: engloba todas las propiedades en si, según la siguiente estructura: 
{animation-name: ""; animation-duration: ""; animation-timing-function: ""; animation-delay: ""; animation-iteration-count: ""; animation-direction: ""; }


#### ¿Cómo escribirlo en código?

```css
    @keyframes firstExample {
        0%   {background-color: blue;}
        25%  {background-color: purple;}
        50%  {background-color: pink;}
        100% {background-color: red;}
    }

    div {
        width: 50px;
        height: 50px;
        position: relative;
        animation-name: firstExample;
        animation-duration: 8s;
        animation-iteration-count: 4;
        animation-direction: alternate;
    }


```

#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase2-ejemplo3.gif)


#### ¿Cómo escribirlo en código?

```css
    @keyframes secondExample {
    from {
        background-color: green;
    }
    to {
        background-color: purple;
    }
    }

    div {
        width: 100px;
        height: 100px;
        margin-top: 5px;
        animation: secondExample 2s ease-in 5s infinite alternate;
    }

```
#### ¿Cómo se vería representado?
![img](../../../assets/bloque02/clase2-ejemplo4.gif)

#### Recursos

- [CSS Animations](https://www.w3schools.com/css/css3_animations.asp)

