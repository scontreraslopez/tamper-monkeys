# tamper-monkeys

Scripts de [Tampermonkey](https://www.tampermonkey.net/) que uso para extraer directamente desde el front (en el navegador) información que contiene datos sensibles, y luego trabajarla a mano en Excel y similares.

## Por qué existe este repo

Los datos con información personal (PII) de alumnado, familias, etc. **no deben pasar por ningún LLM**. Por eso estos scripts:

- Se ejecutan **en local, dentro del navegador**, sobre páginas donde ya tengo sesión iniciada.
- **No envían nada a servidores externos** (`@grant none`, sin peticiones a terceros; solo se consulta el propio sitio).
- Dejan el resultado en pantalla o en un fichero local para tratarlo después a mano.

## Scripts

| Script | Sitio | Qué hace |
| --- | --- | --- |
| [`Aules · Pendientes de corregir-1.0.txt`](./Aules%20·%20Pendientes%20de%20corregir-1.0.txt) | Aules (`aules.edu.gva.es`) | En la portada de un curso, muestra bajo cada tarea cuántas entregas quedan por corregir. |

## Instalación

1. Instalar la extensión Tampermonkey en el navegador.
2. Crear un script nuevo y pegar el contenido del fichero `.txt` correspondiente (o importarlo desde fichero).
3. Guardar y comprobar que está activado. Se ejecuta solo en las URLs indicadas en `@match`.

## Normas del repo

- **Nunca subir datos reales** (capturas, exportaciones, CSV/Excel con PII, logs). Solo código.
- No pegar nada de lo que sacan estos scripts en un chat con IA ni en herramientas externas.
- Revisar los `@match` y `@grant` de cada script antes de añadirlo.

## Créditos

- *Aules · Pendientes de corregir* es un port a userscript de la extensión [josangarcia/aules-pendientes-corregir](https://github.com/josangarcia/aules-pendientes-corregir).
