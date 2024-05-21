# Generación de Imágenes de Tumores Cerebrales mediante Generative Adversarial Networks (GAN)

## 📘 Introducción

Este proyecto tiene como objetivo la **generación de imágenes de tumores cerebrales** utilizando **generative adversarial networks (GANs)**. Los tumores cerebrales son crecimientos anormales de células en el cerebro, que pueden ser benignos o malignos. En España, se detectan aproximadamente **5000 casos** de tumores cerebrales anualmente, subrayando la necesidad de métodos avanzados de generación de imágenes basados en **inteligencia artificial (IA)** con el fin de desarrollar otros algoritmos para la detección temprana de esta enfermedad.

## 🎯 Objetivos

- **Desarrollar y entrenar modelos GAN** para generar imágenes sintéticas de resonancias magnéticas (RM) del cerebro.
- **Evaluar la efectividad** de estos modelos en la captura de la distribución de probabilidad de las imágenes reales.
- **Comparar diferentes arquitecturas** de generadores y discriminadores dentro de los modelos GAN.

## 🗂️ Conjunto de Datos

El conjunto de datos utilizado está compuesto por **253 imágenes de resonancias magnéticas cerebrales**, divididas en dos clases:
- **YES**: 155 imágenes con tumores.
- **NO**: 98 imágenes sin tumores.

Las imágenes se han preprocesado redimensionándolas a **128x128 píxeles** y normalizándolas.

## 🧠 Modelos

### TUMORSYNTH 1

- **Generador**:
  - Arquitectura simple con capas densas y convolucionales transpuestas.
  - **Parámetros entrenables**: 27,848,066.
  - **Tamaño del ruido**: 100.
  - **Optimizador**: Adam con tasa de aprendizaje de 0.0002 y beta_1 de 0.5.
  - **Función de pérdida**: Entropía cruzada binaria.
  - **Número de Epochs**: 18.
  - **Mejor época**: 8.

- **Discriminador**:
  - Varias capas convolucionales con activación LeakyReLU y una capa de salida con activación sigmoide.
  - Incluye capas de aplanamiento y dropout.

### TUMORSYNTH 2

- **Generador**:
  - Arquitectura más sofisticada basada en un encoder-decoder.
  - **Parámetros entrenables**: 427,362,946.
  - **Tamaño del ruido**: 100.
  - **Optimizador**: Adam con tasa de aprendizaje de 0.0002 y beta_1 de 0.5.
  - **Función de pérdida**: Entropía cruzada binaria.
  - **Número de Epochs**: 30.
  - **Mejor época**: 27.

- **Discriminador**:
  - Similar al de TUMORSYNTH 1, pero con más capas y parámetros entrenables.

## 📊 Resultados

Los resultados indican que el modelo **TUMORSYNTH 2**, con su arquitectura más compleja, captura mejor la distribución de probabilidad de las imágenes reales. Sin embargo, puede sufrir de sobreajuste y no necesariamente genera imágenes visualmente más realistas comparadas con TUMORSYNTH 1.

## 📝 Conclusiones

- El modelo con generador basado en encoder-decoder (**TUMORSYNTH 2**) captura con mayor fidelidad la distribución de probabilidad de las imágenes reales.
- A pesar de esta precisión en la distribución, el **análisis visual** es crucial para evaluar la calidad y realismo de las imágenes generadas.
- Es necesario encontrar un **equilibrio** entre la complejidad del modelo y su capacidad de generalización para evitar el sobreajuste.

## 🔮 Trabajo Futuro

- **Evaluar los modelos** con métricas adicionales como **Inception Score** o **FID** para obtener más información.
- **Probar diferentes arquitecturas**, como generadores basados en **ResNet** o **Unet**.
- Ampliar el conjunto de datos con un mayor número de imágenes para mejorar el rendimiento de los modelos.

## Autoría

Este proyecto fue desarrollado por **Borja Esteve Molner** como parte del Máster en Inteligencia Artificial Avanzada y Aplicada.

