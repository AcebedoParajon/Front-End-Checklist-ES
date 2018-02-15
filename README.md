[![Front-End Checklist Logo](https://github.com/thedaviddias/Front-End-Checklist/blob/master/src/img/banners/front-end-checklist-banner-light.jpg?raw=true)](https://frontendchecklist.io)

# Front-End Checklist-ES
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/eoasakura/Front-End-Checklist-ES/graphs/contributors)
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/eoasakura/Front-End-Checklist-ES/)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

La **Front-End Checklist** es una lista exhaustiva de todos los elementos que necesitas tener/probar antes de lanzar tu sitio/página HTML a producción.

Esta basada en años de experiencia de desarrolladores Front-End, con agregados provenientes de otros checklist de código abierto.

## Tabla de contenidos

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Webfonts](#webfonts)**
4. **[CSS](#css)**
5. **[Imágenes](#imágenes)**
6. **[JavaScript](#javascript)**
7. **[Seguridad](#seguridad)**
8. **[Rendimiento](#rendimiento-1)**
9. **[Accesibilidad](#accesibilidad)**
10. **[SEO](#seo)**


## ¿Cómo usar?

Todos los elementos en la **Front-End Checklist** son requeridos para la mayoría de los proyectos, pero algunos elementos pueden ser omitidos o no son esenciales (por ejemplo, en el caso de una aplicación web administrativa, quizás no necesitas la función de RSS). Elegimos usar 3 niveles de flexibilidad:

* ![Bajo][low_img] significa que el elemento es **recomendado** pero puede ser omitido en situaciones particulares.
* ![Medio][medium_img] significa que el elemento es **altamente recomendado** y eventualmente puede ser omitido en casos muy particulares. Algunos elementos, si son omitidos, pueden traer malas repercusiones en términos de rendimiento o SEO.
* ![Alto][high_img] significa que el elemento **no se puede omitir** por ningún motivo. Puede causar una anomalía en su página, tener problemas de accesibilidad o SEO. Estos elementos deben tener prioridad en el test.

Algunos recursos poseen un emoticón para ayudar a entender el tipo de contenido/ayuda que podrás encontrar en el checklist:

* 📖: documentación o artículos
* 🛠: herramienta en línea / herramienta para pruebas
* 📹: media o contenido en video

> **Nota:** Debido a que este documento es una traducción, la documentación, artículos, herramientas y medios se encuentran en inglés. 

---

## Head

> **Nota:** Puedes encontrar [una lista de todo](https://github.com/eoasakura/HEAD-ES) `(traducción en progreso)` lo que puede encontrarse en el `<head>` de un documento HTML.

### Meta tag

* [ ] **Doctype:** ![Alto][high_img] El Doctype es HTML5 y se localiza arriba del todo en tus páginas HTML.

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> 📖 [Determinando la codificación de caracteres - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)`(fuente en inglés)`

*Los siguientes 3 meta etiquetas (Charset, X-UA Compatible and Viewport) necesitan ir primero en el head.*

* [ ] **Charset:** ![Alto][high_img] El charset definido (UTF-8) es declarado correctamente.

```html
<!-- Declaramos la codificación de juego de caracteres para el documento -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** ![Medio][medium_img] La meta etiqueta X-UA-Compatible está presente.

```html
<!-- Ordenamos a Internet Explorer usar su motor de renderizado más reciente -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> 📖 [Especificando modos de documento heredado (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx) `(fuente en inglés)`

* [ ] **Viewport:** ![Alto][high_img] El viewport es declarado correctamente.

```html
<!-- Viewport para diseño web responsivo -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![Alto][high_img] El título es usado en todas las páginas (SEO: Google calcula el ancho de los caracteres usados en el título y los corta entre los 477 y 485 pixeles. El límite promedio en los títulos es de no más de 55 caracteres).

```html
<!-- Título del documento -->
<title>Título de página menor a 55 caracteres</title>
```

> 📖 [Título - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title) `(fuente en inglés)`
> * 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/) `(fuente en inglés)`

* [ ] **Description:** ![Alto][high_img] Una meta descripción es proporcionada, es única y no posee más de 150 caracteres.

```html
<!-- Meta descripción -->
<meta name="description" content="Descripción de la página en menos de 150 caracteres">
```
> 📖 [Meta descripción - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description) `(fuente en inglés)`

* [ ] **Favicons:** ![Medio][medium_img] Cada favicon se ha creado y mostrado correctamente. Si solo tienes un `favicon.ico`, colocalo en la raíz de tu sitio. Normalmente no necesitarás usar ningún marcado. Sin embargo, es una buena práctica enlazarlo usando el ejemplo debajo. Al día de hoy, **se recomienda el formato PNG** sobre el formato `.ico` (dimensión: 32x32px).

```html
<!-- Favicon estandar -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Formato favicon recomendado -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Generador de Favicon](https://www.favicon-generator.org/) `(herramienta en inglés)`
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/) `(herramienta en inglés)`
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet) `(fuente en inglés)`
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. ¿Cuál necesitas? - CSS Tricks](https://css-tricks.com/favicon-quiz/) `(fuente en inglés)`
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png) `(fuente en inglés)`

* [ ] **Apple Web App Meta:** ![Low][low_img] Se usan Apple meta-tags.

```html
<!-- Apple Touch Icon (al menos de 200x200px)-->
<link rel="apple-touch-icon" href="/custom-icon.png">
<!-- Para correr aplicaciones a pantalla completa -->
<meta name="apple-mobile-web-app-capable" content="yes">
<!-- Estilo de la barra de estado (ver enlace Meta Tags soportados para valores disponibles) -->
<!-- No funcionará a menos que coloques la etiqueta anterior -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">

```

> 📖 [Configurando Aplicaciones Web](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html) `(fuente en inglés)`
> * 📖 [Meta Tags soportados](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html) `(fuente en inglés)`

- [ ] **Windows Tiles:**![Low][low_img] Windows tiles están presentes y enlazadas.

```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

El marcado xml mínimo requerido para el archivo browserconfig.xml es el siguiente:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

> 📖 [Referencia de esquema de configuración del navegador](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx) `(fuente en inglés)`

* [ ] **Canonical:** ![Medium][medium_img] Usa `rel="canonical"` para evitar contenido duplicado.

```html
<!-- Ayuda a prevenir problemas de contenido duplicado -->
<link rel="canonical" href="http://ejemplo.com/2017/09/articulo-nuevo-para-leer.html">
```

> * 📖 [Consolidar URLs duplicadas - Search Console Help - Google Support](https://support.google.com/webmasters/answer/139066?hl=es)
> * 📖 [5 errores comunes con rel=canonical - Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html) `(fuente en inglés)`

### Etiquetas HTML

* [ ] **Language tag:** ![Alto][high_img] La etiqueta de lenguaje de tu sitio web está específicada y relacionada al lenguaje de la página actual.

```html
<!-- Indicamos el idioma definido para la página actual -->
<html lang="es">
```

* [ ] **Direction tag:** ![Medio][medium_img] La dirección de lectura es específicada en la etiqueta body (Puede ser usada en otra etiqueta HTML).

```html
<!-- Indicamos la dirección de lectura (rtl = right to left/ derecha a izquierda) -->
<html dir="rtl">
```

> 📖 [Atributo Global dir - HTML - MDN](https://developer.mozilla.org/es/docs/Web/HTML/Atributos_Globales/dir)

* [ ] **Alternate language:** ![Bajo][low_img] La etiqueta de lenguaje de tu sitio web está específicada y relacionada al lenguaje de la página actual .

```html
<!-- Indicamos el idioma definido para la página actual -->
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Comentarios condicionales:** ![Bajo][low_img] Comentarios condicionales están presentes para IE si son necesarios.

> 📖 [Comentarios condicionales (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx) `(fuente en inglés)`

* [ ] **RSS feed:** ![Bajo][low_img] Si tu proyecto es un blog o tiene artículos, un enlace RSS fue proprocionado.

* [ ] **CSS Crítico:** ![Medio][medium_img] El CSS crítico (o "above the fold") contiene todo el CSS usado para renderizar la porción visible de la página. Se incrusta antes de la llamada principal a CSS y entre `<style></style>` en una sola línea (minificado).

> 🛠 [Critical by Addy Osmani on Github](https://github.com/addyosmani/critical)

* [ ] **Orden del CSS:** ![Alto][high_img] Todos los archivos CSS son cargados antes que cualquier archivo JavaScript en el `<head>`. (Excepto en los casos donde los archivos JS se cargan asíncronamente en tus páginas).

### Social meta

***Facebook OG*** y ***Twitter Cards*** son altamente recomendados para cualquier sitio. Otras etiquetas de medios sociales pueden ser considerados si tienes un objetivo partícular y quieres asegurar la visualización.

* [ ] **Facebook Open Graph:** ![Bajo][low_img] Todos los Facebook Open Graph (OG) fueron probados y ninguno es erroneo o contiene información falsa. Las imágenes necesitan ser de al menos 600 x 315 pixeles, se recomienda 1200 x 630 pixeles.

> **Nota:** Al usar `og:image:width` y `og:image:height` se especificaran las dimensiones de la imagen al crawler para que pueda desplegar la imagen inmediatamente sin tener que descargarla y procesarla asíncronamente.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Título del contenido">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Descripción aquí">
<meta property="og:site_name" content="Nombre del sitio">
<meta property="og:locale" content="en_US">
<!-- Las siguientes etiquetas son opcionales, pero recomendadas -->
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
```

> * 📖 [Guía para webmasters sobre el uso compartidos](https://developers.facebook.com/docs/sharing/webmasters/)
> * 🛠 Prueba tus páginas con el [Depurador de contenido compartido](https://developers.facebook.com/tools/debug/)

* [ ] **Twitter Card:** ![Bajo][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Título del contenido">
<meta name="twitter:description" content="Descripción del contenido menor a 200 caracteres">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started) `(fuente en inglés)`
> * 🛠 Test your page with the [Twitter card validator](https://cards-dev.twitter.com/validator)

**[⬆ volver a arriba](#tabla-de-contenidos)**

---

## HTML

### Mejores prácticas

* [ ] **Elementos semánticos HTML5:** ![Alto][high_img] Los elementos semánticos HTML5 son usados apropiadamente (header, section, footer, main...).

> 📖 [Referencia HTML](http://htmlreference.io/) `(fuente en inglés)`

* [ ] **Páginas de error:** ![Alto][high_img] Páginas de error 400 y 5xx existen. Recuerda que las páginas de error 5xx necesitan tener su CSS integrado (sin llamadas externas del servidor actual).

* [ ] **Noopener:** ![Medio][medium_img] En caso que uses enlaces externos con `target="_blank"`, tu enlace debe tener un atributo `rel="noopener"`para evitar tab nabbing. Si necesitas dar soporte a versiones antigüas de Firefox, usa `rel="noopener noreferrer"`.

> 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Limpiar comentarios:** ![Bajo][low_img] Código innecesario necesita ser removido antes de enviar la página a producción.

### Pruebas HTML

* [ ] **Obedece al W3C:** ![Alto][high_img] Todas las páginas necesitan ser aprobadas por el validador W3C para identificar posibles problemas en el código HTML.

> 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![Alto][high_img] Uso herramientas para ayudarme a analizar cualquier problema que podría tener en mi código HTML.

> 🛠 [Dirty markup](https://dirtymarkup.com/)

> * 🛠 [Sonar a linting tool for the web](https://sonarwhal.com/)

* [ ] **Verificador de enlaces:** ![High][high_img] No hay enlaces rotos en la página,  verifica que no tienes ningún error 404.

> 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Prueba de Adblockers:** ![Medium][medium_img] Tu sitio web muesta el contenido correctamente cuando adblockers están habilitados (Puedes incluir un mensaje para sugerir a las personas deshabilitar su adblocker).


**[⬆ volver a arriba](#tabla-de-contenidos)**

---

## Webfonts

> **Notas:** Usar fuentes web puede ocasionar retardos en la visualización de textos (Flash Of Unstyled Text/Flash Of Invisible Text), considera tener fuentes de respaldo y/0 usar cargadores de fuentes para controlar el comportamiento.
> * 📖 [Consideraciones técnicas acerca de webfonts](https://developers.google.com/fonts/docs/technical_considerations) `(fuente en inglés)`

* [ ] **Formato de fuentes:** ![Alto][high_img] WOFF, WOFF2 y TTF son formatos soportados por todos los navegadores modernos.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff). `(fuente en inglés)`
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2). `(fuente en inglés)`
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf) `(fuente en inglés)`
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/) `(fuente en inglés)`

* [ ] **Tamaño de fuentes:** ![High][high_img] El tamaño de las fuentes no excede los 2 MB (todas las variantes incluidas).
* [ ] **Cargador de fuentes:** ![Low][low_img] Controlar el comportamiento de carga de fuentes con un cargador de fuentes web

> * 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ volver a arriba](#tabla-de-contenidos)**

---

## CSS

> **Notas:** Echa un vistazo a los [Lineamientos CSS](https://cssguidelin.es/) y [Lineamientos Sass](https://sass-guidelin.es/) seguidos por la mayoría de los desarrolladores. Si tienes alguna duda acerca de las propiedades CSS, puedes visitar la [Referencia CSS](http://cssreference.io/).

* [ ] **Diseño Web Responsivo:** ![High][high_img] El sitio wen utiliza diseño web responsivo.
* [ ] **CSS Print:** ![Medium][medium_img] Se proporciona una hoja de estilo para impresión y es correcto en cada página.
* [ ] **Preprocesador:** ![Medium][medium_img] Tu página utiliza un preprocesador CSS ([Sass](http://sass-lang.com/) es recomendado).
* [ ] **ID único:** ![High][high_img] Si utilizas IDs, son únicos en la página.
* [ ] **Reinicio de CSS:** ![High][high_img] Un reinicio de CSS es usado y está actualizado. *(Si utilizas algún Framework CSS como Bootstrap o Foundation, el reinicio de CSS ya está implementado.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **Prefijos JS:** ![Low][low_img] Todas las clases (o id- usados en archivos JavaScript) comienzan con **js-** y no son estilizados dentro del archivo CSS.

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **CSS incrustado:** ![High][high_img] Evita a todo costo el CSS inscrustado (directo al HTML): solo usalo por razones válidas (ej: imagen de fondo para un slider, CSS crítico).
* [ ] **Vendor prefixes:** ![High][high_img] Los vendor prefixes son usados y generados de acuerdo con la compatibilidad de tu navegador. *(Si utilizas un preprocesador, esta labor se puede automatizar)*

> 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Rendimiento

- [ ] **Concatenado:** ![High][high_img] Los archivos CSS son concatenados en un solo archivo. *(No aplica en HTTP/2)*
- [ ] **Minificado:** ![High][high_img] Todos los archivos CSS están minificados (estilos en una sola línea).
- [ ] **No bloquea renderizado:** ![Medium][medium_img] Los archivos CSS no deben afectar el tiempo carga del DOM.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **CSS sin utilizar:** ![Low][low_img] Remover CSS sin utilizar.

> * 🛠 [UnCSS Online](https://uncss-online.com/) 
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [PurgeCSS](https://github.com/FullHuman/purgecss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### Pruebas CSS 

* [ ] **Stylelint:** ![High][high_img] Los archivos CSS o SCSS no contienen errores.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)


* [ ] **Diseño web responsivo:** ![High][high_img] Todas las páginas fueron probadas en los siguientes puntos: 320px, 768px, 1024px (pueden ser más / varia de acuerdo a tus resultados en analítica).

* [ ] **Validador CSS:** ![Medium][medium_img] El CSS fue probado y los errores pertinentes fueron corregidos.

> 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Navegadores de escritorio:** ![High][high_img] Todas las págunas fueron probadas en todos los navegadores actuales (Safari, Firefox, Chrome, Edge...)
* [ ] **Navegadores móviles:**  ![High][high_img] Todas las páginas fueron probadas en todos los navegadores móviles actuales (Navegador nativo, Chrome, Safari...)
* [ ] **Sistema Operativo:**  ![High][high_img] Todas las páginas fueron probadas en todos los Sistemoas Operativos actuales (Windows, Android, iOS, Mac).

- [ ] **Fidelidad al diseño:** ![Low][low_img] Dependiendo del proyecto y de la calidad creativa, pueden solicitarte apegarte lo más posible al diseño. Puedes utilizar herramientas para comparar los diseños con la implementación de código y asegurar consistencia.

> 🛠 [Pixel Perfect - Extension para Chrome](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

* [ ] **Dirección de lectura:** ![High][high_img] Todas las páginas necesitan ser probadas para idiomas LTR y RTL si necesitan soporte.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/) `(fuente en inglés)`
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/) `(fuente en inglés)`

**[⬆ volver a arriba](#tabla-de-contenidos)**

---

## Imágenes

> **Notas:** Para un completo entendimiento de la optimización de imágenes, mira el ebook gratuito **[Essential Image Optimization](https://images.guide/)** de Addy Osmani.

### Mejores prácticas

* [ ] **Optimización:** ![High][high_img] Todas las imágesnes están optimizadas para ser renderizadas en el navegador. El formato WebP puede ser utilizado para páginas críticas (como la Página de Inicio).

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Usa [ImageOptim](https://imageoptim.com/) para optimizar tus imágenes gratis.
> * 🛠 Usa [Kraken.io](https://kraken.io/web-interface) una maravillosa alternativa tanto para optimización png o jpg. Hasta 1mb por archivo en plan gratuito.
> * 🛠 [TinyPNG](https://tinypng.com/) optimiza sin perdidas png, apng (png animado) e imágenes jpg. Versiones gratuitas y de pago disponibles.
> * 🛠 [ZorroSVG](http://quasimondo.com/ZorroSVG/) compresion jpg para imágenes transparentes usando enmascarado svg.
> * 🛠 [SVGO](https://github.com/svg/svgo) una herramienta basada en Nodejs para optimisar archivos de gráficos vectoriales.
> * 🛠 [SVGOMG](https://jakearchibald.github.io/svgomg/)  herramienta para optimizar archivos svgs en línea.


* [ ] **Picture/Srcset:** ![Medium][medium_img] You use picture/srcset to provide the most appropriate image for the current viewport of the user.

> * 📖 [How to Build Responsive Images with srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

* [ ] **Retina:** ![Low][low_img] Proporcionas imágenes para layouts x2 o x3, soporte para retina display.
* [ ] **Sprite:** ![Medium][medium_img] Las imágenes pequeñas están en un archivo sprite (en el caso de iconos, es recomedable colocarlos en formato SVG).
* [ ] **Ancho y altura:** ![High][high_img] Todo las etiquetas `<img>` tienen una altura y ancho establecido (No especificar px o %).

* [ ] **Lazy loading:** ![Medium][medium_img] Las imágenes usan lazy loading (solo cargan cuando están en la parte visible del viewport, siempre se proporciona un fallback que no use script).

* [ ] **Texto alternativo:** ![High][high_img] Todas las imágenes tienen un texto alternativo que las describe.

> * 📖 [Textos alternativos - La guía definitiva](https://axesslab.com/alt-texts/) `(fuente en inglés)`


**[⬆ volver a arriba](#tabla-de-contenidos)**

---

## JavaScript

### Mejores prácticas

* [ ] **JavaScript Incrustado:** ![High][high_img] No tienes JavaScript incrustado (mezclado con tu código HTML).
* [ ] **Concatenado:** ![High][high_img] Los archivos JavaScript están concatenados.
* [ ] **Minificado:** ![High][high_img] Los archivos JavaScript están minificados (puedes agregar el subfijo `.min`).

> [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **Seguridad JavaScript:**

> [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)*

* [ ] **`noscript` tag:** ![Medium][medium_img]  Usar la etiqueta `<noscript>`en el cuerpo del HTML si un script en la página no es soportado o si los scripts están desactivaos en el navegaor. Esto será útil en el renderizado de aplicaciones cliente-servidor pesadas, como React,js, ver [ejemplo](https://webdesign.tutsplus.com/tutorials/quick-tip-dont-forget-the-noscript-element--cms-25498) `(fuente en inglés)`

```html
<noscript>
  Necesitas habilitar Javascript para visualizar la aplicación.
</noscript>
```

* [ ] **No bloquea el renderizado:** ![Medium][medium_img] Los archivos JavaScript son cargados asíncronamente usando el atributo `async` o deferidos usando el atributo `defer`.

> 📖 [Remover Javascript que bloquea el renderizado](https://developers.google.com/speed/docs/insights/BlockingJS) `(fuente en inglés)`

* [ ] **Modernizr:** ![Low][low_img] Si necesitas apuntar a alguna característica específica puedes usar Modernizr para agregar clases a tu etiqueta `<html>`.

> 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### Pruebas de JavaScript

* [ ] **ESLint:** ![High][high_img] No hay errores marcados por ESLint (basados en tu configuración o reglas de estándares)

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ volver a arriba](#tabla-de-contenidos)**

---

## Seguridad

### Scanear verificar tu sitio web

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - Automated Security Analyser for ASP.NET Websites](https://asafaweb.com/)

### Mejores prácticas

* [ ] **HTTPS:** ![Medium][medium_img] HTTPS es usado en cada página y para todo el contenido externo (plugins, imágenes...).

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] La cabecera HTTP está configurada como 'Strict-Transport-Security'.

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Cross Site Request Forgery (CSRF):** ![High][high_img] Asegurate que las peticiones hechas a tu servidor son legítimas y oríginadas desde tu sitio web/aplicación para prevenir ataques CSRF.

> 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Cross Site Scripting (XSS):** ![High][high_img] Tu página o sitio web esta libre de posibles problemas XSS.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Opciones de Content-Type** ![Medium][medium_img] Previene a Google Chrome e Internet Explorer intentar ataques mime-sniff al content-type de respuestas no declaradas desde el servidor.

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO)** ![Medium][medium_img] Proteje a tus visitantes contra ataques clickkacking.

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

* [ ] **Política de seguridad del contenido:** ![Medium][medium_img] Define cómo es cargado el contenido en tu sitio y desde dónde está permitido cargarlo. Puede ser usado para proteger contra ataques clckjacking.

> * 📖 [Content Security Policy - An Introduction - Scott Helme](https://scotthelme.co.uk/content-security-policy-an-introduction/)
> * 📖 [CSP Cheat Sheet - Scott Helme](https://scotthelme.co.uk/csp-cheat-sheet/)
> * 📖 [CSP Cheat Sheet - OWASP](https://www.owasp.org/index.php/Content_Security_Policy_Cheat_Sheet)
> * 📖 [Content Security Policy Reference](https://content-security-policy.com/)

**[⬆ volver a arriba](#tabla-de-contenidos)**

---

## Rendimiento

### Mejores prácticas

- [ ] **Metas a alcanzar:** ![Medium][medium_img] Tu página debe alcanzar las siguientes metas:
  - La primera visualización significativa suceda en menos de 1 segundo
  - El tiempo para interactuar es menor a 5 segundos para una configuración "promedio" (un dispositivo Android en una red 3G lenta con 400ms RTT y velocidad de transferencia de 400kbps) y menor a 2 segundos para visitas recurrentes.
  - Tamaño de archivo debajo de 170Kb gzipped

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 🛠 [WebPageTest](https://www.webpagetest.org/)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minificado:** ![Medium][medium_img] Tu HTML está minificado.

* [ ] **Lazy loading:** ![Medium][medium_img] Imágenes, scripts y CSS necesitan cargarse implementando lazy loading para mejorar el tiempo de respuesta de la página actual (Mira los detalles en las secciones respectivas)

* [ ] **Tamaño de Cookie:** Si estás usando cookies asegurate que cada cookie no exceda los 4096 bytes y tu nombre de dominio no tiene más de 20 cookies.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

* [ ] **Componentes de terceros:** ![Medium][medium_img] iframes o componentes de terceros que dependan de JS externo (como botones para compartir contenido) son reemplazados por componentes estáticos cuando sea posible, asi se limitan llamadas externas a APIs y se mantiene privada la actividad de los usuarios.

> * 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### Preparando solicitudes futuras

> 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **Resolución de DNS:** ![Low][low_img] Los DNS de servicios de terceros que son necesarios son resueltos por adelantado durante el tiempo de inactividad usando `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Pre-conexión:** ![Low][low_img] Búsquedas de DNS, TCP handshakes y negociaciones TLS con servicios que serán requeridos pronto son hechos por adelantado durante el tiempo de inactividad usando `preconnect`.

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching:** ![Low][low_img] Recursos que se necesitarán pronto (ej. imágenes con lazy loading) son solicitados por adelantado durante el tiempo de inactividad usando `prefetch`.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Precarga:** ![Low][low_img] Recursos necesarios en la página actual (ej. scripts colocados al final de la etiqueta `<body>`) son solicitados por adelantado usando `preload`.

```html
<link rel="preload" href="app.js">
```

> 📖 [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Performance testing

* [ ] **Google PageSpeed:** ![High][high_img] Todas tus páginas fueron probadas (no solo la página de inicio) y tienen una calificación de al menos 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)
> * 🛠 [GTmetrix - Website speed and performance optimization](https://gtmetrix.com/)

**[⬆ volver a arriba](#tabla-de-contenidos)**

---

## Accesibilidad

> **Notas:** Puedes mirar la lista de reproducción [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Mejores prácticas

- [ ] **Mejora progresiva:** ![Medium][medium_img] Las funcionalidad principales, como la navegación y búsquedas, deben funcionar con JavaScript deshabilitado.

> 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Contraste de color:** ![Medium][medium_img] El contraste de color debe pasar la recomendación WCAG AA (AAA para móviles).

> 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/)

#### Encabezados

* [ ] **H1:** ![High][high_img] Todas las páginas tienen una etiqueta H1 la cual no es el título del sitio web.
* [ ] **Encabezados:** ![High][high_img] Los encabezados deben ser usados en el orden correcto (H1 a H6).

> 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Puntos de referencia

- [ ] **Role banner:** ![High][high_img] `<header>` tiene el atributo `role="banner"`.
- [ ] **Role navigation:** ![High][high_img] `<nav>` tiene el atributo `role="navigation"`.
- [ ] **Role main:** ![High][high_img] `<main>` tiene el atributo `role="main"`.

> 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### Semántica

- [ ] **Tipos de entrada HTML5 específicos son usados:** ![Medium][medium_img] Esto es importante para dispositivos móviles que muestran teclados personalizados y widgets para diferentes tipos.

> 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Formulario

* [ ] **Etiqueta:** ![High][high_img] Una etiqueta `<label>` es asociada a cada elemento del formulario. En caso de que una etiqueta no pueda ser mostrada, usa `aria-label` en su lugar.

> 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Pruebas de accesibilidad

* [ ] **Pruebas de estándares de accesibilidad:** ![High][high_img] Usa la herramienta WAVE para probar si tu página respeta los estándares de accesibilidad.

> 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Navegación con teclado:** ![High][high_img] Prueba tu sitio web utlizando solo tu teclado en un orden previsible. Todos los elementos interactivos son alcanzable y pueden usarse.
* [ ] **Screen-reader:** ![Medium][medium_img] Todas las páginas son probadas en un screen reader (VoiceOver, ChromeVox, NVDA o Lynx).
* [ ] **Focus style:** ![High][high_img] Si se deshabilita el estado focus de los elementos, se reemplaza por un estado visible en CSS.

> 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ volver a arriba](#tabla-de-contenidos)**

---

## SEO

* [ ] **Google Analytics:** ![High][high_img] Google Analytics está instalado y configurado correctamente.

> * 🛠 [Google Analytics](https://analytics.google.com/analytics/web/)
> * 🛠 [GA Checker (and others)](http://www.gachecker.com/)

* [ ] **Lógica de encabezados:** ![Medium][medium_img] El texto de encabezado ayuda a entender el contenido en la página actual.

> * 🛠 [Tota11y, tab Headings](http://khan.github.io/tota11y/#Try-it)

* [ ] **sitemap.xml:** ![High][high_img] Existe un sitemap.xml y fue enviado por Google Search Console (nombrado Google Webmaster Tools anteriormente).

> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)

* [ ] **robots.txt:** ![High][high_img] El archivo robots.txt no bloquea páginas.

> * 📖 [The robots.txt file](https://varvy.com/robottxt.html)
> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Datos estructurados:** ![High][high_img] Las páginas usando datos estructurados son probadas y no contienen errores. Los datos estructurados ayudar a los crawlers a entender el contenido en la página actual.

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 📖 [RDFa - Linked Data in HTML](https://rdfa.info/)
> * 📖 [JSON-LD](https://json-ld.org/)
> * 📖 [Microdata](https://www.w3.org/TR/microdata/)
> * 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)
> * 🛠 Complete list of vocabularies that can be used as structured data. [Schema.org Full Hierarchy](http://schema.org/docs/full.html)

* [ ] **Sitemap HTML:** ![Medium][medium_img] Un sitemap HTML es proporcionado y es accesible con enlaces en el footer del sitio web.

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)

* [ ] **Enlaces con etiquetas de paginación:** ![Medium][medium_img] Proporcionar `rel="prev"` y `rel="next"` para indicar contenido paginado.

> * 🛠 [Pagination (rel="prev/next") Testing Tool](https://technicalseo.com/seo-tools/rel-prev-next/)

> * 📖 [Pagination guidelines - Google Support](https://support.google.com/webmasters/answer/1663744?hl=en)

```html
<!-- Ejemplo: Enlaces con etiquetas de paginación de la página 2 -->
<link rel="prev" href="https://example.com/?page=1">
<link rel="next" href="https://example.com/?page=3">
```

**[⬆ vovler a arriba](#tabla-de-contenidos)**

---

## Traducción

La Front-End Checklist también está disponible en otros idiomas. ¡Gracias a todos los traductores y a su mágnifico trabajo!

* :us:  Inglés(repositorio principal): [thedaviddias/Front-End-Checklist](https://github.com/thedaviddias/Front-End-Checklist)
* 🇯🇵 Japonés: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇨🇳 Chino: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Coreano: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Portugués: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
* 🇻🇳 Vietnamita: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)
* 🇹🇼 Traditional Chinese: [EngineLin/Front-End-Checklist](https://github.com/EngineLin/Front-End-Checklist)
* 🇫🇷 French: [ynizon/Front-End-Checklist](https://github.com/ynizon/Front-End-Checklist)
* 🇷🇺 Russian: [ungear/Front-End-Checklist](https://github.com/ungear/Front-End-Checklist)
* 🇹🇷 Turkish: [eraycetinay/Front-End-Checklist](https://github.com/eraycetinay/Front-End-Checklist)
* 🇩🇪 German: [xfuture603/Front-End-Checklist](https://github.com/xFuture603/Front-End-Checklist)


**[⬆ volver a arriba](#tabla-de-contenidos)**

---
## Insignia Front-End Checklist

Si quieres mostrar que estás siguiendo las reglas del Front-End Checklist, pon esta insignia en tu archivo README.

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ volver a arriba](#tabla-de-contenidos)**

---

## Contribución

**Abre un issue o un pull requesto para sugerir cambios o añadir información**

### Guía

El repositorio del **Front-End Checklist** consiste en dos ramas:

#### 1. `master`

Esta rama consiste en el archivo `README.md` que se refleja automaticamete en el sitio web [Front-End Checklist](http://frontendchecklist.com/).

#### 2. `develop`

Esta rama será usada para hacer cambios significativos a la estructura o contenido, de ser necesarios. Es preferible usar la rama master para pequeñas correcciones o añadir un nuevo elemento.

### Contribuyentes

Dale un vistazo a todos estos asombrosos [contribuyentes](https://github.com/eoasakura/Front-End-Checklist-ES/graphs/contributors).

## Autores

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**, **[Geoffrey Signorato](https://github.com/geosenna)**, **[Sandeep Ramgolam](https://twitter.com/__Sun__)** and **[Cédric Poilly](https://github.com/CedricPoilly)**.

## Licencia

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ volver a arriba](#tabla-de-contenidos)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png
