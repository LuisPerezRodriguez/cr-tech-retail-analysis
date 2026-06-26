# Análisis del Mercado Retail de Hardware frente a la IA en Costa Rica (`cr-tech-retail-analysis`)

## 📌 Descripción
Este proyecto implementa un pipeline de Ingeniería de Datos bajo la arquitectura **Medallion** para extraer, unificar y analizar diariamente el catálogo de los dos principales distribuidores de hardware tecnológico en Costa Rica: **ExtremeTech** e **Intelec**.

El objetivo es evaluar cómo responden estas plataformas locales (estrategias de precios, gestión de stock antiguo y adopción de tecnologías nuevas) en una era global donde los fabricantes priorizan el silicio para entornos corporativos de Inteligencia Artificial en detrimento del consumidor retail.

## 🛠️ Alcance del Proyecto
Para evitar ruido analítico, el pipeline se concentra exclusivamente en tres componentes core fuertemente impactados por la IA:
* **GPUs (Tarjetas Gráficas):** Monitoreo de VRAM, arquitecturas y stock.
* **CPUs (Procesadores):** Identificación de nuevas generaciones con NPU vs. tradicionales.
* **RAM (Memorias):** Transición de velocidades y capacidades orientadas a cómputo local.

## 🏗️ Arquitectura Propuesta (MVP Local-First)
El proyecto está diseñado bajo un enfoque de desarrollo local gratuito con miras a escalar a un servidor propio (`On-Premise` en Linux):
1. **Capa Bronze (Extracción):** Scripts diarios en Python (`BeautifulSoup`/`Requests`) que guardan capturas crudas en formato JSON.
2. **Capa Silver (Estandarización):** Procesamiento en **PySpark** local para limpiar, tipar y unificar los esquemas de ambas tiendas en un formato estándar.
3. **Capa Gold (Analítica):** Modelado en esquema estrella utilizando **Dimensiones de Cambio Lento (SCD Tipo 2)** para medir la volatilidad de precios y rotación de inventario en el tiempo.

---
*Proyecto de graduación para el Bootcamp de Ingeniería de Datos - 2026.*
