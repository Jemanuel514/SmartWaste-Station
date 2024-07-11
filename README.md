# NeuroEcoWasteSolutions
En este espacio se sube el código creado para el grupo 

Se debe agregar toda la documentación que ustedes consideren pertinente para la compresión de los modelos usados, la ejecución del código y los resultados obtenidos. 
Puden, si desean, agregar imágenes o resultados obtenidos. 

Recuerden que este readme es su puerta de entrada para su proyecto. 

Un ejemplo puede ser: 
# Nombre del Proyecto

Breve descripción del proyecto.

## Tabla de contenidos

1. [Nombre](#Nombre)
2. [Descripción](#descripción)
3. [Arquitectura](#Arquitectura)
4. [Proceso](#Proceso)
5. [Funcionalidades](#Funcionalidades)
6. [Estado del proyecto](#EstadoDelProyecto)
7. [Agradecimientos](#Agradecimientos)


* Nombre del proyecto

* Breve descripción del proyecto -> Alguna imagen o gif que muestre el proyecto

* Arquitectura del proyecto + imagen
    El proyecto sigue una arquitectura de transferencia de aprendizaje. Primero, desarrollamos y entrenamos un modelo de clasificación de imágenes usando el dataset CIFAR-10. Luego, utilizamos este modelo preentrenado y ajustamos las últimas capas para adaptarlo a la tarea de clasificar imágenes de basura en cuatro categorías.


    Arquitctura del modelo CIFAR-10

    ![Arquitectura del modelo CIFAR-10](Img/model_architecture2.png)
    



    Arquitectura del modelo Principal

    ![Arquitectura del modelo principal](Img/model_architecture1.png)

* Proceso de desarrollo:

- Fuente del dataset
    El dataset utilizado para el proyecto se encuentra en el directorio 4Clases/, que contiene subdirectorios para cada una de las cuatro clases de imágenes.
    Este es la combinación de 3 datasets diferentes, los cuales son:
        * https://www.kaggle.com/datasets/mostafaabla/garbage-classification
        * https://www.kaggle.com/datasets/farzadnekouei/trash-type-image-dataset
        * https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2
    A su vez se utilizo el dataset cifar10 para el entrenamiento del modelo base que posteriormente se utilizo para entrenar el modelo principal.

- Limpieza de datos (img que lo valide)
    Se normalizaron los datos de imágenes utilizando z-score (media y desviación estándar). Aqui se muestra una imagen despues de la normalizacion:
    

    
    CIFAR-10
    ![Imagen normalizada del modelo CIFAR-10](Img/image2.png)
    Modelo Principal
    ![Imagen normalizada del modelo principal](Img/image1.png)





- Manejo excepciones/control errores
- ¿Qué modelo de Machine Learning están usando?
    Modelo CIFAR-10
    Primero, desarrollamos y entrenamos un modelo de clasificación de imágenes usando el dataset CIFAR-10. La arquitectura del modelo es la siguiente:

    - Capa de Convolución: Se utilizan múltiples capas de convolución con activaciones ReLU y regularización L2.
    - Capa de Agrupamiento: Se aplican capas de MaxPooling para reducir la dimensionalidad.
    - Batch Normalization: Se normalizan las salidas de las capas de convolución.
    - Dropout: Se usan capas de Dropout para prevenir el sobreajuste.
    - Capas Densas: Finalmente, el modelo tiene capas densas con activación ReLU y una capa de salida con activación softmax para las 10 clases de CIFAR-10.

    El modelo se entrenó con técnicas de aumento de datos y callbacks como detención temprana y reducción de la tasa de aprendizaje. Tras el entrenamiento, el modelo se guardó como cifar10.h5.


    Modelo de Clasificación de Basura
    Usamos el modelo CIFAR-10 preentrenado y ajustamos las últimas capas para clasificar imágenes de basura en cuatro categorías. La arquitectura del modelo es la siguiente:

    - Carga del Modelo Preentrenado: Se carga el modelo CIFAR-10 entrenado por nosotros.
    - Congelación de Capas: Se congelan todas las capas excepto las últimas cinco para conservar las características aprendidas del CIFAR-10.
    - Ajuste de las Últimas Capas:
        -Capa Densa Adicional: Se agrega una capa densa con 256 neuronas y activación ReLU.
        -Capa de Salida: Se agrega una capa de salida con activación softmax para las cuatro clases de basura.
    - Compilación del Modelo: El modelo se compila con el optimizador Adam y la función de pérdida categorical_crossentropy.
    - Entrenamiento del Modelo: Se entrena el modelo con el conjunto de datos de basura, utilizando técnicas de detención temprana y reducción de la tasa de aprendizaje.
    - Evaluación del Modelo: Se evalúa el modelo en un conjunto de prueba separado, calculando la precisión global.

- Estadísticos (Valores, gráficos, …)

- Métrica(s) de evaluación del modelo
    El modelo se evalúa utilizando la precisión, obteniendo una precisión global del {valor}%.




* Funcionalidades extra:

Ejem 1: Implementación de chatbot
- Tecnología/Herramientas usadas (Librería, Framework, …)
- Arquitectura (img)
- Indicar fuente del dataset
- Limpieza de datos (ejem: se usó PLN + img que lo validen)
- Manejo excepciones/control errores
- En caso de usar un modelo de ML indicar ¿Qué modelo de Machine Learning están usando?
- Estadísticos (Valores, gráficos, …)
- Métrica(s) de evaluación del modelo

Ejem 2: Integración del proyecto en una pág web
- Tecnología/Herramientas usadas …
- Arquitectura (img)

Ejem 3: Integración del proyecto en un canal WhatsApp, Discord, Telegram, Correo, …
- Tecnología/Herramientas usadas …
- Arquitectura (img)

Ejem 4: Desarrollo de interfaz gráfica de usuario
- Tecnología/Herramientas usadas …
- Arquitectura (img)

Ejem …: …
- Tecnología/Herramientas usadas …