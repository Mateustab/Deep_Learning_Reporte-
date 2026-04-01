# Detector de personas caídas  
## Deep_Learning_Reporte-  

Presentación de el trabajo final de la asignatura Deep Learning.  

## Contexto  
La seguridad y el bienestar de los adultos mayores o personas en rehabilitación requieren un monitoreo constante. Un problema crítico es la detección de caídas o situaciones donde una persona queda tendida en el piso sin poder levantarse. Motivado por una vivencia familiar reciente de caida nocturna de mi padre, decidi enfocar este proyecto a la detección de personas caídas.  

El proyecto se aborda como un problema de clasificación de imágenes multiclase.
El modelo debe clasificar una imagen capturada por una cámara en dos categorías: "Parado" o Acostado/Caído"
Al ser un entorno doméstico con datos limitados, se usara Transfer Learning para aprovechar el conocimiento de modelos pre-entrenados en grandes bases de datos como ImageNet.  

El dataset final se construyó mediante una de fusión de tres fuentes distintas para garantizar la representatividad de las dos clases de interés:
Clase "Caida": Las imágenes fueron obtenidas del repositorio de Kaggle "simuletic/cctv-incident-dataset-fall-and-lying-down-detection". Este conjunto proporciona capturas de cámaras de seguridad reales en entornos como tiendas, pasillos y exteriores, enfocándose en la cinemática de personas tendidas en el suelo.
Clase "Normal": Para representar actividades cotidianas, se utilizó el dataset Pascal VOC, extrayendo específicamente muestras donde la etiqueta del objeto es la 14 (correspondiente a 'person'). Además, según el historial del proyecto, se complementó esta clase con imágenes descargadas de Google Images para añadir variedad en contextos.
