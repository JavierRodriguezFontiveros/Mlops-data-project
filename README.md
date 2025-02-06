# Mlops-data-project


Proyecto Personal: Automatización de MLOps y Data Engineering

Introducción

Tras completar una formación intensiva en Data Science a través de un bootcamp, superar diversos retos en plataformas como Nuwe, y participar en competiciones de Kaggle en distintas vertientes del dato, he decidido emprender un proyecto personal que abarque de manera integral la automatización de procesos en MLOps y Data Engineering. Este desafío no solo pondrá a prueba mis conocimientos adquiridos, sino que también me permitirá enfrentarme a nuevos obstáculos y descubrir metodologías innovadoras en el campo de la ciencia de datos.

Objetivo

El objetivo principal de este proyecto es desarrollar una arquitectura escalable, automatizada y de bajo costo que permita la extracción, almacenamiento, procesamiento y modelado de datos, utilizando herramientas open-source y servicios gratuitos siempre que sea posible. Se busca predecir la evolución de los precios del aceite en Amazon mediante técnicas de series temporales.

Arquitectura y Tecnologías Utilizadas

1. Extracción de Datos (Web Scraping)

Herramientas: BeautifulSoup + requests (evita el alto consumo de Selenium).

Automatización: AWS Lambda con ejecuciones programadas o GitHub Actions.

Alternativa escalable: Scrapy con rotación de proxies.

2. Almacenamiento y Procesamiento

Base de datos: DynamoDB (NoSQL) para almacenamiento eficiente de producto, precio, categoría y fecha.

Alternativa para queries avanzadas: PostgreSQL (TimescaleDB) en Railway o AWS Free Tier.

3. API Backend

Framework: FastAPI para construir endpoints REST.

Endpoints clave:

/scraper: Ejecución del scraping manual o automática.

/data: Consulta de precios históricos.

/predict: Predicción de precios futuros.

/retrain: Reentrenamiento del modelo con nuevos datos.

Despliegue: Render o Railway con planes gratuitos.

4. Modelado de Series Temporales

Modelos utilizados:

Facebook Prophet (para predicciones rápidas y ajustables).

Alternativa: LSTM en TensorFlow si se requiere mayor precisión.

Entrenamiento: Google Colab Free o Hugging Face Spaces.

Seguimiento de modelos: DVC para versionado de datos y modelos.

5. Visualización de Datos y Dashboard

Tecnología: HTML + JS + Plotly Dash para flexibilidad y personalización.

Despliegue: Streamlit Cloud (alternativa gratuita) o Render.

6. Automatización y Orquestación

Scraping: AWS Lambda o cronjobs en GitHub Actions.

Pipelines de ML: Prefect (alternativa ligera a Airflow).

Contenedores: Docker para estandarizar ejecuciones.

Orquestación: Se evita Kubernetes inicialmente para reducir costos y complejidad.

Plan de Desarrollo y Seguimiento

Este proyecto evolucionará a medida que se vayan resolviendo los desafíos técnicos. Documentaré cada avance y obstáculo encontrado en este proceso, compartiendo actualizaciones en esta plataforma y en mi repositorio de GitHub.

Si deseas seguir el desarrollo en tiempo real, te invito a visitar mi repo: [GitHub Repository Link]

Este proyecto no solo consolidará mis habilidades en Data Engineering y MLOps, sino que también servirá como una referencia para otros entusiastas que quieran desarrollar soluciones escalables y automatizadas en el ámbito del Machine Learning.

# 📂📂📂

```bash
📂 mlops-data-project (Directorio raíz del proyecto)
│
├── 📂 data (Almacenamiento temporal de datos)
│ ├── raw/ (Datos crudos extraídos del scraping)
│ ├── processed/ (Datos limpios y listos para ML)
│ ├── models/ (Modelos entrenados y versiones anteriores)
│ ├── datasets/ (Datos históricos para análisis y predicción)
│
├── 📂 scraper (Código de web scraping con BeautifulSoup)
│ ├── scraper.py (Script principal para extraer datos)
│ ├── scraper_utils.py (Funciones auxiliares, headers, proxies...)
│ ├── requirements.txt (Dependencias de scraping: BeautifulSoup, requests...)
│
├── 📂 api (FastAPI para servir el backend)
│ ├── main.py (Punto de entrada de la API, define endpoints)
│ ├── routes.py (Módulo con rutas separadas para organización)
│ ├── models.py (Definición de esquemas Pydantic y base de datos)
│ ├── config.py (Configuraciones de la API y credenciales)
│ ├── requirements.txt (Dependencias del backend: FastAPI, Uvicorn...)
│
├── 📂 ml (Modelo de series temporales y entrenamiento)
│ ├── train.py (Código de entrenamiento del modelo Prophet/LSTM)
│ ├── predict.py (Carga el modelo y genera predicciones)
│ ├── evaluate.py (Métricas y evaluación del modelo)
│ ├── ml_utils.py (Funciones auxiliares de ML)
│ ├── requirements.txt (Dependencias: Prophet, TensorFlow, scikit-learn...)
│
├── 📂 dashboard (Interfaz para visualización de datos con Plotly Dash)
│ ├── app.py (Código principal del dashboard en Dash)
│ ├── layout.py (Diseño de la interfaz y gráficas)
│ ├── callbacks.py (Funciones interactivas del dashboard)
│ ├── requirements.txt (Dependencias: Dash, Plotly, Pandas...)
│
├── 📂 automation (Orquestación y ejecución de tareas automatizadas)
│ ├── pipeline.py (Pipeline de extracción, almacenamiento y ML con Prefect/Airflow)
│ ├── scheduler.py (Configuración de ejecución automática con AWS Lambda/GitHub Actions)
│ ├── dockerfile (Configuración de Docker para la ejecución del proyecto)
│ ├── k8s_deployment.yaml (Si en el futuro quieres usar Kubernetes)
│
├── 📂 tests (Pruebas unitarias y de integración)
│ ├── test_scraper.py (Tests para la extracción de datos)
│ ├── test_api.py (Tests para la API con pytest y FastAPI TestClient)
│ ├── test_ml.py (Tests para validación del modelo de predicción)
│
├── .gitignore (Archivos y carpetas a ignorar en GitHub, como modelos y credenciales)
├── README.md (Descripción del proyecto y documentación inicial)
├── docker-compose.yml (Si necesitas levantar servicios como la base de datos localmente)
├── config.yaml (Archivo de configuración global del proyecto)