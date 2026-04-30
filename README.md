# ¿Cuándo dejó de ser normal el calor?

## Autora

Mia Ana Itzel Horta López

## Descripción del proyecto

Este proyecto presenta una narrativa visual interactiva sobre la evolución de la temperatura histórica global y en México. El objetivo es mostrar cómo el calentamiento no ocurre como un cambio aislado, sino como una tendencia que puede observarse en diferentes escalas: primero en México, después en el contexto global y finalmente en la distribución territorial del calor.

La pregunta principal del proyecto es:

**¿Cuándo dejó de sentirse “normal” la temperatura en México y cómo se compara ese cambio con la tendencia global?**

A través de visualizaciones interactivas, el sitio permite observar el aumento de la temperatura media anual en México, comparar las anomalías de temperatura mexicanas con las globales, explorar cómo cambia la temperatura por entidad federativa y revisar un mapa mundial de temperatura media por país.

El proyecto fue desarrollado como un artículo de datos, no como un dashboard. Por ello, las gráficas están integradas dentro de una narrativa que guía al lector de una pregunta inicial hacia una interpretación final.

## Herramienta utilizada

El proyecto fue desarrollado con **Quarto HTML**, usando **Python** para la carga, limpieza, transformación y visualización de los datos.

Las visualizaciones interactivas fueron creadas principalmente con **Plotly**, mientras que el manejo del GeoJSON de México se realizó con **GeoPandas**. La publicación del sitio se realizó mediante **GitHub Pages**.

## Visualizaciones incluidas

El sitio contiene las siguientes visualizaciones principales:

1. **Temperatura media anual en México**  
   Muestra cómo ha cambiado la temperatura media nacional desde 1985 hasta 2025.

2. **Contexto global: anomalías de temperatura**  
   Presenta la anomalía de temperatura global anual usando datos de NASA GISTEMP.

3. **México frente al mundo**  
   Compara la anomalía de temperatura de México con la anomalía global.

4. **Temperatura media anual por estado en México**  
   Mapa interactivo con animación temporal para observar la temperatura media por entidad federativa entre 1985 y 2025.

5. **Temperatura media anual por país**  
   Mapa mundial interactivo con animación temporal para explorar la temperatura media anual por país entre 1900 y 2013.

## Fuentes de datos

| Fuente | Uso | URL | Fecha de descarga |
|---|---|---|---|
| NASA GISTEMP | Datos de anomalía de temperatura global histórica | https://data.giss.nasa.gov/gistemp/ | 27/04/2026 |
| Data México - Temperaturas mensuales en México 1985-2025 | Datos mensuales de temperatura mínima, media y máxima en México por entidad federativa | https://datamx.io/es/dataset/temperaturas-mensuales-en-mexico-1985-2025 | 27/04/2026 |
| Data México - División política de México en GeoJSON 2024 | Archivo GeoJSON usado para construir el mapa de entidades federativas de México | https://datamx.io/es/dataset/division-politica-de-mexico-estatal-y-municipal-en-geojson-2024 | 27/04/2026 |
| Kaggle - Global Land Temperatures by Country | Datos históricos de temperatura media por país para construir el mapa mundial | https://www.kaggle.com/datasets/vijayvvenkitesh/global-land-temperatures-by-country | 29/04/2026 |
| Quarto | Herramienta utilizada para crear el sitio HTML interactivo | https://quarto.org/ | - |

## Estructura del proyecto

```text
proyecto-final_VG_HortaMia/
│
├── _quarto.yml
├── .gitignore
├── index.qmd
├── metodologia.qmd
├── README.md
├── styles.css
│
└── data/
    ├── raw/
    │   ├── estados_mexico.geojson
    │   ├── temperatura_global.csv
    │   ├── temperatura_lluvias_mensual_mexico.csv
    │   └── GlobalLandTemperaturesByCountry.csv
    │
    └── clean/
        ├── comparacion_mexico_global.csv
        ├── global_limpio.csv
        ├── mapa_mexico_limpio.geojson
        ├── mexico_anual_limpio.csv
        ├── mapa_mexico_anual_limpio.geojson
        └── paises_anual_limpio.csv

```

## Descripción de archivos principales

| Archivo o carpeta | Descripción                                                                           |
| ----------------- | ------------------------------------------------------------------------------------- |
| `index.qmd`       | Página principal del sitio. Contiene la narrativa visual y las gráficas interactivas. |
| `metodologia.qmd` | Página secundaria con la metodología, limpieza, transformación y decisiones técnicas. |
| `_quarto.yml`     | Archivo de configuración del sitio Quarto.                                            |
| `styles.css`      | Archivo de estilos visuales personalizados del sitio.                                 |
| `data/raw/`       | Carpeta con los datos originales descargados.                                         |
| `data/clean/`     | Carpeta con los datos limpios generados por el proyecto.                              |
| `_site/`          | Carpeta generada automáticamente por Quarto con el sitio HTML final.                  |

## Instrucciones para ejecutar el proyecto localmente

1. Instalar Quarto desde la página oficial:

   https://quarto.org/

2. Instalar Python.

3. Instalar las librerías necesarias de Python:

   py -m pip install pandas geopandas plotly matplotlib jupyter pyyaml

4. Abrir la carpeta del proyecto en Visual Studio Code.

5. En la terminal, ejecutar:

   quarto preview

6. Se abrirá una página local en el navegador donde se podrá visualizar el proyecto en formato HTML interactivo.

## Instrucciones para generar el sitio HTML

Para generar la versión final del sitio, ejecutar:

   quarto render

Esto creará o actualizará la carpeta _site/, donde se encuentran los archivos HTML finales del proyecto.

## Sitio publicado

El proyecto final puede consultarse en el siguiente enlace:

   https://mia-0607.github.io/proyecto-final_VG_HortaMia/


## Notas metodológicas

El proyecto separa la narrativa visual del proceso técnico. La página principal presenta la historia y los hallazgos principales, mientras que la página de metodología documenta el procesamiento de datos, las transformaciones realizadas y las decisiones de diseño.

El mapa mundial no utiliza un archivo GeoJSON descargado por separado. La geometría base de los países es generada internamente por Plotly mediante locationmode="country names", usando los nombres de países del archivo GlobalLandTemperaturesByCountry.csv.