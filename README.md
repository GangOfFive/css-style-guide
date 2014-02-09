**Tabla de Contenidos**

- [Estándares de (S)CSS para Gang of Five](#est%C3%A1ndares-de-scss-para-gang-of-five)
	- [Nombres de archivo](#nombres-de-archivo)
	- [IDs y Clases](#ids-y-clases)
	- [Formato](#formato)
	- [SCSS](#scss)

# Estándares de (S)CSS para *Gang of Five*

Se utilizará SCSS (Sass) para las hojas de estilo.

Esta guía está basada en [Google CSS style guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml#CSS_Style_Rules).

## Nombres de archivo
 - Se separan las palabras con guiones: `elephant.scss`, `original-name.scss`, y para los *partials* se antepone un guión bajo: `_ocean.scss`, `_banana-bread.css`.

## IDs y Clases
 - Se utilizarán nombres significativos o genéricos, dependiendo de lo que se ocupe hacer.
 
    ~~~css
    /* No recomendado: no se entiende */
    #yee-1901 {}
    
    /* No recomendado: presentacional */
    .button-green {}
    .clear {}
    /* Recomendado: específico */
    #gallery {}
    #login {}
    .video {}
    
    /* Recomendado: genérico */
    .aux {}
    .alt {}
    ~~~

 - Se deben utilizar nombres cortos siempre que sea posible. Utilizar abreviaciones está permitido.

## Formato
 - Se utilizarán minúsculas para atributos y valores.

    ~~~css
      /* No recomendado */
      color: #E5E5E5;
      /* Recomendado */
      color: #e5e5e5;
    ~~~

 - Se utilizará notación corta para las propiedades siempre que sea posible.

    ~~~css
    /* No recomendado */
    border-top-style: none;
    font-family: palatino, georgia, serif;
    font-size: 100%;
    line-height: 1.6;
    padding-bottom: 2em;
    padding-left: 1em;
    padding-right: 1em;
    padding-top: 0;
    /* Recomendado */
    border-top: 0;
    font: 100%/1.6 palatino, georgia, serif;
    padding: 0 1em 2em;
    ~~~
    
 - No se deben especificar unidades para valores que sean `0` al menos que sean requeridos.
    ~~~css
    margin: 0;
    padding: 0;
    ~~~

 - No es necesario poner `0` antes del `.` para valores o longitudes entre `-1` y `1`.

    ~~~css
    font-size: .8em;
    ~~~

 - Para los colores que lo permitan, la notación hexadecimal de 3 caracteres es preferida.

    ~~~css
    /* No recomendado */
    color: #eebbcc;
    /* Recomendado */
    color: #ebc;
    ~~~
 - Se debe utilizar un punto y coma después de cada declaración.

    ~~~css
    /* No recomendado */
    .test {
      display: block;
      height: 100px
    }
    /* Recomendado */
    .test {
      display: block;
      height: 100px;
    }
    ~~~
    
 - Siempre colocar un espacio entre la propiedad y el valor, (pero no entre el valor y el punto y coma).

    ~~~css
    /* No recomendado */
    h3 {
      font-weight:bold;
    }
    /* Recomendado */
    h3 {
      font-weight: bold;
    }
    ~~~

 - Utilizar siempre un espacio entre el último selector y el corchete que comienza el bloque
   de declaraciones. El corchete debería estar en la misma línea que el último selector de una regla.

    ~~~css
    /* No recomendado: falta el espacio */
    #video{
      margin-top: 1em;
    }
    
    /* No recomendado: salto de línea innecesario */
    #video
    {
      margin-top: 1em;
    }
    /* Recomendado */
    #video {
      margin-top: 1em;
    }
    ~~~
 - Utilizar comillas simples `''` en vez de dobles `""` para selectores de atributos o
   valores de propiedades. No utilizar comillas para valores de URI `url()`.

    ~~~css
    /* No recomendado */
    @import url("css/maia.css");
    
    html {
      font-family: "open sans", arial, sans-serif;
    }
    /* Recomendado */
    @import url(css/main.css);
    
    html {
      font-family: 'open sans', arial, sans-serif;
    }
    ~~~
    
## SCSS

Los siguientes son estándares específicos para SCSS. Basadas en: http://css-tricks.com/sass-style-guide/.
 - No agregar archivos CSS al control de versines.
   Compilar los archivos de SCSS es parte del proceso de desplegamiento.
 
 - Utilizar variables siempre que tenga sentido.
    
    ~~~scss
    $zHeader: 2000;
    $zOverlay: 5000;
    $zMessage: 5050;
    $headerBg: #f00;
    $messageText: #000;
    
    .header {
      z-index: $zHeader;
      background-color: $headerBg;
    }
    .overlay {
      z-index: $zOverlay;
    }
    .message {
      z-index: $zMessage;
      color: $messageText;
    }
    ~~~
 
 - Listar reglas `@extends` primero.
 - Listar reglas `@includes` después.
 - Listar reglas "normales" después.
 - Listar los selectores anidados de último.
    
    ~~~scss
    .weather {
      @extends %module; 
      @include transition(all 0.3s ease); // Recomendado
      background: LightCyan;
      > h3 {
        @include transform(rotate(90deg));
        border-bottom: 1px solid white;
      }
    }
    ~~~

 - Ser generoso con los comentarios.

 - Prefirir utilizar muchos archivos pequeños.

    ~~~scss
    @import "global/header/header/";
    @import "global/header/logo/";
    @import "global/header/dropdowns/";
    @import "global/header/nav/";
    @import "global/header/really-specific-thingy/";
    ~~~

 - Evitar especificar demasiado los selectores:
   https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Writing_efficient_CSS

     ~~~scss
	// No recomendado
	button#backButton {…}
	// No recomendado
	.menu-left#newMenuIcon {…}
	// Recomendado
	#backButton {…}
	// Recomendado
	#newMenuIcon {…}
    ~~~
