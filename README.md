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
| [`Exportar participantes Aules a CSV-1.0.txt`](./Exportar%20participantes%20Aules%20a%20CSV-1.0.txt) | Aules (`aules.edu.gva.es`) | Exporta los participantes de un curso a CSV. |
| [`Exportar alumnos ITACA-grupo a CSV-1.0.txt`](./Exportar%20alumnos%20ITACA-grupo%20a%20CSV-1.0.txt) | Docent (`docent.edu.gva.es/md-front`) | Exporta los alumnos del grupo (apellidos, nombre, grupo, módulo, singularidad) a CSV. |
| [`ITACA · Exportar matrículas (recorrido alumno a alumno)-3.0.txt`](./ITACA%20·%20Exportar%20matrículas%20%28recorrido%20alumno%20a%20alumno%29-3.0.txt) | ITACA (`itaca3.edu.gva.es/itaca3-gac`) | Recorre la ficha de matrícula con "Siguiente" y exporta alumno, grupo, repite, modalidad, horas y módulos a CSV por partes. |
| [`Exportar alumnos SAO-GESTION a CSV-1.0.txt`](./Exportar%20alumnos%20SAO-GESTION%20a%20CSV-1.0.txt) | SAO-Gestión (`@match *://*/*`) | Exporta el grid de alumnos (ZK) a CSV, con o sin paginador. |
| [`Exportar empresas SAO-Gestion (ITACA) a CSV-1.1.txt`](./Exportar%20empresas%20SAO-Gestion%20%28ITACA%29%20a%20CSV-1.1.txt) | SAO-Gestión (`@match *://*/*`) | Exporta todas las empresas del grid ZK a CSV bajo demanda. |
| [`Exportar empresas FCT a CSV-1.0.txt`](./Exportar%20empresas%20FCT%20a%20CSV-1.0.txt) | FCT (`@match *://*/index.php*`) | Recorre todas las páginas del listado de empresas FCT y exporta un CSV. |

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
