# css-animations

## Curso de animaciones con CSS en Platzi
- Link -> https://platzi.com/cursos/animaciones-css/

### Notas:
- [Markdown sintax](https://markdown.es/sintaxis-markdown/)

## Clase 1: Counter CSS

- counter-reset: Crea o reinicia un contador.
- counter-increment: Incrementa un valor del contador.
- content: Inserta el contenido generado (debe usarse con un pseudoelemento).
- counter(): Función que agrega el valor de un contador a un elemento.

## Clase 2: Contexto de apilamiento

- https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes
Eje Z, es el eje que sale del navegador hacia ti como usuario.
Determinar que va a ir primero y que despues.

atajos: emmet ->  
- .layer-$*10
- .phone>.layer-$*10
- El position relativo es el telefono, el resto de las capas son absolutas
    - los elementos se van a posicionar a partir del telefono

## Reto:
- ✅ Realizar Capas 4-10 
![Capas][img1] 
[img1]: /assets/img/layers.png "Capas de ejemplo"

## Clase 4: Agregando los conejos por CSS
Lecturas:
- https://dev.to/cchana/explained-creating-a-zigzag-pattern-with-just-css-13g1
- https://www.magicpattern.design/tools/css-backgrounds
- https://css-tricks.com/a-few-background-patterns-sites/

## Reto:
- ✅ Completar los patrones de Zig-Zag del Wall con Linear gradients

## Clase 5: Animation name y keyframe
Lecturas:
- [CSS Animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
Propiedad: 
- animation-name: colocarle un nombre a nuestra fracción de codigo que queremos animar, para que nuestro Keyframe sepa a quien animar.
- ej: animation-name: blink;

### Transiciones: 
- Punto A a B, sin nada en el medio. 
- Solo estado inicial a final. 
- Nos quedamos cortos en cuanto a la manipulacion de los estados a traves del tiempo.
### Keyframe: 
- Punto A a B pero le podemos manipular el tiempo que hay desde el principio hasta el final.
- 0 inicial, 100 final, y numeros en el medio, que en 50 agregue una propiedad, etc.
- Podemos utilizar palabras claves como "from" y "to"

---

Dentro de la clase: 

`
.head__eye{
    animation-name: blink;
}
`

Fuera de la clase:
`
@keyframes blink {
    0% {}
    5% {}
    10% {}
}
`
---

## Clase 6: Animation duration
Tiene dos propiedades principales:
- animation duration: Cuanto tiempo va a durar mi animacion, si quiero que sea rapido, lento, etc
- animation-iteration-count: cuantas veces se va a repetir la animacion, 1 vez, 2 veces, infinito.


Debemos elegir cuales son las propiedades que queremos animar, por ejemplo el height

`
    animation-name: blink;
    animation-duration: 2s;
    animation-iteration-count: infinite;
`
`
@keyframes blink {
    0% { height: 4px; }
    5% { height: 1px; }
    15% { height: 4px;}
}
`

los porcentajes de los keyframes son basados en el animation duration
Es decir, que 10% es el 10% de 2 segundos. (0.2seg)

## Clase 7: Animation timing-function y delay

animation-delay: tiempo de espera para que se ejecute nuestra animacion
animation-timing-function: = Aceleracion, como quiero que se muevan mis elementos.
Funciona parecido a las transiciones: ease-in, out, in-out, linear, etc

Vamos a utilizar selectores de atributos
´
.layer-1 input[type=checkbox]{
    
}
´
### Recursos: 
- [Cubic-bezier](https://cubic-bezier.com/#.17,.67,.83,.67)
- Ver reglas para el navegador Chrome
- [Animate.css](https://animate.style/)
- [unDraw](https://undraw.co/illustrations)

## Clase 8: Animation direction, fill mode y play state
- animation-direction: la dirección en la que va a ir la animación, hacia adelante, hacia atrás, etc.
    - normal: la animación se ejecutará hacia delante. Si se repite, cuando vuelve a empezar parte de la situación inicial.
    - reverse: la animación se ejecutará hacia detrás. Si se repite, cuando vuelve a empezar parte de la situación inicial.
    - alternate: la animación se ejecutará una vez en un sentido y otra vez en otro, comenzando hacia delante, luego hacia detrás y así sucesivamente el número de repeticiones especificado.
    - alternate-reverse: la animación se ejecutará una vez en un sentido y otra vez en otro, comenzando hacia detrás, luego hacia delante y así sucesivamente el número de repeticiones especificado.
- animation-play-state: En que estado va a estar nuestra animacion, pausada, play, etc.
    Esta propiedad permite detener una animación que se está ejecutando (ponerla en pausa). Su valor por defecto es running y sus dos valores posibles son:
    - running: la animación está en ejecución
    - paused: la animación está en pausa

- animation-fill-mode: nos dice cual es el estado al iniciar o al terminar la animacion. Lo mas normal es indicar un estado al finalizar.

    - none: el elemento comenzará y quedará en el estado previo a la animación.
    - forwards: el elemento quedará en el estado final de la animación.
    - backwards: el elemento se pondrá en el estado indicado para el comienzo de la animación inmediatamente y esperará en ese estado hasta que se cumpla el tiempo indicado en animation-delay. Una vez se cumpla ese tiempo la animación continuará la ejecución desde ese estado inicial.
    - both: combinación de las dos opciones anteriores.
### Reto: 
Solo con la propiedad animation, controlar name, timing-function, iteration-count, todo reducido en una sola.

~~~
    animation-name: bunny-1;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-iteration-count: infinite;
~~~

`
    animation: bunny-1 2s ease-in-out infinite;
    - Sintaxis: 
    animation: name duration timing-function delay iteration-count direction fill-mode;
`


### Adjuntos:
- [CodePen Zanahoria](https://codepen.io/camilo315853/pen/mdWKeRZ?editors=0100)