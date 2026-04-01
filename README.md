# Detector de personas caídas  
## Deep_Learning_Reporte-  

**Al ejecutar el notebook, cambiar a entorno de ejecucion GPU T4**.  

"Es importante mencionar que debido a la naturaleza no determinista del entrenamiento en entornos de computación paralela (GPU) y la optimización de algoritmos de convolución en TensorFlow,  existen  variaciones en las métricas cada vez que se entrena los modelos. Factores como la inicialización aleatoria de pesos, el uso de capas de Dropout y la optimización de operaciones atómicas en la arquitectura CUDA  introducen variaciones marginales. Para mitigar solo un poco este efecto, se han fijado alguna semillas.

Presentación de el trabajo final de la asignatura Deep Learning.  

## Contexto  
La seguridad y el bienestar de los adultos mayores o personas en rehabilitación requieren un monitoreo constante. Un problema crítico es la detección de caídas o situaciones donde una persona queda tendida en el piso sin poder levantarse. Motivado por una vivencia familiar reciente de caida nocturna de mi padre, decidi enfocar este proyecto a la detección de personas caídas.  

El proyecto se aborda como un problema de clasificación de imágenes multiclase.
El modelo debe clasificar una imagen capturada por una cámara en dos categorías: "Parado" o Acostado/Caído"
Al ser un entorno doméstico con datos limitados, se usara Transfer Learning para aprovechar el conocimiento de modelos pre-entrenados en grandes bases de datos como ImageNet.  

El dataset final se construyó mediante una de fusión de tres fuentes distintas para garantizar la representatividad de las dos clases de interés:
Clase "Caida": Las imágenes fueron obtenidas del repositorio de Kaggle "simuletic/cctv-incident-dataset-fall-and-lying-down-detection". Este conjunto proporciona capturas de cámaras de seguridad reales en entornos como tiendas, pasillos y exteriores, enfocándose en la cinemática de personas tendidas en el suelo.
Clase "Normal": Para representar actividades cotidianas, se utilizó el dataset Pascal VOC, extrayendo específicamente muestras donde la etiqueta del objeto es la 14 (correspondiente a 'person'). Además, según el historial del proyecto, se complementó esta clase con imágenes descargadas de Google Images para añadir variedad en contextos.

## Conclusión  

- Los resultados finales de este estudio demuestran la superioridad técnica del Transfer Learning sobre el entrenamiento desde cero para la detección de incidentes, Las arquitecturas que aprovecharon el conocimiento previo de ImageNet superaron al CNN_Scratch.  
- El mejor modelo con mejor desempeño fue es el ResNet50, el cual alcanzó una precisión de validación del 98% con la pérdida más baja registrada.  
- A pesar de las métricas sobresalientes obtenidas durante la fase de entrenamiento, una validación externa con imágenes fuera del dataset original reveló comportamientos divergentes en los modelos. Cada vez que se entrenaba los modelos los resultados eran muy diferentes para aquellas imagenes externas. Unas veces los modelos eran buenas solo detectando personas de pie y otras veces eran buenos solo detectando personas caídas. Estos resultados subrayan la necesidad de robustecer el dataset con una mayor diversidad de fondos, ángulos de cámara y variaciones de iluminación para mejorar la capacidad de generalización en entornos reales, es decir, tener un dataset mas amplio ya que 271 imagenes no son suficiente. En un sistema de salud, a veces es preferible un falso positivo (una alarma falsa) que un falso negativo (una caída no detectada)
