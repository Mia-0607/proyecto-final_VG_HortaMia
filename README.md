# ¿Cuándo dejó de ser normal el calor?

## Autora
Mia Ana Itzel Horta López

## Descripción del proyecto

Este proyecto analiza la evolución histórica de la temperatura global y en México para observar cómo ha cambiado el comportamiento térmico en las últimas décadas. A través de una narrativa visual interactiva creada con Quarto HTML, se comparan datos globales de anomalía de temperatura con registros nacionales y estatales de México.

La pregunta principal del proyecto es:

**¿Cuándo dejó de sentirse “normal” la temperatura en México y cómo se compara ese cambio con la tendencia global?**

## Herramienta utilizada

El proyecto fue desarrollado con **Quarto HTML**, usando Python para la limpieza, transformación y visualización de los datos. Las visualizaciones interactivas fueron creadas principalmente con Plotly.

## Fuentes de datos

| Fuente | Uso | URL | Fecha de descarga |
|---|---|---|---|
| NASA GISTEMP | Datos de temperatura global histórica | https://data.giss.nasa.gov/gistemp/ | 27/04/2026 |
| Data México - Temperaturas mensuales en México 1985-2025 | Datos mensuales de temperatura en México por entidad federativa | https://datamx.io/es/dataset/temperaturas-mensuales-en-mexico-1985-2025 | 27/04/2026 |
| Data México - División política de México en GeoJSON 2024 | GeoJSON de estados de México | https://datamx.io/es/dataset/division-politica-de-mexico-estatal-y-municipal-en-geojson-2024 | 27/04/2026 |
| Quarto | Herramienta utilizada para crear el sitio HTML interactivo | https://quarto.org/ | - |

## Estructura del proyecto

```text
proyecto-final_VG_HortaMia/
│
├── data/
│   ├── raw/
│   │   ├── estados_mexico.geojson
│   │   ├── temperatura_global.csv
│   │   └── temperatura_lluvias_mensual_mexico.csv
│   │
│   └── clean/
│       ├── comparacion_mexico_global.csv
│       ├── global_limpio.csv
│       ├── mapa_mexico_limpio.geojson
│       └── mexico_anual_limpio.csv
│
├── index_files/
├── index.qmd
├── index.html
└── README.md
```

## Instrucciones para ejecutar el proyecto localmente

1. Instalar Quarto desde la página oficial:

   https://quarto.org/

2. Instalar las librerías necesarias de Python:

   py -m pip install pandas geopandas plotly matplotlib jupyter pyyaml

3. Abrir la carpeta del proyecto en Visual Studio Code.

4. En la terminal, ejecutar:

    quarto preview index.qmd

5. Se abrirá una página local en el navegador donde se podrá visualizar el proyecto en formato HTML interactivo.


## Sitio publicado

El proyecto final puede consultarse en el siguiente enlace:

https://mia-0607.github.io/proyecto-final_VG_HortaMia/
    