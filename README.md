<h1>Grid CSS</h1>
Grid CSS nace de la necesidad de colocar y distribuir los elementos a lo largo de una página, y recoge las ventajas de ese sistema, añadiendo numerosas mejoras y características que permiten crear rápidamente cuadrículas sencillas y potentes de forma prácticamente instantánea.

## Conceptos Básicos
Para utilizar Grid CSS necesitamos tener en cuenta los siguientes conceptos ya que son la base de este sistema de grillas.
![](https://static.platzi.com/media/user_upload/1-dd5c265b-bf7b-494a-b939-04d7866194a7.jpg)

Elementos principales del Grid CSS.

- Contenedor. El elemento padre contenedor que definirá la cuadrícula o rejilla.
- ítem. Cada uno de los hijos que contiene la cuadrícula (elemento contenedor).
- Celda (grid cell). Cada uno de los cuadros que conforman la cuadrícula, esta sería la unidad mínima.
- Area (grid area). Región o conjunto de celdas de la cuadrícula.
- Banda (grid track). Banda horizontal o vertical de celdas de la cuadrícula.
- Línea (grid line). Separador horizontal o vertical de las celdas de la cuadrícula.

Para trabajar con el concepto de cuadriculas Grid CSS se necesita un escenario similar al siguiente en nuestro código HTML.

    <!-- contenedor -->
    <section>
    		<!-- ítems del grid -->
    	  <article>Item 1</article>
    	  <article>Item 2</article>
    	  <article>Item 3</article>
    </section>

Si queremos activar la cuadrícula grid hay que habilitarla modificando el valor por defecto de la propiedad display y especificar el valor grid o inline-grid.

    section {
    		display: grid;
    }

Una vez definido esto podemos empezar a trabajar con nuestras cuadrículas.

## Grid con Filas y Columnas
Se puede establecer un tamaño fijo para la cuadrícula. Para ello podemos hacer uso de las propiedades CSS grid-template-columns y grid-template-rows, que sirven para indicar las dimensiones de cada celda de la cuadrícula, diferenciando entre columnas y filas.

Esto en código sería lo siguiente:

    section {
    		display: grid;
    	  grid-template-columns: 50px 300px;
    	  grid-template-rows: 200px 75px;
    }

El código anterior se traduce como que tendremos una cuadrícula con dos columnas (la primera con 50px de ancho y la segunda con 300px) y con dos filas (la primera con 200px de alto y la segunda con 75px).

![](https://static.platzi.com/media/user_upload/2-eaec82d5-e3da-457b-9626-23619dd03fdc.jpg)

## Grid con Filas y Columnas
Se puede establecer un tamaño fijo para la cuadrícula. Para ello podemos hacer uso de las propiedades CSS grid-template-columns y grid-template-rows, que sirven para indicar las dimensiones de cada celda de la cuadrícula, diferenciando entre columnas y filas.

Esto en código sería lo siguiente:

    section {
    		display: grid;
    	  grid-template-columns: 50px 300px;
    	  grid-template-rows: 200px 75px;
    }

El código anterior se traduce como que tendremos una cuadrícula con dos columnas (la primera con 50px de ancho y la segunda con 300px) y con dos filas (la primera con 200px de alto y la segunda con 75px).

![](https://static.platzi.com/media/user_upload/2-eaec82d5-e3da-457b-9626-23619dd03fdc.jpg)

## Unidad Fracción Restante

CSS Grid tiene una unidad especial llamada fr que simboliza una fracción de espacio restante en el grid. El uso de estas unidades puede reemplazar valores estáticos como los píxeles utilizados para definir nuestra grid anterior.

    section {
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-template-rows: 2fr 1fr;
    }

Con el código anterior se crea una cuadrícula de 2x2, donde el tamaño de ancho de la cuadrícula se divide en dos columnas (mismo tamaño de ancho para cada una), y el tamaño de alto de la cuadrícula se divide en dos filas, donde la primera ocupará el doble (2fr) que la segunda (1fr).

![](https://static.platzi.com/media/user_upload/3-e610ccbd-5e9b-441e-8d39-2fcf52462a38.jpg)

Ejemplo del uso de las proporciones obtenidas utilizando la unidad.
💡 Se pueden combinar varias unidades diferentes, pudiendo utilizar píxeles px y fracciones restantes fr, porcentajes % y fracciones restantes fr o combinaciones similares.

## Grid con Líneas Nombradas
Dentro de las opciones de grid se encuentra la posibilidad de usar linenames, o sea, ponerle nombre a las líneas de nuestro grid. Teniendo la siguiente estructura HTML como ejemplo.

    <!-- contenedor -->
    <div class="grid-template">
    		<!-- ítems del grid -->
    	  <header>Encabezado</header>
    	  <aside>Barra lateral</aside>
    	  <section>Contenido</section>
    		<footer>Footer</footer>
    </div>

Mediante Grid CSS podremos dar una estructura definida a la cuadrícula. Supongamos que tenemos una cuadrícula como la siguiente y definimos los nombres utilizando X para las posiciones en el eje X y Y para las posiciones en el eje Y.

![](https://static.platzi.com/media/user_upload/4-7547e35e-0612-49ee-a531-0f36f92310b2.jpg)

Cuadrícula de Grid CSS con nombres definidos.
Teniendo en cuenta lo definido en la imagen anterior lo que tenemos que hacer en nuestro código CSS será definir estos nombres entre corchetes, justo antes de la medida que estableceremos.

    div.grid-template {
    	  display: grid;
    	  grid-template-columns: [x0] 1fr [x1] 1fr [x2] 1fr [x3];
    	  grid-template-rows: [y0] 1fr [y1] 1fr [y2] 1fr [y3];
    }

Como podemos ver en el código anterior también se coloca un nombre de línea final sin medida a continuación que representa la línea final.
Con los nombres de cada línea definidos ahora sólo necesitamos delimitar que zonas del grid queremos que ocupe cada uno de nuestros bloques. Para eso se utilizan las propiedades grid-column-start, grid-column-end y grid-row-start, grid-row-end. También podríamos utilizar sus propiedades de atajo grid-column y grid-row.

    header {
    	  background: #1297FF;
    	  grid-column-start: x0;
    	  grid-column-end: x3;
    }
    
    aside {
    	  background: #C0C0C0;
    	  grid-row: y1 / y2;
    	  color: white;
    }
    
    section {
    	  background: #FF7E79;
    	  grid-column: x1 / x3;
    	  grid-row: y1 / y3;
    }
    
    footer {
    	  background: #73FA79;
    	  grid-column: x0 / x3;
    	  grid-row: y2;
    }

Debido al código anterior definimos que nuestro <header> abarca desde la columna x0 a x3, el <aside> desde la fila y1 a y2, el <section> desde la columna x1 a x3 y desde la fila y1 a y3 y por último el footer que va desde la columna x0 a x3 en la fila y2.
Esto se puede ver más claro en la siguiente imagen.

![](https://static.platzi.com/media/user_upload/5-7083c4c0-b5a6-4475-911d-08a566e894a6.jpg)

Distribución de las secciones en la cuadrícula definida anteriormente.
💡 Es necesario darle un tamaño de alto con height al contenedor padre para que el navegador sepa cuanto ocupará la estructura completa.

## Grid por Áreas

Es posible también gracias a los grids CSS se puede indicar el nombre y posición concreta de cada área de una cuadrícula, para esto se puede utilizar la propiedad grid-template-areas, donde se debe especificar el orden de las áreas en la cuadrícula. Posteriormente, en cada ítem hijo, se utiliza la propiedad grid-area para indicar el nombre del área del que se trata.

    <!-- contenedor -->
    <section class="grid-template">
    		<!-- ítems del grid -->
    	  <article class="a">Item 1</article>
    	  <article class="b">Item 2</article>
    	  <article class="c">Item 3</article>
    	  <article class="d">Item 4</article>
    </section>

Esta característica nos permite crear una cuadrícula altamente personalizada en apenas unas líneas de código como podemos ver a continuación:

    .grid {
    	  display: grid;
    	  grid-template-areas: "head head"
    	                       "menu main"
    	                       "foot foot";
    }
	
    .a { grid-area: head; background: #1297FF }
    .b { grid-area: menu; background: #FF7E79 }
    .c { grid-area: main; background: #009193 }
    .d { grid-area: foot; background: #929292 }

Con el código anterior podemos lograr una cuadrícula donde el Ítem 1 (head), ocuparía toda la parte superior, el 2 (menú), ocuparía el área izquierda del grid, debajo de la cabecera, el 3 (main), ocuparía el área derecha del grid, debajo de la cabecera y por último el 4 (foot) que ocuparía toda la zona inferior del grid.

![](https://static.platzi.com/media/user_upload/7-b304d4a6-d1e7-4b0c-9dd1-e6688f85b1c7.jpg)

Representación gráfica del resultado del template grid creado.
En esta propiedad en lugar de indicar el nombre del área a colocar, también podemos indicar una palabra clave especial:

- La palabra clave none indica que no se colocará ninguna celda en esta posición.
- Uno o más puntos . indica que se colocará una celda vacía en esta posición.

## Huecos en Grid

La cuadrícula por defecto tiene todas sus celdas pegadas a sus celdas contiguas. Aunque sería posible darle un margin a las celdas dentro del contenedor, existe una forma más apropiada que es hacer uso de las propiedades grid-column-gap y/o grid-row-gap.

    section {
    		grid-column-gap: 100px;
    	  grid-row-gap: 10px;
    }

Con esto, obtendríamos un resultado como el siguiente, indicando huecos entre columnas de 100px y huecos entre filas de 10px:

![](https://static.platzi.com/media/user_upload/8-a2e3d2a9-6ed9-484d-91c9-4890431e2c0a.jpg)
Representación gráfica de los huecos en la cuadrícula.

## Posición en el Grid
Así como tenemos propiedades para posicionar elementos en Flexbox estas propiedades también las tenemos en CSS grid y son las de justify-items y align-items. Estas propiedades se aplican sobre el elemento contenedor padre, pero afecta a los ítems hijos, por lo que actúan sobre la distribución de cada uno de los hijos.
También podemos utilizar las propiedades justify-content o align-content para modificar la distribución de todo el contenido en su conjunto, y no sólo de los ítems por separado.

    section {
    	  display: grid;
    		justify-items: end;
    		height: 200px;
    		align-items: center;
    }

## Ajuste Automático de Celdas
Es posible utilizar las propiedades grid-auto-columns y grid-auto-rows para darle un tamaño automático a las celdas de la cuadrícula. Para ello, sólo hay que especificar el tamaño deseado en cada una de las propiedades. Además, también podemos utilizar grid-auto-flow para indicar el flujo de elementos en una cuadrícula, y especificar por dónde se irán añadiendo.

Un ejemplo de como se insertarían los elementos en una cuadrícula de 2x2 utilizando grid-auto-flow por columnas o por filas

![](https://static.platzi.com/media/user_upload/9-1e53842c-bb87-4f58-b877-86050d44e3aa.jpg)
Uso del grid-auto-flow en una cuadrícula.

## Propiedades para Ítems Hijos
Hay propiedades especificas para los ítems hijos que por ejemplo permiten modificar la posición donde va a comenzar o terminar una fila o columna.
Estas propiedades son:

1. grid-column-start → Indica en que columna empezará el ítem de la cuadrícula.
2. grid-column-end → Indica en que columna terminará el ítem de la cuadrícula.
3. grid-row-start → Indica en que fila empezará el ítem de la cuadrícula.
4. grid-row-end → Indica en que fila terminará el ítem de la cuadrícula.

Estas propiedades nos permiten acomodar los ítems hijos a nuestro gusto dentro del elemento padre.

    select {
    		display: grid;
    }
    
    article .a {
    		grid-column-start: 2;
    		grid-column-end: 3:
    }

Con el código anterior le indicamos que los elementos con clase a iniciaran en la columna dos y terminará en la columna tres.

<h3>Atajo</h3>
Se puede combinar las propiedades de start y end tanto de las columnas como de las filas en una sola de la siguiente manera.

    article .a {
    		grid-column: 2 / 3;
    		grid-row: 1 / 4;
    }