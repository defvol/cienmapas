---
layout: post
title:  "El COVID-19 en México por estados"
style: "mapbox://styles/mapbox/dark-v10"
source: "rodowi.2scq6zcv"
date:   2020-03-22 20:04:14 -0800
updated_at: 20200323
categories: posts
technologies:
- mapbox.js
- javascript
topics:
- covid
- mapbox
---

### Arte previo

Hasta la fecha, no he encontrado un buen _choropleth_ dinámico
de la situación del COVID-19 (coronavirus) en México.

Lo más cercano a un mapa dinámico (y que he encontrado como referencia
en varios medios) ha sido este buen mapa creado por Sismo Alerta
Mexicana usando Google Maps:

{% raw %}
<iframe src="https://www.google.com/maps/d/embed?mid=1-XnTNpU7R4XiVewJh_nwcpUrtGgd4gwu" width="640" height="480"></iframe>
{% endraw %}

Referencia: [Mapa avanzado en tiempo real de pandemia del COVID-19 en Mexico](https://www.google.com/maps/d/u/0/viewer?mid=1-XnTNpU7R4XiVewJh_nwcpUrtGgd4gwu&shorturl=1&ll=23.94570947621723%2C-100.96115414999997&z=5)

Sin embargo, busco algo menos saturado, un _choropleth_ limpio o
al menos agrupar esos _pins_ en _clusters_. Tambień tener algo de
control sobre la capa de estilos y finalmente tener la tabla de datos
abierta y fácil de editar desde GitHub.

### Los datos

La Secretaría de Salud publica [un infográfico estático en su comunicado
técnico diario](https://www.gob.mx/salud/prensa/nuevo-coronavirus-en-el-mundo-covid-19-comunicado-tecnico-diario-238709) de donde manualmente podemos extraer los datos (a falta de tiempo para un buen OCR).

## Mapa

### Metadata

- **proyecto**: COVID-19
- **code**: [https://github.com/defvol/cienmapas](https://github.com/defvol/cienmapas)
- **fuente**: [Secretaría de Salud](https://www.gob.mx/salud/prensa/nuevo-coronavirus-en-el-mundo-covid-19-comunicado-tecnico-diario-238709)
- **tecnologías**: {{ page.technologies | array_to_sentence_string }}
- **temas**: {{ page.topics | array_to_sentence_string }}


