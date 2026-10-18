# Andamio mínimo para Ehundu

Un sitio de presentación de cuatro páginas (inicio, servicios, contacto y la página de error), hecho con [Ehundu](https://ehundu.com), el generador de sitios estáticos en PHP. Es un andamio: la estructura de partida de un sitio pequeño. Cambias los textos, los datos y el CSS, y es tuyo.

Puedes verlo funcionando, sin instalar nada, en [andamio-minimo.ehundu.com](https://andamio-minimo.ehundu.com/).

Necesitas PHP 8.4 o superior y [Composer](https://getcomposer.org).

## Empezar

Si lo has creado con `composer create-project`, ya está todo instalado. Si has usado el botón «Use this template» de GitHub, o has descargado el zip, instala el motor:

```
composer install
```

Las tres órdenes que vas a usar:

```
composer servir      # lo previsualiza en http://127.0.0.1:8000/ y rehace solo lo que cambia
composer compilar    # deja el sitio terminado en la carpeta salida/
composer desplegar   # lo compila y lo sube al servidor que digas en sitio.yml
```

## Qué hay en cada carpeta

```
sitio.yml        el nombre, la dirección y adónde se publica
contenido/       las páginas, en Markdown: cada fichero es una página
datos/           lo que se repite en varias páginas (el nombre, el correo, el teléfono)
plantillas/      el HTML que envuelve cada página, con Twig
parciales/       trozos de HTML que reutilizan las plantillas (la cabecera y el pie)
publico/         el CSS, las imágenes y el icono: se copia tal cual a la raíz del sitio
```

`salida/` (el sitio compilado) y `.ehundu/` (lo que recuerda el motor) los crea Ehundu y no se versionan.

## Lo primero que cambiar

1. En `sitio.yml`, el nombre y la dirección del sitio.
2. En `datos/cliente.yml`, tus datos.
3. En `contenido/`, los textos.
4. En `publico/css/estilos.css`, los colores: están al principio, en variables.

## Publicarlo

Descomenta la sección `despliegue` de `sitio.yml` y rellénala. La contraseña no va ahí, porque `sitio.yml` se comparte: crea un fichero `.secretos.yml` en la raíz del proyecto, entre comillas simples:

```yaml
despliegue:
  clave: 'la-contraseña'
```

Antes de subir nada, mira qué haría:

```
composer desplegar -- --simular
```

Y cuando todo cuadre, `composer desplegar`. La guía [Desplegar el sitio](https://ehundu.com/documentacion/guias/desplegar/) explica los destinos (carpeta, FTP, SFTP y S3) y cómo decide Ehundu qué sube y qué borra.

## Para seguir

- [Tu primer sitio](https://ehundu.com/documentacion/empezar/tu-primer-sitio/), un recorrido paso a paso.
- [La hoja de referencia rápida](https://ehundu.com/documentacion/empezar/hoja-rapida/), con todo lo que vas a necesitar cada día.
- [La documentación completa](https://ehundu.com/documentacion/).

Licencia MIT.
