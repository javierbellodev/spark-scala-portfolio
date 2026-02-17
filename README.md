# Portafolio — spark-scala-portfolio

<p align="center">
  <img src="https://www.scala-lang.org/resources/img/scala-logo.png" alt="Scala" width="140" />
  &nbsp;&nbsp;
  <img src="https://spark.apache.org/images/spark-logo-trademark.png" alt="Apache Spark" width="200" />
</p>

## Descripción
Este repositorio es un portafolio de ejercicios y prácticas centradas en Scala y Apache Spark, pensado para aprendizaje y demostración de conceptos fundamentales de programación funcional, colecciones, pattern matching y uso de Spark desde notebooks. Incluye notebooks, datos de ejemplo, y archivos para ejecutar entornos basados en Docker (Jupyter / Spark).


## Objetivos
- Reunir ejercicios y notas de aprendizaje en Scala y Spark.
- Proveer notebooks reproducibles para estudiar conceptos clave.
- Facilitar reproducibilidad del entorno mediante Docker.

## Estructura del proyecto
- `docker-compose.yml` — Orquesta servicios (Jupyter / Spark) para ejecutar los notebooks.
- `Dockerfile.jupyter` — Imagen para el servidor Jupyter (entorno de notebooks).
- `Dockerfile.spark` — Imagen base para servicios Spark si aplica.
- `download_deps.sh` / `download_deps.ps1` — Scripts para descargar dependencias (Linux/macOS y PowerShell).
- `deps/` — Dependencias adicionales (ej. coursier) usadas por los ejemplos.
- `data/` — Datos de ejemplo usados en los notebooks:
  - `product_sale_sample.json`
  - `product_stock_sample.csv`
- `notebooks/` — Colección de notebooks Jupyter con contenido didáctico y ejercicios:
  - `00_fundamentals.ipynb` — Fundamentos de Scala.
  - `01_collections.ipynb` — Colecciones en Scala.
  - `02_functional_programming.ipynb` — Programación funcional.
  - `03_pattern_matching.ipynb` — Pattern matching.
  - `04_scala_spark.ipynb` — Introducción a Scala + Spark.
  - `Semana1_Porfolio.ipynb`, `Semana2_Porfolio.ipynb` — Notebooks del portafolio semanal.
  - `data/` — Copia de datos usada directamente por algunos notebooks.

## Descripción de carpetas y archivos relevantes
- notebooks/: Contiene las prácticas y explicaciones en formato Jupyter. Son el corazón del portafolio.
- data/: Contiene muestras de datos que permiten ejecutar los notebooks sin necesidad de fuentes externas.
- deps/: Herramientas y utilidades (por ejemplo, `coursier`) para manejar dependencias Scala/Java.
- Dockerfiles y `docker-compose.yml`: Permiten levantar un entorno reproducible con Jupyter y Spark, evitando configurar localmente Java/Scala/Spark.

## Requisitos previos
- Docker y Docker Compose instalados (recomendado para reproducibilidad).
- (Opcional) Java/Scala/SBT si desea ejecutar ejemplos fuera del contenedor.

## Cómo empezar (How to start)
Sigue estas instrucciones para ejecutar el entorno de notebooks con Docker Compose.

1) Construir las imágenes (desde la raíz del proyecto):

```bash
docker-compose build
```

2) Levantar los servicios (Jupyter / Spark):

```bash
docker-compose up -d
```

3) Ver los logs y obtener la URL/token de Jupyter (si aplica):

```bash
docker-compose logs -f
# o para ver solo jupyter:
# docker-compose logs -f jupyter
```

4) Abrir el navegador en la dirección que indique el contenedor (usualmente `http://localhost:8888`) y navegar a la carpeta `notebooks/`.

5) Abrir y ejecutar los notebooks en orden para seguir el material: empezar por `00_fundamentals.ipynb` y avanzar.


Si prefieres ejecutar los notebooks localmente sin Docker:
- Asegúrate de tener Jupyter instalado (`pip install notebook` o `pip install jupyterlab`).
- Instala Java/Scala/Spark si los notebooks lo requieren.
- Inicia Jupyter desde la raíz del proyecto y abre `notebooks/`:

```bash
jupyter lab
```

## Notas finales
- Los datos de ejemplo están en `data/` para que los notebooks sean reproducibles.
- Para actualizar o agregar notebooks, edítalos en `notebooks/` y añade nuevas entradas al portafolio.

## Agradecimientos
Quiero expresar mi agradecimiento al profesor **Mario Renau Arce** de la **EOI** por su excepcional guía, claridad en las explicaciones y constante apoyo durante el curso. Sus enseñanzas y orientación han sido fundamentales para la elaboración de este portafolio y para mi progreso en Scala y Spark. Gracias por inspirar un enfoque práctico y riguroso en el aprendizaje.
