# 📌 Machine-Learning
Se aplican modelos de Machine Learning para predecir condiciones meteorológicas basadas en datos históricos obtenidos de Open-Meteo. El conjunto de datos incluye variables meteorológicas como temperaturas, precipitaciones, duración del sol, velocidad del viento, entre otras. La variable objetivo (weather_code) representa códigos de tiempo según ciertas condiciones meteorológicas.

# 🧩 ¿Qué hace el proyecto?
Este proyecto utiliza datos meteorológicos diarios para predecir la variable weather_code mediante un modelo de basado en Random Forest y otro en Neural Netwoks. 

En el proyecto se divide en 5 secciones:

* En la sección 1 se extraen los datos de las variables meteorológicas de Open-Meteo en https://open-meteo.com/. Para extraer los datos es necesario otorgar parámetros como la ubicación y el rango de tiempo que se desea.

* En la sección 2 se hace un tratamiento del data frame donde se eliminan las columnas con varibles vacías (0 non-null) y se crea un nuevo data frame sin dichas columnas.

* En la sección 3 se entrena un modelo de clasificación Random Forest para predecir el valor de la columna weather_code del conjunto de datos meteorológicos. Se crea un data frame en el cual se quitan las columnas time y precipitation_sum. Dado que la columna time puede incurrir en errores por el tipo de dato (datetime64[ns]), además por ahora no nos interesa saber en qué fecha ocurre alguno de los weather_code. Asimismo, precipitation_sum, ya que es la suma de las precipitaciones diarias, incluidas: lluvias, chubascos y nevadas). Luego de esto, se dividen los datos en 80% para entrenamiento y 20% para prueba, luego se crea y se entrena el modelo con 100 árboles de decisión.

* En la sección 4 se implementa y entrena un modelo de red neuronal en Keras para predecir la variable weather_code a partir del conjunto de datos meteorológicos. De manera similar a la sección 3, se crea un nuevo data frame sin las columnas time y precipitation_sum. Para este modelo, primero se separan las variables predictoras (X) y la variable objetivo (y). Seguidamente, se divide el conjunto de datos en 80% para entrenamiento y 20% para prueba, y las variables de entrada se escalan para que tengan media 0 y desviación estándar 1. Y se crea el modelo con 2 capas ocultas 
y 1 capa de salida (con tantas neuronas como clases tenga weather_code).

* La sección 5 se centra en predecir el código meteorológico (weather_code) a partir de variables numéricas y temporales, es decir, se busca predecir si un día presenta lluvia ligera (weather_code == 61) o no. Para este caso se utiliza la columna time del data frame inicial, se debe tener en cuenta que el modelo no puede otorgar una fecha exacta como salida. Así que se predece en qué fechas es probable que ocurra cierto tipo de clima, en este caso, weather_code == 61.

# 🌤️ ¿Por qué el proyecto es útil?
Este proyecto aborda una necesidad crítica: estimar condiciones climáticas a partir de variables físicas accesibles. Utilizando modelos de aprendizaje automático como Random Forest y redes neuronales, permite predecir el estado del clima (weather_code) con base en datos meteorológicos diarios reales. Esta capacidad resulta clave para la toma de decisiones en sectores sensibles al clima como la agricultura, la gestión de recursos hídricos, la logística y los sistemas de alerta temprana frente a eventos extremos.

Además, al emplear datos históricos (2005–2025) y técnicas de preprocesamiento robustas se sienta las bases para modelos predictivos personalizados o integraciones futuras con datos en tiempo real. Así, se convierte en una herramienta valiosa tanto para aplicaciones prácticas como para la investigación científica en climatología local y cambio climático.

# 🚀 ¿Cómo pueden comenzar los usuarios con el proyecto?
Los usuarios pueden comenzar con este proyecto siguiendo estos pasos básicos:

1. Descargar los datos climáticos: El proyecto usa datos históricos de la API de Open-Meteo, que son gratuitos y accesibles sin autenticación. Solo deben definir la ubicación (latitud/longitud), rango de fechas y variables deseadas.

2. Ejecutar el código en Google Colab o Jupyter Notebook: El código está pensado para correr en entornos interactivos. Solo necesitan tener instaladas bibliotecas como pandas, scikit-learn, matplotlib, tensorflow y seaborn.

3. Entrenar los modelos: Con los datos descargados y preprocesados, los usuarios pueden ejecutar las celdas para entrenar tanto el modelo de Random Forest como la red neuronal.

4. Interpretar resultados: El proyecto genera automáticamente métricas como precisión, matriz de confusión y curvas de pérdida y precisión. Estas visualizaciones ayudan a entender cómo se desempeña el modelo y en qué clases es más o menos preciso.

5. Probar predicciones por fecha: Finalmente, se puede usar el modelo entrenado para predecir el código climático de un día específico, aplicando el preprocesamiento adecuado.

# 📫 ¿Dónde pueden recibir ayuda los usuarios con tu proyecto?
Si requiere ayuda con el proyecto o tiene dudas al respecto, puede escribir al e-mail: ana.ruizn@udea.edu.co

# 🤝 ¿Quién mantiene y contribuye con el proyecto?
Ana Luz Ruiz Noriega
