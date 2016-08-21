---
layout: post
title:  "Nunki Core [Theme Options for WordPress]"
date: 2016-05-23
excerpt: ""
project: true
feature: assets/img/nunkicore/featurenunkicore.png
tag:
- GNU/Linux
- Commands
- Cheat Sheet
comments: true
version: "1.0v"
license: "GPL v3"
---

# Descripción / Descipció / Desciption

**[ES]**    **Nunki Core** es un ***Theme Options*** libre. Basado en [**Options Framework**](https://github.com/devinsays/options-framework-plugin) **Nunki Core** permite crear configuraciones en plantillas de WordPress permitiendo al usuario configurar el tema que hemos desarrollado a su gusto. **Nunki Core** es libre y puede ser utilizado en proyectos comerciales y personales.

**[CA]**    **Nunki Core** és un ***Theme Options*** lliure. Basat en [**Options Framework**](https://github.com/devinsays/options-framework-plugin) **Nunki Core** permet crear configuracions en plantilles de WordPress permetent a l'usuari configurar el tema que hem desenvolupat al seu gust. **Nunki Core** és lliure i pot ser utilitzar en projectes comercials i personals.

**[EN]**    Nunki Core it's a Free Theme Options. Based on [**Options Framework**](https://github.com/devinsays/options-framework-plugin) Nunki Core allows you to create configurations on WordPress Themes, allowing to set the theme that we have developed on the taste of each user. It's free to use in both commercial and personal projects.


# Características / Caracteristiques / Features

**[ES]**

+ Configurar encabezado.
+ Activa/Desactiva diferentes servicios (Subir arriba, Lo más visto, Compartir redes sociales...).
+ Configurar ***Infinite Scroll*** de manera sencilla.
+ Posición de la barra lateral.
+ 7 estilos diferentes (Rojo, Verde, Amarillo, Azul, Lila, Agua y naranja)
+ Configura fondo del tema.
+ Añadir **favicon** fácilmente.
+ Configura tipografía (En desarrollo).
+ Añadir licencia a tu contenido fácilmente.
+ Configura el pie de página (añade tu **copyrigth** y tus redes sociales).
+ Añadir códigos de publicidad de Google o de Google Analytics y Piwik Analytics.
+ Entre muchos otros...

**[CA]**

+ Configurar encapçalament.
+ Activa/Desactiva diferents serveis (Pujar a dalt, El més vist, Compartir xarxes socials...).
+ Configurar ***Infinite Scroll*** de manera senzilla.
+ Posició de la barra lateral.
+ 7 estils diferents (Vermell, Verd, Groc, Blau, Lila, Aigua i Taronja)
+ Configurar fons del tema.
+ Afegir **favicon** fàcilment.
+ Configura tipografia (En desenvolupament).
+ Afegir llicència al teu contingut fàcilment.
+ Configura el peu de pàgina (afegeix el **copyrigth** i les teves xarxes socials).
+ Afegir codis de publicitat de Google o de Google Analytics i Piwik Analytics.
+ Entre molts d'altres...

**[EN]**

+ Set header of the page.
+ Enable / Disable various services (To top, Most viewed, Social sharing ...).
+ Set ***Infinite Scroll*** easily.
+ Position of the sidebar.
+ 7 different styles (Red, Green, Yellow, Blue, Purple, Water and Orange)
+ Set background of the template.
+ Add **favicon** easily.
+ Set typography (in development).
+ Add license your content easily.
+ Set the footer (add your **copyrigth** and your social networks).
+ Add advertising codes Google or Google Analytics and Piwik Analytics.
+ As well as many others...

# Cómo funciona Nunki Core / Com funciona Nunki Core / How it works Nunki Core

**[ES]**

**Nunki Core** está basado en [**Options Framework**](https://github.com/devinsays/options-framework-plugin) y su funcionamiento es muy similar. A diferencia de **Options Framework**, **Nunki Core** tiene integrado una serie de funciones que permiten utilizarlas dentro de nuestro tema.

```php
<?php nc_NameFunction(); ?>
```

**[CA]**

**Nunki Core** està basat en [**Options Framework**](https://github.com/devinsays/options-framework-plugin) i el seu funcionament és molt similar. A diferència de **Options Framework**, **Nunki Core** té integrat una sèrie de funcions que permeten utilitzar-les dins del nostre tema.

```php
<?php nc_NameFunction(); ?>
```

**[EN]**

**Nunki Core** is based on [**Options Framework**](https://github.com/devinsays/options-framework-plugin) and it's operation is very similar. Unlike **Framework Options** **Core Nunki** has integrated a number of features to use within our theme.

# Opciones

***(Only Spanish, sorry. Look the documentation on [English](zagur.github.io))***

A continuación se explica todas las configuraciones que hay actualmente en **Nunki Core** de manera ordenada por secciones, como se muestra en el panel de configuración de **Nunki Core**.

## SLIDER

Si en tu tema quieres incluír un slider, puedes hacerlo con esta función:

```php
<?php nc_slider(); ?>
```

Una vez marques la opción en el panel de **Nunki Core** aparecerán otras opciones tales como:

+ Selecciona la categoría a mostrar en el slider
+ Número de entradas a mostrar
+ Intervalo entre diapositivas
+ Pausar Slider

El Slider que se muestra es el slider propio de Bootstrap

## Header

En esta pestaña podremos configurar todo lo relacionado con la cabezera de la

## Configuración bàsica

En este apartado podremos configurar

<dl>
    <dt>Activar aviso cookies - <i>nc_cookiesMessage()</i></dt>
    <dd>Si se activa esta función aparecerá un triángulo en la parte inferior derecha avisando al visitante de que la web utiliza cookies propias para mejorar los servicios.</dd>
</dl>

```php
function nc_cookiesMessage() {
    $stateCheckboxCookies = of_get_option('cookies');
    if ($stateCheckboxCookies == 1) {
        echo '<div class="cookies" ondblclick="cerrarCookie(this);"><span id="cookie" tabindex="0" class="glyphicon glyphicon-cog" data-container="body" data-toggle="popover" data-trigger="focus" data-placement="left" data-content="Utilizamos cookies propias y de terceros para mejorar nuestros servicios. Si continúa navegando, consideramos que acepta su uso. Doble clic sobre el triángulo rojo para cerrar."></span></div>';
    }
}
```

<dl>
    <dt>Activar Breadcrumbs - <i>nc_breadcrumb()</i></dt>
    <dd>Si se activa esta función debajo del título principal de la entrada aparecerán los <i>Breadcrumbs</i> para indicar en que zona de la web está el usuario.</dd>
</dl>

```php
function nc_breadcrumb() {
    $stateCheckboxBreadCrumb = of_get_option('breadcrumb');
    if ($stateCheckboxBreadCrumb == 1) {
        if (!is_home()) {
            echo '<span class="glyphicon glyphicon-home"></span>';
            echo '<span> ';
            bloginfo('name');
            echo '</span> <span class="fa fa-angle-right"></span> ';
            if (is_category() || is_single()) {
                the_category('title_li=');
                if (is_single()) {
                    echo ' <span class="fa fa-angle-right"></span> ';
                    the_title();
                }
            } elseif (is_page()) {
                echo the_title();
            }
        }
    }
}
```

<dl>
    <dt>Activar "Subir arriba" - <i>nc_toTopPage()</i></dt>
    <dd>Si se activa esta función en la parte inferior de la pàgina (zona footer secundario) aparecerá una flecha para subir hacía arriba. Esta opción solo aparece en entradas y páginas.</dd>
</dl>

```php
function nc_toTopPage() {
    $stateCheckBoxToTop = of_get_option('totop');
    if ($stateCheckBoxToTop == 1) {
        echo '<a id="backtotop" href="#" onclick="toTopEffect();return false"><span class="glyphicon glyphicon-chevron-up"></span></a>';
    }
}
```

<dl>
    <dt>Activar "Infinite Scroll" - <i>nc_infiniteScroll()</i></dt>
    <dd>*EN DESARROLLO*</dd>
</dl>

```php
function nc_infiniteScroll() {
    // code
}
```

<dl>
    <dt>Activar "Lo más visto" - <i>nc_relatedPosts()</i></dt>
    <dd>Añade una lista en la parte superior de la entrada relacionadas con la entrada.</dd>
</dl>

```php
function nc_relatedPosts() {
    $stateCheckTrendingArticles = of_get_option('relatedPost');
    if ($stateCheckTrendingArticles == 1) {
        echo '<div class="trending-articles">';
        echo '<ul>';
        echo '<li class="firstlink">Lo más visitado: </li>';
        echo popularPosts();
        echo '</ul>';
        echo '</div>';
    }
}
```

<dl>
    <dt>Activar compartir con redes sociales - <i>nc_shareContent()</i></dt>
    <dd>Añade al final de cada entrada la opción de compartir con redes sociales (Facebook, Twitter, Google+ y Email).</dd>
</dl>

```php
function nc_shareContent() {
    $stateCheckShareContent = of_get_option('sharecontent');
    if ($stateCheckShareContent == 1) {
        get_template_part('content', 'share');
    }
}
```

## Configuracion Avanzada


<dl>
    <dt>Posición de la barra lateral - <i>nc_sidebarPosition()</i></dt>
    <dd>Permite definir la posición de la barra lateral (<i>sidebar</i>).</dd>
</dl>

```php
function nc_sidebarPosition() {
    $position = of_get_option('sidebar_position');
    if ($position == "sidebar_left") {
        $stylePosition = 'style="float:right"';
        return $stylePosition;
    }
}
```

<dl>
    <dt>Color del tema</dt>
    <dd>Permite seleccionar diferentes hojas de estilos para cambiar el color del tema (Rojo, Verde, Amarillo, Azul, Lila, Agua, Naranja). Para utilizar esto es necesario añadir el siguiente código dentro de la etiqueta &lt;head&gt;.</dd>
</dl>

```php
<?php echo of_get_option( 'style', 'style.min.css' ); ?>
```

<dl>
    <dt>Fondo del tema - <i>nc_changeBkgImgOrColor()</i></dt>
    <dd>Esta opción permite escoger el fondo de la página web. Se puede seleccionar un color o una imagen.</dd>
</dl>

```php
function nc_changeBkgImgOrColor() {
    $background = of_get_option('background');
    if ( $background ) {
        if ( $background['image'] ) {
            $bgc = ' style="background:url(' . $background['image'] . ')"';
            return $bgc;
        } else if ( $background['color'] ) {
            $bgc = ' style="background:' . $background['color'] . '"';
            return $bgc;
        } else {
            return null;
        }
    }
}
```

<dl>
    <dt>Favicon</dt>
    <dd>Permite subir una imagen para añadir un favicon en la página web. El código muestra una URL de la imagen.</dd>
</dl>

```php
<?php echo of_get_option( 'favicon' ); ?>
```

<dl>
    <dt>Activar "Infinite Scroll" - <i>nc_infiniteScroll()</i></dt>
    <dd>*EN DESARROLLO*</dd>
</dl>

```php
function nc_infiniteScroll() {
    // code
}
```

<dl>
    <dt>Activar "Infinite Scroll" - <i>nc_infiniteScroll()</i></dt>
    <dd>*EN DESARROLLO*</dd>
</dl>

```php
function nc_infiniteScroll() {
    // code
}
```

<dl>
    <dt>Activar "Infinite Scroll" - <i>nc_infiniteScroll()</i></dt>
    <dd>*EN DESARROLLO*</dd>
</dl>

```php
function nc_infiniteScroll() {
    // code
}
```

<dl>
    <dt>Activar "Infinite Scroll" - <i>nc_infiniteScroll()</i></dt>
    <dd>*EN DESARROLLO*</dd>
</dl>

```php
function nc_infiniteScroll() {
    // code
}
```



## Tipografía


## Licencia


## Footer


## Publicidad


## Otros



#########

# Instalar NunkiCore en tu tema / Instal·lar NunkiCore al teu tema / Install NunkiCore on your Theme

**[ES \| CASTELLANO, CASTELLÀ, SPANISH]**

+ Descargar repositorio desde GitLab

```
git clone https://gitlab.com/zagur/nunki-core.git
```

+ Copiar el directorio **inc/** y el fichero **options.php** en la raíz de tu tema.
+ Añadir este trozo de código en tu **functions.php**

```php
// Nunki Core
define( 'OPTIONS_FRAMEWORK_DIRECTORY', get_template_directory_uri() . '/inc/NunkiCore/' );
require_once dirname( __FILE__ ) . '/inc/NunkiCore/options-framework.php';
require_once dirname( __FILE__ ) . '/inc/NunkiCore/nunki-options.php';

// Loads options.php from child or parent theme
$optionsfile = locate_template( 'options.php' );
load_template( $optionsfile );
```

**[CA \| CATALÀ, CATALÁN, CATALAN]**

**[EN \| ENGLISH, INGLÉS, ANGLÈS]**

1) Descargar el repositorio
2) Copiar el contenido descargado en la raíz del tema (tu_tema/inc, tu_tema/options.php)
3) Añadir las siguientes lineas en el fichero functions.php de tu tema

// Theme Options
define( 'OPTIONS_FRAMEWORK_DIRECTORY', get_template_directory_uri() . '/inc/NunkiCore/' );
require_once dirname( __FILE__ ) . '/inc/NunkiCore/options-framework.php';
require_once dirname( __FILE__ ) . '/inc/NunkiCore/nunki-options.php';

// Loads options.php from child or parent theme
$optionsfile = locate_template( 'options.php' );
load_template( $optionsfile );

Listo.
