# blogdecafe_page
Página web de un blog de café

#Mejorando el Performance con lazy Loading
Incluir loading="lazy" en todas las imagenes para que no cargue al instante
sino hasta se visualize la imagen

#Mejorando el performance con preload
Preload lo que hara es cargar elementos que sean necesarios o lo más antes posible
por ejemplo las hojas de estilo o letras de google font o imagenes

example:

<link rel="preload" href="css/normalize.css" as="style">
<link rel="stylesheet" href="css/normalize.css">

<link rel="preload" href="https://fonts.googleapis.com/css2?family=Open+Sans&family=PT+Sans:wght@400;700&display=swap" as="font" crossorigin="crossorigin">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Open+Sans&family=PT+Sans:wght@400;700&display=swap" rel="stylesheet">
    
<link rel="preload" href="img/blog1.jpg" as="image">

#Mejorando el performance con prefetch
<link rel="prefetch" href="contacto.html" as="document">

document -> hace referencia a un archivo html y lo empieza a descargar y eso va hacer la carga mucha más rapida de la página.

Con Google Analytics podremos saber en que página de nuestro sitio pasan más tiempo para aplicarle ese prefetch.

#Imagenes más ligeras con Webp e imagenes picture
<picture>
    <source loading="lazy" srcset="img/blog1.webp" type="image/webp">
    <img loading="lazy" src="img/blog1.jpg" alt="Imagen Blog">
</picture>

El navegador cargara la imagen webp si es que lo soporta de otra manera entonces cargara la imagen jpg

#Mejorando el performance con Modernizr y Webp
Utilizando modernizr agregamos el script de webp a nuestro proyecto para utilizar nuestras imagenes webp en nuestro CSS directamente

.webp -> Soporta imagenes webp el navegador
.no-webp -> No soporta imagenes webp el navegador

Ejemplo:

.webp .header{
    background-image: url(../img/banner.webp);
}

.no-webp .header{
    background-image: url(../img/banner.jpg);
}

.header{
    height: 60rem;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center center;
}

#Etiquetas Meta
<meta name="description" content="Página web de blog de café">  
Ayuda a buscar nuestro sitio web (SEO)

