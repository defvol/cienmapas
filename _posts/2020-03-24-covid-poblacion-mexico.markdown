---
layout: post
title:  "El COVID-19 en México por población estatal"
style: "mapbox://styles/mapbox/dark-v10"
source: "rodowi.2scq6zcv"
date:   2020-03-24 20:04:14 -0800
updated_at: 2020-03-23
method: "by_population"
categories: posts
technologies:
- mapbox.js
- javascript
topics:
- covid
- mapbox
---

### Arte previo

En [el post anterior]({{ site.baseurl }}{% post_url
2020-03-22-covid-19-en-mexico %}) hicimos un primer mapa _choropleth_ tomando como referencia simplemente el número de casos.

Dado que no queremos desviar la atención de otros focos de infección, tal vez algo más justo sería determinar el color en base a el % de la
población infectada, como se ve a continuación.

## Mapa

Se calcula cobertura por estado como `casos / poblacion`, y el color del
estado entra en el rango (0, cobertura_maxima), donde la
cobertura_maxima es el estado con el peor caso.

A diferencia del mapa anterior, aquí toma más relevancia Quintana Roo y
Yucatán, y un poco menos Nuevo León, Jalisco, y CDMX (dada la densidad
poblacional).

### Metadata

- **proyecto**: COVID-19
- **code**: [https://github.com/defvol/cienmapas](https://github.com/defvol/cienmapas)
- **fuentes**: [Comunicado Técnico Diario de la Secretaría de Salud](https://www.gob.mx/salud/documentos/coronavirus-covid-19-comunicado-tecnico-diario-238449), [Marco Geoestadístico Estatal de INEGI](https://www.inegi.org.mx/temas/mg/)
- **última actualización**: {{ page.updated_at }}
- **tecnologías**: {{ page.technologies | array_to_sentence_string }}
- **temas**: {{ page.topics | array_to_sentence_string }}


