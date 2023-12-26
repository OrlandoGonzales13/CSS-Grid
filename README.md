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


