Clasificador de caracteres manuales con CNN
Este repositorio contiene un script para entrenar y validar una red neuronal convolucional (CNN) capaz de reconocer letras manuscritas. A diferencia de otros proyectos que usan MNIST, este modelo fue probado con un dataset propio de letras "A", "B" y "C" para evaluar su desempeño con caligrafía real.

Herramientas utilizadas
TensorFlow y Keras: Construcción y entrenamiento de la red.

OpenCV: Tratamiento de imágenes y carga de archivos.

Scikit-learn: Generación del reporte de clasificación y métricas.

Matplotlib / Seaborn: Visualización de la matriz de confusión.

Metodología y Arquitectura
El modelo procesa imágenes de 64x64 píxeles en escala de grises. La estructura de la red se definió de la siguiente manera:

Extracción de características: Tres capas Conv2D con funciones de activación ReLU para detectar rasgos geométricos.

Reducción: Capas de MaxPooling2D después de las convoluciones para optimizar el cómputo.

Clasificación: Una etapa Flatten seguida de una capa Dense de 64 neuronas y una capa de salida Softmax para determinar la clase más probable.

Para el entrenamiento se utilizó el optimizador Adam y la función de pérdida sparse_categorical_crossentropy, adecuada para este tipo de clasificación multiclase.

Análisis de desempeño
El script incluye un bloque para generar una matriz de confusión al finalizar la validación. Esto permite identificar si el modelo tiene dificultades específicas entre caracteres similares, como la "A" y la "B", debido a trazos ambiguos en la escritura manual.

Instrucciones de uso
Instalar dependencias: pip install tensorflow opencv-python matplotlib seaborn scikit-learn

Organizar los datos en una carpeta llamada mi_dataset con subdirectorios para entrenamiento y validación.

Ejecutar el script principal para iniciar el entrenamiento y visualizar las métricas finales.

Retos técnicos resueltos
Normalización de datos: Se implementó un mapeo para convertir los valores de los píxeles al rango [0, 1], lo que estabilizó el entrenamiento.

Manejo de dataset propio: Se configuró el flujo de datos para leer directamente desde directorios locales, facilitando la expansión del modelo a más letras en el futuro.
