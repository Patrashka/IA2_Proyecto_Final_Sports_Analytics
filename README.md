# Sports Analytics using Deep Learning Models - AI II (UDEM)

Este repositorio contiene el desarrollo del proyecto final para la materia de **Inteligencia Artificial II** en la **Universidad de Monterrey**. El sistema consiste en un pipeline automatizado de visión por computadora que detecta jugadores de fútbol y el balón en tiempo real utilizando una toma aérea fija capturada por un dron en el Campus UDEM, generando analíticas visuales dinámicas por cuadro.

---

## Descripción del Proyecto
El núcleo del desarrollo utiliza la arquitectura **YOLOv8** de Ultralytics (detección de objetos de una sola etapa libre de anclas) entrenada localmente mediante transferencia de conocimiento a partir de un dataset de 576 (minimo) fotogramas extraídos de la secuencia original y etiquetados manualmente cuadro por cuadro en Roboflow. 

El pipeline no solo localiza los elementos, sino que implementa lógica analítica espacial calculando el centroide de cada objeto para determinar su posición exacta respecto a zonas reglamentarias fijas: mitad izquierda/derecha, áreas de penalti y fueras de banda, inyectando los indicadores directamente en la parte superior del video de salida.

---

## Requisitos del Entorno
* **Sistema Operativo:** Windows / Linux / macOS
* **Lenguaje:** Python >= 3.10
* **Aceleración por Hardware (Recomendado):** Tarjeta Gráfica NVIDIA con soporte CUDA para optimizar el rendimiento en paralelo. El entrenamiento base se completó utilizando una GPU **NVIDIA GeForce RTX 5070**, reduciendo el tiempo por época de 2.5 minutos (en CPU) a solo 8 segundos.

---

## Instalación y Configuración

Sigue estos pasos para clonar el repositorio e instalar todas las dependencias necesarias en tu entorno local:

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/TU_USUARIO/TU_REPOSITORIO.git](https://github.com/TU_USUARIO/TU_REPOSITORIO.git)
   cd TU_REPOSITORIO

## Crear un entorno virtual para contener el modelo (opcional)
  python -m venv venv
  # En Windows:
    venv\Scripts\activate
  # En Linux/macOS:
    source venv/bin/activate

## Instalar las dependencias requeridas:
pip install -r requirements.txt
