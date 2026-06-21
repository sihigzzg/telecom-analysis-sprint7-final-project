📊 Análisis Exploratorio y Segmentación de Clientes de Telecomunicaciones LATAM

Descripción del Proyecto

Este proyecto desarrolla un proceso completo de análisis exploratorio de datos (EDA), limpieza, transformación y segmentación de clientes utilizando información de una empresa de telecomunicaciones en Latinoamérica.

El objetivo principal es comprender los patrones de uso de los clientes, identificar problemas de calidad en los datos, analizar diferencias entre planes de servicio y generar segmentos que apoyen la toma de decisiones comerciales.

El análisis fue realizado en Python mediante un notebook de Jupyter y constituye una práctica integral de manipulación de datos con Pandas, visualización estadística y análisis descriptivo.

⸻

🎯 Objetivos

* Analizar la calidad de los datos y detectar valores faltantes.
* Identificar patrones de uso de llamadas, mensajes y consumo de servicios.
* Comparar el comportamiento de usuarios entre diferentes planes.
* Aplicar técnicas de limpieza e imputación de datos.
* Detectar valores atípicos mediante métodos estadísticos.
* Generar variables derivadas y métricas agregadas por usuario.
* Construir segmentos de clientes para apoyar estrategias de negocio.

⸻

📂 Datasets Utilizados

users_latam.csv

Contiene información demográfica y de suscripción de los usuarios.

Variables principales:

* user_id
* age
* city
* region
* plan

⸻

usage.csv

Contiene el detalle de uso de servicios de telecomunicaciones.

Variables principales:

* user_id
* date
* type
* duration
* length

Donde:

* call representa llamadas.
* text representa mensajes SMS.
* duration almacena duración de llamadas.
* length almacena longitud de mensajes.

⸻

plans.csv

Contiene la información de los planes ofrecidos por la compañía.

Variables principales:

* Nombre del plan.
* Beneficios incluidos.
* Límites de consumo.
* Tarifas asociadas.

⸻

🔍 Etapas del Análisis

1. Carga y exploración inicial

Se importaron los datasets utilizando Pandas y se realizó una inspección inicial mediante:

head()
info()
describe()

Se verificaron:

* Tipos de datos.
* Valores faltantes.
* Cardinalidad.
* Distribuciones iniciales.

⸻

2. Diagnóstico de calidad de datos

Se identificaron:

* Valores nulos.
* Valores centinela.
* Registros inconsistentes.
* Fechas sospechosas.
* Variables con alta cardinalidad.

También se analizaron patrones de ausencia utilizando:

isna()
groupby()
mean()

para distinguir entre:

* MCAR
* MAR
* Missing estructural

⸻

3. Limpieza de datos

Se realizaron tareas como:

Conversión de tipos

pd.to_numeric()
pd.to_datetime()

Estandarización de texto

str.strip()
str.lower()

Tratamiento de valores faltantes

* Imputación por media.
* Imputación por mediana.
* Eliminación de registros cuando fue necesario.

Reemplazo de sentinels

Ejemplos:

-999
999
?

⸻

4. Ingeniería de Variables

Se construyeron variables auxiliares para resumir información por usuario.

Ejemplo:

usage["is_text"]
usage["is_call"]

Posteriormente se agregaron métricas mediante:

groupby()
agg()

para obtener:

* Total de mensajes.
* Total de llamadas.
* Duración acumulada.

⸻

5. Estadística Descriptiva

Se calcularon medidas de:

Tendencia Central

* Media
* Mediana

Dispersión

* Desviación estándar
* Rango intercuartílico (IQR)

Distribución

* Frecuencias absolutas
* Frecuencias relativas

⸻

6. Visualización de Datos

Se utilizaron las librerías:

* Matplotlib
* Seaborn

Visualizaciones desarrolladas:

Histogramas

Para analizar:

* Edad
* Duración de llamadas
* Longitud de mensajes

Boxplots

Para detectar valores atípicos y estudiar dispersión.

Comparaciones por plan

Mediante:

hue="plan"

⸻

7. Detección de Outliers

Se implementaron dos metodologías:

Método IQR

Q1
Q3
IQR

Método Z-Score

z = (x - media) / desviacion

Identificando observaciones extremas que podrían afectar los análisis.

⸻

8. Segmentación de Clientes

Se generaron segmentos utilizando:

* Edad.
* Cantidad de uso.
* Tipo de plan.
* Consumo total.

Mediante:

if
elif
else

y

apply()

para clasificar usuarios en grupos de comportamiento.

⸻

🛠️ Tecnologías Utilizadas

* Python 3
* Jupyter Notebook
* Google Colab
* Pandas
* NumPy
* Matplotlib
* Seaborn

⸻

▶️ Cómo Ejecutar el Proyecto

Opción 1: Google Colab

1. Descarga los archivos:
    * telecom-analysis.ipynb
    * plans.csv
    * usage.csv
    * users_latam.csv
2. Ingresa a:
    https://colab.research.google.com
3. Selecciona:

Archivo → Subir notebook

4. Carga el archivo:

telecom-analysis.ipynb

5. Sube los datasets al entorno de Colab.
6. Ejecuta todas las celdas:

Entorno de ejecución → Ejecutar todo

⸻

Opción 2: JupyterLab o Jupyter Notebook

Instalar dependencias:

pip install pandas numpy matplotlib seaborn

Abrir Jupyter:

jupyter lab

o

jupyter notebook

Abrir:

telecom-analysis.ipynb

y ejecutar las celdas secuencialmente.

⸻

🔄 Guía de Reproducción

1. Clonar el repositorio:

git clone https://github.com//sihigzzg/telecom-analysis-sprint7-final-project.git

2. Entrar al directorio:

cd tu_repositorio

3. Instalar dependencias:

pip install pandas numpy matplotlib seaborn

4. Abrir el notebook:

jupyter lab

5. Ejecutar todas las celdas.
6. Verificar la generación de:

* Estadísticas descriptivas.
* Histogramas.
* Boxplots.
* Tablas agregadas por usuario.
* Segmentaciones finales.

⸻

📈 Resultados Principales

* Se identificaron patrones de uso diferenciados entre planes.
* Se detectaron valores faltantes estructurales asociados al tipo de servicio.
* Se construyeron métricas agregadas por usuario para facilitar el análisis.
* Se identificaron valores atípicos mediante IQR y Z-Score.
* Se generaron segmentos útiles para análisis comercial y marketing.

⸻

👨‍💻 Autor

Jorge Alberto González Guevara

Profesor de Ciencias Exactas en transición hacia Ciencia y Análisis de Datos.

Proyecto desarrollado como práctica de análisis exploratorio de datos, limpieza de información y segmentación de clientes utilizando Python.
