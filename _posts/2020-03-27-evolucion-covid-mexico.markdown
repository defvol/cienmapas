---
layout: post
map_template: time
title:  "Evolución del COVID-19 en México"
style: "mapbox://styles/mapbox/dark-v10"
source: "rodowi.2scq6zcv"
date:   2020-03-27 10:04:14 -0800
updated_at: 2020-03-27
categories: posts
technologies:
- mapbox.js
- javascript
topics:
- covid
- mapbox
---

Después de pasar tiempo perdido en el [sitio de gob.mx destinado
al coronavirus](https://coronavirus.gob.mx/), finalmente [un tuit de @lobo_tuerto](https://twitter.com/lobo_tuerto/status/1242942200868212738) me hizo encontrar 2 iniciativas de la comunidad para traducir a formato estructurado los PDFs publicados por gobierno.

Tomando como referencia los [archivos .XLSX publicados por guzmart](https://github.com/guzmart/covid19_mex/issues/2) logré armar un script que:
1. Transforma la carpeta de datos en CSVs usando [xlsx2csv](https://github.com/dilshod/xlsx2csv), ver Fig 1.
2. Mezcla los CSVs en un JSON indexado por fechas, y de paso utiliza el
   [Marco Geoestadístico de INEGI](https://www.inegi.org.mx/temas/mg/) para nombrar los estados, y así
   hacerlos más fácil de asociar a geometrías (i.e. shapefiles). El
   resultado se puede ver en [series.json](https://github.com/defvol/cienmapas/tree/master/_data/covid/series.json) y el script en [covid19mx-to-jsonseries.js](https://gist.github.com/defvol/b802c12afb57557b7322b164ccf7970c).

```sh
find . -name '*.xlsx' | xargs -I {} xlsx2csv {} {}.csv | \
find . -name '*.xlsx.csv' | sed 'p;s/\.xlsx\.csv/\.csv/' | \
xargs -n2 mv
```
_Fig 1. Comando de shell para transformar todos los archivos .xlsx a .csv_

## Mapa

Usando como base la tasa de casos por población estatal que utilicé [en este post]({{ site.baseurl }}{% post_url
2020-03-24-covid-poblacion-mexico %}) logramos armar un mapa _choropleth_ con un _slider_ para visualizar la progresión de los casos a través del tiempo.

Es fácil notar como para el día 20 de marzo, la mayoría de los estados
reportaban casos. Resulta también de mi interés el incremento de casos
en BCS con relación al resto; uno puede ver como la intensidad de la
tasa aumenta para el día 27 de Marzo.

Cabe aclarar que existen ciertas inconsistencias en la
publicaciones de la Secretaría de Salud, como han sido expresadas por la comunidad en [[1]](https://github.com/guzmart/covid19_mex/issues/2) y [[2]](https://github.com/covidctdmx/covid_ctd_mx/issues/31); por lo pronto, tomemos estos ejercicios de visualización como un ejercicio meramente ilustrativo.
