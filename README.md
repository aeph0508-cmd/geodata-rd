# geodata-rd

Límites y toponimia de las 32 provincias de República Dominicana (31 provincias + Distrito Nacional) en formato GeoJSON, para uso en R, QGIS y análisis de vigilancia epidemiológica.

## Archivos

| Archivo | Geometría | Descripción |
|---|---|---|
| `provincias_rd.geojson` | Polígonos | Límites provinciales. Base para mapas coropléticos. |
| `toponimia_provincias_rd.geojson` | Puntos | Un punto por provincia, ubicado dentro de su polígono, para etiquetar nombres. |

## Campos

| Campo | Descripción |
|---|---|
| `COD_PROV` | Código de provincia (01 Distrito Nacional – 32 Santo Domingo) |
| `PROVINCIA` | Nombre en mayúsculas, para unir con bases de datos |
| `NOMBRE` | Nombre con tildes, para etiquetas |
| `N_MUNICIPIOS` | Número de municipios de la provincia |

Sistema de referencia: WGS84 (EPSG:4326).

## Uso en R

```r
library(sf)
url <- "https://raw.githubusercontent.com/aeph0508-cmd/geodata-rd/main/"
provincias <- st_read(paste0(url, "provincias_rd.geojson"))
toponimia  <- st_read(paste0(url, "toponimia_provincias_rd.geojson"))
```

## Fuente

Adaptado de jeasoft/provinces_geojson (GitHub): geometría simplificada, nombres corregidos y códigos provinciales añadidos.

Elaborado por Armilkis Paulino.
