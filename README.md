# Curso HTML & CSS

Por: [supersimple.dev](https://supersimple.dev/courses/html-css-course)

Video: https://youtu.be/G3e-cpL7ofc

Referencia: [HTML + CSS](https://supersimpledev.github.io/references/html-css-reference.pdf)

## 1. HTML básico

- Elementos HTML
- Atributos HTML
- Curiosidades

### Elementos HTML

![elemento-HTML](./public/grumpy-cat-small.png)

Reglas de sintaxis de un elemento: cada **elemento HTML** generalmente consiste de un **contenido** y dos **etiquetas HTML** que lo rodean: una _etiqueta de apertura_ y una _etiqueta de cierre_. La _etiqueta de cierre_ incluye un _slash (/)_ antes del nombre de la etiqueta.

```html
<button>Texto</button>
```

- etiqueta de apertura: `<>`
- etiqueta de cierre: `</>`
- nombre del elemento: `button`
- contenido: `Texto`

> Elementos HTML vistos: `<p>` y `<button>`

### Atributos HTML

Un **atributo** _modifica el comportamiento_ de un **elemento**. Generalmento un atributo funciona dentro de un elemento en particular.

Reglas de sintaxis de un atributo: debemos tener un **espacio** entre el **nombre del elemento** y el **nombre del atributo**, luego un **signo de asignación** (`=`) y luego un **par de comillas dobles** que encierren el **valor del atributo**. Podemos tener múltiples atributos dentro de un elemento HTML.

```html
<a href="https://www.youtube.com/" target="_blank">Enlace a Youtube</a>
```

- etiqueta de apertura: `<>`
- etiqueta de cierre: `</>`
- nombre del elemento: `a`
- contenido: `Enlace a Youtube`
- nombre del atributo 1: `href`
- valor del atributo 1: `https://www.youtube.com/`
- nombre del atributo 2: `target`
- valor del atributo 1: `_blank`

> Elementos HTML vistos: `<a>`<br>
Atributos HTML vistos: `href` y `target`

### Curiosidades de HTML

- Los espacios extra son ignorados.
- Las líneas extra también son ignoradas.
- La indentación es usada para mejorar la lectura del código. VSCode usa 4 espacios para la indentación de HTML. Pero generalmente en HTML y CSS se usa 2 espacios para la indentación.

> VSCode: settings > tabsize > 2

## 2. CSS básico

CSS trabaja el **estilo**, por lo tanto **cambia la apariencia de los elementos HTML**.

[Página de referencia de diseño de los ejemplos](https://supersimple.dev/exercises/buttons)


Reglas de sintaxis en CSS: cada **elemento HTML** generalmente consiste de un **contenido** y dos **etiquetas HTML** que lo rodean: una _etiqueta de apertura_ y una _etiqueta de cierre_. La _etiqueta de cierre_ incluye un _slash (/)_ antes del nombre de la etiqueta.

```css
button {
  background-color: red;
}

<button>SUBSCRIBE</button>
```

- selector CSS: `button`
- llaves que continen estilos del selector CSS indicado: `{}`
- estilo CSS: `background-color: red;`
- propiedad CSS: `background-color`
- valor CSS: `red`

El **selector CSS** indica cual el es elemeto HTML de la página al que apuntamos. La **propiedad CSS** indica qué aspecto de la apariencia queremos modificar. El **valor CSS** indica el valor que debe cambiar la propiedad CSS. El signo `:` sirve para  separar la **propiedad CSS** del **valor CSS** y el signo `;`  indica la finalización del **estilo**.

> Elementos HTML vistos: `<style>`<br>
Propiedades CSS vistas: `background-color`

### Otras propiedades CSS:

Tomemos de referencencia la siguiente página: https://supersimple.dev/exercises/buttons

Técnica general:

1. Creamos el botón con HTML.
2. Estilizamos con CSS regla por regla.

```css
<style>
  button {
    background-color: rgb(212, 42, 42);
    color: white;
    border: none;
    height: 36px;
    width: 108px;
    border-radius: 2px;
    cursor: pointer;
  }
</style>

<button>SUBSCRIBE</button>
```

> Propiedades CSS vistas: `color`, `border`, `height`, `width`, `border-radius` y `cursor`.

### Elemento HTML `<class>`

```css
<style>
  .subscribe-button {
    background-color: rgb(212, 42, 42);
    color: white;
    border: none;
    height: 36px;
    width: 108px;
    border-radius: 2px;
    cursor: pointer;
    margin-right: 8px;
  }

  .join-button {
    background-color: white;
    border-color: rgb(7, 74, 199);
    border-style: solid;
    border-width: 1px;
    color: rgb(7, 74, 199);
    height: 36px;
    width: 62px;
    border-radius: 2px;
    cursor: pointer;
  }

  .tweet-button {
    background-color: rgb(20, 153, 230);
    color: white;
    border: none;
    height: 36px;
    width: 74px;
    border-radius: 18px;
    font-weight: bold;
    font-size: 15px;
    cursor: pointer;
    margin-left: 8px;
  }
</style>

<button class="subscribe-button">SUBSCRIBE</button>
<button class="join-button">JOIN</button>
<button class="tweet-button">Tweet</button>
```

> Elementos HTML vistos: `<class>`<br>
Propiedades CSS vistas: `margin-right`, `margin-left`, `border-color`, `border-style`, `border-width`, `font-weight` y `font-size`.

## 3. Pseudo-clases, transitions, sombras

### Pseudo-clases (`hover` y `active`)

Tomemos de referencencia la siguiente página: https://supersimple.dev/exercises/buttons

Tanto `hover` como `active` son considerados **pseudo-clases** las cuales agregan estilos extra a los ya determinados por el selector inicial en una cierta _situación_, por ejemplo cuando nos posicionamos sobre el botón (`hover`) o cuando hacemos clic en dicho botón (`active`).

```css
<style>
  .subscribe-button {
    background-color: rgb(212, 42, 42);
    color: white;
    border: none;
    height: 36px;
    width: 108px;
    border-radius: 2px;
    cursor: pointer;
    margin-right: 8px;
  }

  .subscribe-button:hover {
    background-color: orange;
  }

  .subscribe-button:active {
    background-color: green;
  }
</style>

<button class="subscribe-button">SUBSCRIBE</button>
```

Tomemos de referencencia la siguiente página: https://supersimple.dev/exercises/buttons

Agreguemos las pseudo-clases hover y active y usemos la propiedad CSS `opacity`. El rango de valores de `opacity` va desde `0` a `1`.

```css
.subscribe-button {
    background-color: rgb(212, 42, 42);
    color: white;
    border: none;
    height: 36px;
    width: 108px;
    border-radius: 2px;
    cursor: pointer;
    margin-right: 8px;
  }

  .subscribe-button:hover {
    opacity: 0.8;
  }

  .subscribe-button:active {
    opacity: 0.4;
  }

  .join-button {
    background-color: white;
    border-color: rgb(7, 74, 199);
    border-style: solid;
    border-width: 1px;
    color: rgb(7, 74, 199);
    height: 36px;
    width: 62px;
    border-radius: 2px;
    cursor: pointer;
  }

  .join-button:hover {
    background-color: rgb(7, 74, 199);
    color: white;
  }

  .join-button:active {
    opacity: 0.7;
  }
```

> Elementos HTML vistos: pseudoclases `hover` y `active`<br>
Propiedades CSS vistas: `opacity`

### Transiciones simples

Las transiciones nos permiten generar animaciones desde un valor de un estilo CSS a otro valor en un tiempo determinado. 

La propiedad CSS `transition` espera dos valores: el primero se refiere a la propiedad a transicionar y el segundo en cuánto tiempo lo realizará en segundos. Y es muy importante que siempre la ubiquemos dentro del selector base (en nuestro caso `.subscribe-button`) y no dentro de una pseudo-clase.

```css
<style>
  .subscribe-button {
    background-color: rgb(212, 42, 42);
    color: white;
    border: none;
    height: 36px;
    width: 108px;
    border-radius: 2px;
    cursor: pointer;
    margin-right: 8px;
    transition: opacity 0.15s;
    }

  .subscribe-button:hover {
    opacity: 0.8;
  }

  .subscribe-button:active {
    opacity: 0.4;
  }
</style>

<button class="subscribe-button">SUBSCRIBE</button>
```

### Transiciones múltiples

Otro ejemplo donde queremos transicionar más de una propiedad CSS utilizando una coma (`,`):

```css
<style>
  .join-button {
      background-color: white;
      border-color: rgb(7, 74, 199);
      border-style: solid;
      border-width: 1px;
      color: rgb(7, 74, 199);
      height: 36px;
      width: 62px;
      border-radius: 2px;
      cursor: pointer;
      transition: background-color 0.15s, color 0.15s;
    }

    .join-button:hover {
      background-color: rgb(7, 74, 199);
      color: white;
    }

    .join-button:active {
      opacity: 0.7;
    }
</style>

<button class="join-button">JOIN</button>
```

> Propiedades CSS vistas: múltiple `transition` usando (`,`).

### Sombras

Generalmente usamos la propiedad CSS `box-shadow` para generar sombras. La propiedad espera cuatro valores que representan: posiciónX, posiciónY, tamañoSombra y color.

```css
<style>
  .tweet-button {
    background-color: rgb(20, 153, 230);
    color: white;
    border: none;
    height: 36px;
    width: 74px;
    border-radius: 18px;
    font-weight: bold;
    font-size: 15px;
    cursor: pointer;
    margin-left: 8px;
    transition: box-shadow 0.15s;
  }

  .tweet-button:hover {
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.15);
  }
</style>

<button class="tweet-button">Tweet</button>
```

> Propiedades CSS vistas: `box-shadow`

## 4. Chrome DevTools y Modelo de Caja CSS

### Chrome DevTools

Para acceder a la **DevTools** de Chrome, hacer clic con el botón derecho en un lugar vacío de la página y seleccionar `Inspeccionar`.

Veamos los siguientes elementos:

1. Pestaña `Elements`.
2. Herramienta `Select an element in the page to inspect it`
3. Pestaña `Styles`.

    Ver cómo se escriben los colores en notación hexadecimal.

4. Pestaña `Computed`.

    Buscar los `background-color` exactos y copiarlos en el archivo `buttons.html`.

### Modelo de Caja CSS

Usar `width` y `height` no resulta una buena implementación en botones ya que si modificamos el texto, este no se adaptará al tamaño prefijado.

Por lo tanto se recomiendo usar `padding` en vez de `width` y `height`.
```
m | b | p | texto | p | b | m |

m: margin
b: border
p: padding
```

## 5. Estilos de texto

### Propiedades de fuente y texto básicos

```css
<style>
  .estilo1 {
    font-family: Arial;
    font-size: 30px;
    font-weight: bold;
    font-style: italic;
    text-align: center;
  }
</style>

<p class="estilo1">Este es el texto del párrafo.</p>
```

> Propiedades CSS vistas: `font-family`, `font-size`, `font-weight`, `font-style`, `text-align`

### Primer ejercicio

Tomemos de referencencia la siguiente página: https://supersimple.dev/exercises/text

Técnica general:

1. Creamos el botón con HTML.
2. Estilizamos con CSS regla por regla.

> **Recordemos que:** para obtener el valor de alguna _propiedad CSS_, es conveniente utilizar el **Inspector** del _DevTools_, seleccionar el **elemento HTML** que deseamos analizar y tener activa la pestaña **Computed** para obtener la **propiedad CSS** y el **valor** que desamos obtener.

#### Entidad HTML

Para incorporar un elemento gráfico como el punto medio `·` utilizaremos lo que se denomina **entidad HTML**.

En un buscador escribiremos `html entity middle dot` y copiaremos el código HTML correspondiente: `&#183;`. Si bien es posible copiar y pegar dicha entidad, se recomienda usar el código HTML por cuestiones de compatibilidad de navegadores.

Luego usaremos esta otra entidad `✓` denominada `checkmark`, por lo tanto la buscaremos como `html entity checkmark`. Su código HTML es: `&#10003;`.

Por último buscaremos esta otra entidad `>` denominada `greater than`, por lo tanto la buscaremos como `html entity greater than`.

Siempre es referible escribir el **código HTML** para ingresar una entidad HTML (por ej.: `&#62;`), que usar el **nombre** de la entidad HTML (por ej.: `&gt;`) ya que el navegador puede llegar a no reconocer nombres de identidades y es más seguro usar entonces el **código HTML**.

#### Márgenes en textos

> Los párrafos por defecto vienen con un margen superior e inferior de 14px.

#### Código resultante

```css
<style>
  .video-title {
    font-family: Arial;
    font-weight: bold;
    font-size: 18px;
    width: 280;
    line-height: 24px;
    margin-bottom: 5px;
  }

  .video-stats {
    font-family: Arial;
    font-size: 14px;
    color: rgb(96, 96, 96);
    margin-top: 0px;
    margin-bottom: 20px;
  }

  .video-author {
    font-family: Arial;
    font-size: 14px;
    color: rgb(96, 96, 96);
    margin-top: 0px;
    margin-bottom: 20px;
  }

  .video-description {
    font-family: Arial;
    font-size: 14px;
    color: rgb(96, 96, 96);
    width: 280px;
    line-height: 22px;
    margin-top: 0px;
  }
</style>

<p class="video-title">Talking Tech and AI with Google CEO Sundar Pichai!</p>

<p class="video-stats">3.4M views &#183; 6 months ago</p>

<p class="video-author">Marques Brownlee &#10003;</p>

<p class="video-description">
  Talking tech and AI on the heels of Google I/O. Also a daily driver phone
  reveal from Google's CEO. Shoutout to Sundar!
</p>
```

> Propiedades CSS vistas: `line-height`.

### Refactorización en CSS

Refactorizar CSS significa reorganizar y mejorar el código CSS existente sin alterar el aspecto visual del sitio web o aplicación.

Al igual que en otros lenguajes de programación, el objetivo principal es hacer que el código sea más limpio, fácil de mantener y más eficiente.

Aquí hay algunas actividades comunes en la refactorización de CSS:

1. **Eliminación de código redundante:** Identificar y eliminar reglas CSS duplicadas o innecesarias.
2. **Optimización de selectores:** Simplificar y optimizar selectores CSS para mejorar el rendimiento y la legibilidad.
3. **Uso de variables y mixins:** Utilizar variables y mixins (especialmente en preprocesadores CSS como SASS o LESS) para evitar la repetición y hacer que el código sea más fácil de actualizar.
4. **Modularización:** Dividir el CSS en archivos más pequeños y específicos para diferentes componentes o secciones del sitio, en lugar de tener un solo archivo CSS grande y monolítico.
5. **Adopción de convenciones de nombres consistentes:** Seguir una convención de nombres consistente, como BEM (Block Element Modifier), para mejorar la claridad y previsibilidad del código.
6. **Eliminación de estilos inline:** Mover estilos inline a archivos CSS externos para mantener la separación de contenido y presentación.
7. **Revisión de la especificidad:** Asegurarse de que la especificidad de los selectores CSS sea adecuada y no excesivamente alta, lo que puede hacer que el código sea difícil de mantener.
8. **Optimización de media queries:** Agrupar y organizar media queries para evitar duplicación y mejorar la legibilidad.

Refactorizar CSS puede mejorar significativamente la velocidad de desarrollo, reducir errores y hacer que el mantenimiento futuro sea más fácil y eficiente.

También puede contribuir a mejorar el rendimiento del sitio web, ya que el código CSS más limpio y optimizado se carga y se procesa más rápidamente.

#### Especificidad (CSS specificity)

El **selector** que sea **más específico** tiene una **prioridad más alta**.

Es decir:

```
selector de nombre de clase > selector de nombre de elemento
```

Referencias:

- https://www.w3schools.com/css/css_specificity.asp
- https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity
- https://developer.mozilla.org/es/docs/Web/CSS/Specificity
- https://www.w3.org/TR/selectors-4/
- [CSS Specificity Calculator](https://specificity.keegan.st/)

#### Código resultante

```css
<style>
  p {
    font-family: Arial;
    margin-top: 0;
    margin-bottom: 0;
  }

  .video-title {
    font-weight: bold;
    font-size: 18px;
    width: 280;
    line-height: 24px;
    margin-bottom: 5px;
  }

  .video-stats {
    font-size: 14px;
    color: rgb(96, 96, 96);
    margin-bottom: 20px;
  }

  .video-author {
    font-size: 14px;
    color: rgb(96, 96, 96);
    margin-bottom: 20px;
  }

  .video-description {
    font-size: 14px;
    color: rgb(96, 96, 96);
    width: 280px;
    line-height: 22px;
  }
</style>

<p class="video-title">Talking Tech and AI with Google CEO Sundar Pichai!</p>

<p class="video-stats">3.4M views &#183; 6 months ago</p>

<p class="video-author">Marques Brownlee &#10003;</p>

<p class="video-description">
  Talking tech and AI on the heels of Google I/O. Also a daily driver phone
  reveal from Google's CEO. Shoutout to Sundar!
</p>
```

### Elementos de texto `<strong>`, `<em>`, y `<span>`

Los **elementos de texto** existen dentro de una línea de texto y modifican sólo esa parte de la linea de texto. Algunos muy usados son `<strong>`, `<em>`, y `<span>`.

`<span>` es un elemento de texto que no contiene estilos por defecto. Se usa para agregarle estilos a un fragmento de un texto dentro de un párrafo.

```css
<style>
  .highlight {
    text-decoration: underline;
    background-color: yellow;
  }
</style>

<p>
  En este texto hay una palabra <strong>resaltada</strong>, otra tiene <em>énfasis</em> y las demás son normales. Pero hay casos donde queremos que <span class="highlight">sólo una parte</span> tenga un estilo particular.
</p>
```

> Elementos HTML vistos: `<strong>`, `<em>` y `<span>`

#### Actualicemos el ejercicio con el agregado del último párrafo

```css
<style>
  p {
    font-family: Arial;
    margin-top: 0;
    margin-bottom: 0;
  }

  .video-title {
    font-weight: bold;
    font-size: 18px;
    width: 280;
    line-height: 24px;
    margin-bottom: 5px;
  }

  .video-stats {
    font-size: 14px;
    color: rgb(96, 96, 96);
    margin-bottom: 20px;
  }

  .video-author {
    font-size: 14px;
    color: rgb(96, 96, 96);
    margin-bottom: 20px;
  }

  .video-description {
    font-size: 14px;
    color: rgb(96, 96, 96);
    width: 280px;
    line-height: 22px;
    margin-bottom: 100px;
  }

  .apple-text {
    background-color: rgb(227, 65, 64);
    color: white;
    font-size: 14px;
    text-align: center;
    padding: 16px;
    margin-top: 0;
    margin-bottom: 16px;
    margin-left: 8px;
    margin-right: 8px;
  }

  .shop-link:hover {
    text-decoration: underline;
    cursor: pointer;
  }
</style>

<p class="video-title">Talking Tech and AI with Google CEO Sundar Pichai!</p>

<p class="video-stats">3.4M views &#183; 6 months ago</p>

<p class="video-author">Marques Brownlee &#10003;</p>

<p class="video-description">
  Talking tech and AI on the heels of Google I/O. Also a daily driver phone
  reveal from Google's CEO. Shoutout to Sundar!
</p>

<p class="apple-text">
  Shop early for the best selection of holiday favourites.
  <span class="shop-link">Shop now &#62;</span>
</p>
```

## 6. La estructura HTML

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body></body>
</html>
```

Toda estructura HTML contiene cuatro componentes: una instrucción y 3 elementos:

- `<!DOCTYPE html>` no es una etiqueta sino una instrucción para el navegador que le indica que está por acceder a un documento elaborado en **HTML5** (en modo estándar).
- `<html></html>` corresponde al elemento HTML. Este representa toda la página web.
- `<head></head>` corresponde al elemento HEAD. Este elemento debe contener todos los elementos que **no** son visibles dentro de una página web.
- `<body></body>` corresponde al elemento BODY. Este elemento debe contener todos los elementos que son **sí** son visibles dentro de una página web.

Podemos observar que dentro de la estructura HTML tenemos algunos elementos (`<head>` y `<body>`) dentro de otro elemento (`<html>`). A esto se lo denomina **anidación** (_nesting_).

### Ejercicio 1

1. Tomemos el archivo `website.html` y escribamos los componentes de la estructura HTML.
2. Tomemos los tres elementos e incorporémolos dentro de la etiqueta `<body>`.
3. Añadamos la etiqueta `<title>` dentro de `<head>`.

Resultado:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Mi primer sitio web</title>
  </head>
  <body>
    <button>Clic aquí</button>
    <p>Este es el texto del primer párrafo.</p>
    <a href="https://www.youtube.com/" target="_blank">Enlace a Youtube</a>
  </body>
</html>
```

### Ejercicio 2: botones

Ahora hagamos lo mismo con el archivo `buttons.html`

Resultado:

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      .subscribe-button {
        background-color: rgb(212, 42, 42);
        color: white;
        border: none;
        height: 36px;
        width: 108px;
        border-radius: 2px;
        cursor: pointer;
        margin-right: 8px;
        transition: opacity 0.15s;
      }

      .subscribe-button:hover {
        opacity: 0.8;
      }

      .subscribe-button:active {
        opacity: 0.4;
      }

      .join-button {
        background-color: white;
        border-color: rgb(7, 74, 199);
        border-style: solid;
        border-width: 1px;
        color: rgb(7, 74, 199);
        height: 36px;
        width: 62px;
        border-radius: 2px;
        cursor: pointer;
        transition: background-color 0.15s, color 0.15s;
      }

      .join-button:hover {
        background-color: rgb(7, 74, 199);
        color: white;
      }

      .join-button:active {
        opacity: 0.7;
      }

      .tweet-button {
        background-color: rgb(20, 153, 230);
        color: white;
        border: none;
        height: 36px;
        width: 74px;
        border-radius: 18px;
        font-weight: bold;
        font-size: 15px;
        cursor: pointer;
        margin-left: 8px;
        transition: box-shadow 0.15s;
      }

      .tweet-button:hover {
        box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.15);
      }
    </style>
  </head>
  <body>
    <button class="subscribe-button">SUBSCRIBE</button>
    <button class="join-button">JOIN</button>
    <button class="tweet-button">Tweet</button>
  </body>
</html>
```

### Código CSS como archivo externo - parte 1

Como podemos ver, la longitud del archivo comienza a ser demasiado extensa, por lo tanto vamos a usar la capacidad de modularizar el contenido en dos archivos: uno `html` y otro `css`.

Para esto utilizaremos el elemento especial `<link>`. **Link** es tipo de elemento denominado **elemento vacío** ya que no requiere de contenido y por lo tanto no necesita de una etiqueta de cierre. Espera dos atributos:

- `rel`: indica la _relación_ del documento enlazado con el actual. En este caso le diremos que se trata de una hoja de estilo: `stylesheet`.
- `href`: especifica la URL del recurso enlazado. La _ruta de archivo_ debe ser absoluta o relativa. En este caso le diremos que se trata de una hoja de estilo: `buttons.css`

Resultado:

```html
<!-- buttons.html -->
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="buttons.css" />
  </head>
  <body>
    <button class="subscribe-button">SUBSCRIBE</button>
    <button class="join-button">JOIN</button>
    <button class="tweet-button">Tweet</button>
  </body>
</html>
```

```css
/* buttons.css */
.subscribe-button {
  background-color: rgb(212, 42, 42);
  color: white;
  border: none;
  height: 36px;
  width: 108px;
  border-radius: 2px;
  cursor: pointer;
  margin-right: 8px;
  transition: opacity 0.15s;
}

.subscribe-button:hover {
  opacity: 0.8;
}

.subscribe-button:active {
  opacity: 0.4;
}

.join-button {
  background-color: white;
  border-color: rgb(7, 74, 199);
  border-style: solid;
  border-width: 1px;
  color: rgb(7, 74, 199);
  height: 36px;
  width: 62px;
  border-radius: 2px;
  cursor: pointer;
  transition: background-color 0.15s, color 0.15s;
}

.join-button:hover {
  background-color: rgb(7, 74, 199);
  color: white;
}

.join-button:active {
  opacity: 0.7;
}

.tweet-button {
  background-color: rgb(20, 153, 230);
  color: white;
  border: none;
  height: 36px;
  width: 74px;
  border-radius: 18px;
  font-weight: bold;
  font-size: 15px;
  cursor: pointer;
  margin-left: 8px;
  transition: box-shadow 0.15s;
}

.tweet-button:hover {
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.15);
}
```

### Código CSS como archivo externo - parte 2

Para mayor comodidad y organización a la hora de desarrollar se suelen usar carpetas donde guardar los archivos CSS. Para esto debemos crear una carpeta `styles` y mover allí el archivo CSS y luego moddificar la etiqueta <link> de la siguiente manera: `<link rel="stylesheet" href="styles/buttons.css" />`

### Ejercicio 3: texto

Hagamos lo mismo que con el ejercicio 2 pero con el archivo `text.html`.

### Incorporación de otras fuentes tipográficas

Por defecto podemos usar Arial y Times New Roman, ¿pero cómo podemos hacer para usar otras fuentes de internet?

1. Busquemos en Google la siguiente frase: `google fonts`  y vayamos al enlace que diga `Google Fonts: Browse Fonts`.
2. Ahora busquemos y seleccionemos la fuente `Roboto`. 
3. En este paso tomamos 2 estilos : `Regular 400` y `Bold 700`.
4. Copiamos los enlaces de dichos estilos bajo la opción `link` y los pegamos en nuestra página `text.html`, dentro de la etiqueta `head`, entre `title` y `link`:

    ```html
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    ```

5. Por último modificamos la línea CSS en donde se especificaba la familia de fuentes **Arial** y la cambiamos por **Roboto**: ```font-family: Roboto;```

## 7. Imágenes y cajas de texto

En este capítulo iniciaremos el _trabajo práctico_ **Youtube**. La referencia la podemos encontrar en:

https://supersimple.dev/exercises/youtube

