# Veterinary Clinic Network Demand Forecasting

![Daily Demand](figures/00_executive_summary/network_daily_demand.png)

## Introducción

La gestión eficiente de la demanda es uno de los principales desafíos operativos en servicios de salud, incluyendo clínicas veterinarias. La variabilidad en el número de pacientes que visitan una clínica puede generar desequilibrios operativos importantes, como sobrecarga del personal en períodos de alta demanda o infrautilización de recursos en momentos de baja actividad.

En este contexto, el uso de técnicas de **ciencia de datos y modelos predictivos** permite analizar patrones históricos de demanda y anticipar el volumen futuro de visitas, proporcionando información valiosa para la planificación operativa.

Este proyecto desarrolla un análisis completo de datos operativos provenientes de una **red simulada de clínicas veterinarias**, con el objetivo de comprender los patrones de demanda y construir modelos capaces de **predecir el número diario de visitas de pacientes**.

El estudio sigue un flujo completo de trabajo de Data Science, que incluye:

- generación de datos operativos sintéticos
- análisis exploratorio de la demanda
- ingeniería de variables temporales
- segmentación de clínicas mediante aprendizaje no supervisado
- modelos de predicción de demanda
- análisis de explicabilidad del modelo

El resultado es un marco analítico que ilustra cómo las técnicas de **machine learning aplicadas a datos operativos** pueden contribuir a mejorar la planificación de recursos, la asignación de personal y la eficiencia general de una red de clínicas veterinarias.

---

## Contexto del Problema

Las clínicas veterinarias forman parte de un sistema de servicios de salud que debe gestionar recursos limitados frente a una demanda variable de pacientes. A diferencia de otros sectores, la demanda en servicios de salud suele presentar fluctuaciones significativas debido a factores como:

- comportamiento de los propietarios de mascotas
- estacionalidad en ciertos tratamientos
- aparición de emergencias veterinarias
- patrones de programación de citas

Estas fluctuaciones generan importantes desafíos operativos para las clínicas veterinarias.

Cuando la demanda supera la capacidad disponible, pueden producirse situaciones como:

- aumento en los tiempos de espera de los pacientes
- sobrecarga del personal veterinario
- deterioro en la calidad del servicio

Por otro lado, cuando la demanda es menor de lo esperado, los recursos médicos pueden quedar infrautilizados, lo que afecta la eficiencia operativa de la clínica.

En redes de clínicas veterinarias que operan en múltiples ciudades, estos desafíos se amplifican debido a la heterogeneidad entre clínicas, las diferencias en el volumen de pacientes y la variabilidad en la mezcla de servicios ofrecidos.

En este contexto, el análisis de datos históricos de visitas permite identificar patrones en la demanda y construir modelos capaces de anticipar el número de pacientes que visitarán las clínicas en el futuro.

Los modelos predictivos de demanda pueden proporcionar información valiosa para apoyar decisiones operativas como:

- planificación de turnos del personal veterinario
- gestión de agendas y citas
- asignación de recursos médicos
- preparación ante periodos de alta demanda

Este proyecto explora cómo las técnicas de **machine learning aplicadas a datos operativos** pueden utilizarse para comprender los patrones de demanda en una red de clínicas veterinarias y desarrollar modelos predictivos que apoyen la toma de decisiones operativas.

---

## Descripción del Dataset

El análisis se basa en un conjunto de datos sintético diseñado para simular la operación diaria de una red de clínicas veterinarias.

El dataset representa distintos componentes de la operación clínica, incluyendo información sobre:

- ciudades donde operan las clínicas
- características de las clínicas
- servicios veterinarios disponibles
- pacientes (mascotas)
- registros de visitas
- métricas operativas diarias

Este enfoque permite recrear un entorno realista de datos operativos similar al que podría encontrarse en sistemas de gestión clínica.

---

### Estructura del Dataset

El dataset está compuesto por varias tablas interrelacionadas que representan diferentes entidades del sistema.

Las principales tablas utilizadas en el proyecto son:

| Tabla | Descripción |
|------|-------------|
| cities | Información sobre las ciudades donde operan las clínicas |
| clinics | Características y localización de cada clínica veterinaria |
| services | Tipos de servicios veterinarios ofrecidos |
| pets | Información básica de los pacientes (mascotas) |
| visits | Registros individuales de visitas a las clínicas |
| daily_metrics | Métricas agregadas de actividad diaria |

Estas tablas permiten reconstruir el comportamiento operativo de la red de clínicas a lo largo del tiempo.

---

### Relación entre las entidades

Las entidades del dataset se relacionan de forma similar a un sistema real de gestión clínica.
Cities
   │
   └── Clinics
           │
           └── Visits
                   │
                   ├── Pets
                   └── Services

Cada registro de **visita** conecta la información del paciente, el servicio recibido y la clínica donde se realizó la atención.

Esto permite analizar patrones de demanda tanto a nivel de servicio como a nivel de clínica o red.

---

### Variables principales

Entre las variables más relevantes utilizadas en el análisis se encuentran:

**Información de visitas**

- `visit_date` – fecha de la visita
- `clinic_id` – clínica donde se realizó la visita
- `service_type` – tipo de servicio veterinario
- `pet_type` – tipo de mascota
- `visit_cost` – costo del servicio

**Información de clínicas**

- `clinic_id`
- `city`
- características operativas de la clínica

**Métricas diarias**

- número total de visitas
- ingresos diarios
- demanda agregada por clínica

Estas variables permiten analizar la demanda desde diferentes perspectivas temporales y operativas.

---

### Distribución de servicios veterinarios

El análisis de la distribución de servicios permite comprender qué tipos de atención representan la mayor parte de la actividad clínica.

![Service Distribution](figures/00_executive_summary/service_type_distribution.png)

Como puede observarse en la figura, los servicios más frecuentes corresponden a **consultas generales y servicios preventivos**, lo cual es consistente con el comportamiento esperado en sistemas veterinarios.

Los servicios especializados o procedimientos complejos presentan una frecuencia menor, pero suelen estar asociados a un mayor costo por visita.

Comprender esta distribución es importante para:

- planificación de recursos médicos
- asignación de personal especializado
- estimación de la carga de trabajo en las clínicas

---

### Distribución de ingresos por clínica

Además de analizar la demanda en términos de número de visitas, también es relevante examinar la distribución de ingresos entre clínicas.

![Revenue Distribution](figures/00_executive_summary/clinic_revenue_distribution.png)

La distribución de ingresos muestra una clara heterogeneidad entre clínicas.

Algunas clínicas concentran un volumen significativamente mayor de ingresos, lo que puede estar relacionado con:

- mayor volumen de pacientes
- oferta de servicios especializados
- ubicación en zonas con mayor demanda

Esta heterogeneidad sugiere que las clínicas operan bajo **diferentes perfiles de demanda**, lo que motiva el uso de técnicas de segmentación en etapas posteriores del análisis.

---

### Dinámica temporal de la demanda

El análisis temporal permite observar cómo evoluciona el número de visitas a lo largo del tiempo.

![Daily Demand](figures/00_executive_summary/network_daily_demand.png)

La serie temporal de visitas diarias revela una variabilidad considerable en la demanda.

Sin embargo, también pueden observarse tendencias de corto plazo que sugieren que el comportamiento reciente de la demanda contiene información relevante para predecir visitas futuras.

Este tipo de patrones justifica el uso de modelos de **forecasting basados en series temporales**, los cuales serán desarrollados en las etapas posteriores del proyecto.

---

## Análisis Exploratorio de Datos

El análisis exploratorio tiene como objetivo comprender cómo se comporta la demanda de servicios veterinarios dentro de la red de clínicas.

A través del estudio de los patrones de visitas a lo largo del tiempo, los tipos de servicios y las diferencias entre clínicas, es posible identificar dinámicas operativas que influyen en la demanda de pacientes.

Estos insights son fundamentales para diseñar modelos predictivos capaces de capturar la estructura subyacente de los datos.

---

### Distribución de los Servicios Veterinarios

![Service Distribution](figures/00_executive_summary/service_type_distribution.png)

La distribución de los servicios veterinarios permite entender la composición de la demanda dentro de la red de clínicas.

Los servicios rutinarios, como **consultas generales y vacunaciones**, representan la mayor parte de las visitas. Este patrón es consistente con lo observado en sistemas veterinarios reales, donde la atención preventiva y las consultas de control constituyen el principal motivo de visita.

En contraste, los servicios más especializados, como ciertos procedimientos médicos o quirúrgicos, aparecen con menor frecuencia pero suelen implicar una mayor complejidad operativa.

Comprender la mezcla de servicios es relevante para decisiones como:

- planificación del personal veterinario
- asignación de recursos médicos especializados
- estimación de la demanda por tipo de servicio

---

### Dinámica Temporal de la Demanda

![Daily Demand](figures/00_executive_summary/network_daily_demand.png)

La serie temporal de visitas diarias muestra una variabilidad considerable en la demanda a lo largo del tiempo.

Aunque las fluctuaciones diarias son esperables en sistemas de servicios de salud, la media móvil representada en el gráfico permite observar tendencias de corto plazo en la demanda.

A partir de este análisis se pueden destacar dos observaciones importantes:

- la demanda presenta **persistencia de corto plazo**, lo que significa que los niveles recientes de visitas tienden a influir en la demanda futura
- la variabilidad observada sugiere la presencia de patrones temporales que pueden ser aprovechados por modelos predictivos

Estas características hacen que el dataset sea particularmente adecuado para la construcción de modelos de **predicción de demanda basados en series temporales**.

---

### Distribución de Ingresos entre Clínicas

![Revenue Distribution](figures/00_executive_summary/clinic_revenue_distribution.png)

El análisis de la distribución de ingresos revela una clara heterogeneidad entre las clínicas de la red.

Algunas clínicas generan niveles de ingresos significativamente más altos que otras, lo que puede estar relacionado con factores como:

- mayor volumen de pacientes
- diferencias en la oferta de servicios
- características del entorno geográfico

Esta variabilidad sugiere que las clínicas operan bajo **perfiles operativos distintos**, lo que motiva la aplicación de técnicas de segmentación en etapas posteriores del análisis.

---

### Implicaciones del Análisis Exploratorio

El análisis exploratorio muestra que la demanda de servicios veterinarios está influenciada por múltiples factores, incluyendo la mezcla de servicios ofrecidos, las características de cada clínica y los patrones temporales de visitas.

La presencia de persistencia en la demanda sugiere que el comportamiento reciente de las visitas contiene información valiosa para anticipar la demanda futura.

Estos resultados proporcionan la base analítica para las siguientes etapas del proyecto, donde se desarrollan variables derivadas y modelos de machine learning para la predicción de la demanda diaria.

---

## Análisis Exploratorio de Datos

El análisis exploratorio tiene como objetivo comprender cómo se comporta la demanda de servicios veterinarios dentro de la red de clínicas.

A través del estudio de los patrones de visitas a lo largo del tiempo, los tipos de servicios y las diferencias entre clínicas, es posible identificar dinámicas operativas que influyen en la demanda de pacientes.

Estos insights son fundamentales para diseñar modelos predictivos capaces de capturar la estructura subyacente de los datos.

---

### Distribución de los Servicios Veterinarios

![Service Distribution](figures/00_executive_summary/service_type_distribution.png)

La distribución de los servicios veterinarios permite entender la composición de la demanda dentro de la red de clínicas.

Los servicios rutinarios, como **consultas generales y vacunaciones**, representan la mayor parte de las visitas. Este patrón es consistente con lo observado en sistemas veterinarios reales, donde la atención preventiva y las consultas de control constituyen el principal motivo de visita.

En contraste, los servicios más especializados, como ciertos procedimientos médicos o quirúrgicos, aparecen con menor frecuencia pero suelen implicar una mayor complejidad operativa.

Comprender la mezcla de servicios es relevante para decisiones como:

- planificación del personal veterinario
- asignación de recursos médicos especializados
- estimación de la demanda por tipo de servicio

---

### Dinámica Temporal de la Demanda

![Daily Demand](figures/00_executive_summary/network_daily_demand.png)

La serie temporal de visitas diarias muestra una variabilidad considerable en la demanda a lo largo del tiempo.

Aunque las fluctuaciones diarias son esperables en sistemas de servicios de salud, la media móvil representada en el gráfico permite observar tendencias de corto plazo en la demanda.

A partir de este análisis se pueden destacar dos observaciones importantes:

- la demanda presenta **persistencia de corto plazo**, lo que significa que los niveles recientes de visitas tienden a influir en la demanda futura
- la variabilidad observada sugiere la presencia de patrones temporales que pueden ser aprovechados por modelos predictivos

Estas características hacen que el dataset sea particularmente adecuado para la construcción de modelos de **predicción de demanda basados en series temporales**.

---

### Distribución de Ingresos entre Clínicas

![Revenue Distribution](figures/00_executive_summary/clinic_revenue_distribution.png)

El análisis de la distribución de ingresos revela una clara heterogeneidad entre las clínicas de la red.

Algunas clínicas generan niveles de ingresos significativamente más altos que otras, lo que puede estar relacionado con factores como:

- mayor volumen de pacientes
- diferencias en la oferta de servicios
- características del entorno geográfico

Esta variabilidad sugiere que las clínicas operan bajo **perfiles operativos distintos**, lo que motiva la aplicación de técnicas de segmentación en etapas posteriores del análisis.

---

### Implicaciones del Análisis Exploratorio

El análisis exploratorio muestra que la demanda de servicios veterinarios está influenciada por múltiples factores, incluyendo la mezcla de servicios ofrecidos, las características de cada clínica y los patrones temporales de visitas.

La presencia de persistencia en la demanda sugiere que el comportamiento reciente de las visitas contiene información valiosa para anticipar la demanda futura.

Estos resultados proporcionan la base analítica para las siguientes etapas del proyecto, donde se desarrollan variables derivadas y modelos de machine learning para la predicción de la demanda diaria.

---

## Segmentación de Clínicas

Además de analizar la demanda agregada de la red, resulta importante comprender si existen diferencias estructurales entre las clínicas que componen el sistema.

Las clínicas pueden variar significativamente en términos de:

- volumen de pacientes
- ingresos generados
- mezcla de servicios ofrecidos
- características del entorno donde operan

Identificar estas diferencias permite comprender mejor la estructura operativa de la red y detectar posibles perfiles de clínicas con comportamientos similares.

Para este propósito se aplicaron técnicas de **aprendizaje no supervisado**, específicamente reducción de dimensionalidad y clustering.

---

### Preparación de Variables

Antes de aplicar los algoritmos de clustering, las variables utilizadas para describir el comportamiento de cada clínica fueron estandarizadas.

La estandarización es necesaria porque las variables pueden tener diferentes escalas (por ejemplo, número de visitas, ingresos o proporción de servicios), lo que podría afectar el comportamiento de los algoritmos de agrupamiento.

Para este paso se utilizó **StandardScaler**, que transforma las variables para que tengan media cero y desviación estándar uno.

---

### Reducción de Dimensionalidad con PCA

Dado que el dataset incluye múltiples variables que describen el comportamiento de las clínicas, se aplicó **Principal Component Analysis (PCA)** para reducir la dimensionalidad del espacio de variables.

PCA permite transformar el conjunto original de variables en un número reducido de componentes principales que capturan la mayor parte de la variabilidad presente en los datos.

Esto facilita:

- la visualización de las clínicas en un espacio de menor dimensión
- la identificación de patrones estructurales en el comportamiento de las clínicas
- la aplicación posterior de algoritmos de clustering

---

### Clustering con K-Means

Una vez obtenidas las representaciones de las clínicas en el espacio reducido de PCA, se aplicó el algoritmo **K-Means** para identificar grupos de clínicas con características similares.

K-Means agrupa las observaciones minimizando la distancia entre cada punto y el centroide del cluster al que pertenece.

Este proceso permite detectar **segmentos operativos dentro de la red de clínicas**.

---

### Interpretación de los Clusters

El análisis de clusters revela que las clínicas pueden agruparse en diferentes perfiles operativos.

Estos perfiles pueden reflejar diferencias en:

- volumen de demanda
- generación de ingresos
- tipo de servicios predominantes

Comprender estos segmentos permite analizar la red desde una perspectiva más estratégica, identificando clínicas con patrones de operación similares.

---

### Visualización de los Clusters

La representación de las clínicas en el espacio de los primeros componentes principales permite visualizar claramente la separación entre los clusters identificados.

![Clinic Clusters](figures/04_segmentation/clinic_clusters_pca.png)

En el gráfico anterior, cada punto representa una clínica, mientras que los colores indican el cluster al que pertenece.

Esta visualización facilita la interpretación de los diferentes perfiles operativos presentes en la red.

---

### Implicaciones del Análisis de Segmentación

La segmentación de clínicas proporciona información valiosa sobre la estructura de la red.

Identificar grupos de clínicas con comportamientos similares puede ayudar a:

- diseñar estrategias operativas específicas para cada segmento
- comprender diferencias regionales en la demanda
- mejorar la asignación de recursos dentro de la red

Este análisis complementa el estudio de la demanda y proporciona un contexto adicional para interpretar los resultados de los modelos predictivos desarrollados posteriormente.

---

## Modelos de Predicción de Demanda

Una vez construidas las variables derivadas que capturan los patrones temporales de la demanda, el siguiente paso consiste en desarrollar modelos capaces de predecir el número de visitas diarias en la red de clínicas veterinarias.

La predicción de demanda se plantea como un **problema de regresión**, donde el objetivo es estimar el número de visitas futuras a partir de información histórica y variables temporales.

---

### Formulación del Problema

El objetivo del modelo es predecir la variable objetivo:

- **número de visitas diarias**

Utilizando como variables explicativas:

- variables rezagadas de demanda
- promedios móviles de visitas
- métricas de variabilidad de la demanda
- variables temporales derivadas del calendario

Este enfoque permite que los modelos aprendan patrones en el comportamiento histórico de la demanda.

---

### Modelos Evaluados

Para abordar el problema de predicción se entrenaron varios modelos de regresión con diferentes niveles de complejidad.

Los modelos evaluados incluyen:

- **Linear Regression**
- **Random Forest Regressor**
- **Gradient Boosting Regressor**

Cada modelo presenta características diferentes en términos de capacidad para capturar relaciones lineales y no lineales en los datos.

Los modelos basados en árboles, como Random Forest y Gradient Boosting, suelen ser particularmente efectivos para capturar interacciones complejas entre variables.

---

### Evaluación de los Modelos

El rendimiento de los modelos se evaluó utilizando métricas estándar de regresión.

Las principales métricas utilizadas fueron:

- **Mean Absolute Error (MAE)**  
- **Root Mean Squared Error (RMSE)**  

Estas métricas permiten cuantificar la diferencia entre las predicciones del modelo y los valores reales observados.

Un menor valor en estas métricas indica un mejor desempeño del modelo.

---

### Comparación de Modelos

La comparación entre modelos permite identificar qué enfoque proporciona mejores predicciones para la demanda de visitas.

![Model Comparison](figures/05_demand_forecasting/model_comparison.png)

El análisis comparativo muestra que los modelos basados en árboles presentan un mejor desempeño que el modelo lineal simple.

Esto sugiere que la demanda de visitas está influenciada por **relaciones no lineales entre las variables**, que pueden ser capturadas más eficazmente por modelos de mayor flexibilidad.

---

### Predicción vs Valores Reales

Una forma adicional de evaluar el desempeño del modelo es comparar directamente las predicciones con los valores observados.

![Forecast vs Actual](figures/05_demand_forecasting/forecast_vs_actual.png)

El gráfico anterior muestra que el modelo es capaz de capturar adecuadamente la tendencia general de la demanda, aunque pueden observarse desviaciones en algunos periodos específicos.

Este comportamiento es común en problemas de predicción de demanda donde pueden existir fluctuaciones inesperadas en la actividad.

---

### Interpretación del Desempeño del Modelo

En general, los resultados indican que los modelos entrenados son capaces de capturar patrones relevantes en la demanda de visitas.

La incorporación de variables temporales y de demanda rezagada resulta especialmente importante para mejorar la capacidad predictiva.

Estos resultados demuestran que los datos históricos de visitas contienen información valiosa para anticipar el comportamiento futuro de la demanda en la red de clínicas.

---

## Explicabilidad del Modelo

Además de evaluar la precisión de los modelos predictivos, también es importante comprender **qué variables influyen en las predicciones** y cómo contribuyen a estimar la demanda futura.

La interpretabilidad del modelo permite transformar los resultados de machine learning en **insights accionables**, lo cual es especialmente relevante en contextos operativos.

Para este propósito se aplicaron diferentes técnicas de explicabilidad.

---

### Importancia de las Variables

Una primera aproximación consiste en analizar la importancia relativa de las variables utilizadas por el modelo.

![Feature Importance](figures/06_model_explainability/feature_importance.png)

El análisis de importancia de variables muestra que los factores más influyentes en la predicción de la demanda están relacionados con:

- niveles recientes de visitas
- tendencias de corto plazo en la demanda
- variables temporales del calendario

Este resultado refuerza la idea observada en el análisis exploratorio de que **la demanda reciente contiene información clave para anticipar el comportamiento futuro**.

---

### Análisis SHAP

Para obtener una interpretación más detallada del comportamiento del modelo, se utilizó **SHAP (SHapley Additive Explanations)**.

SHAP es una técnica ampliamente utilizada para interpretar modelos de machine learning, ya que permite estimar la contribución de cada variable a las predicciones del modelo.

![SHAP Summary](figures/06_model_explainability/shap_summary.png)

El gráfico de resumen de SHAP muestra cómo cada variable influye en las predicciones del modelo.

En particular, se observa que:

- los niveles recientes de demanda tienen un impacto significativo en las predicciones
- ciertas variables temporales contribuyen a explicar variaciones en la demanda
- los efectos de algunas variables pueden variar dependiendo del contexto

Este análisis proporciona una comprensión más profunda de los factores que impulsan la demanda en la red de clínicas.

---

### Interpretación de los Resultados

El análisis de explicabilidad confirma que el comportamiento reciente de la demanda es uno de los factores más importantes para predecir el número de visitas futuras.

Esto es consistente con la naturaleza de muchos sistemas de servicios, donde los patrones de demanda tienden a mostrar **dependencia temporal de corto plazo**.

La capacidad de interpretar el modelo permite no solo generar predicciones precisas, sino también comprender mejor los mecanismos que influyen en la demanda de servicios veterinarios.

---

## Explicabilidad del Modelo

Además de evaluar la precisión de los modelos predictivos, también es importante comprender **qué variables influyen en las predicciones** y cómo contribuyen a estimar la demanda futura.

La interpretabilidad del modelo permite transformar los resultados de machine learning en **insights accionables**, lo cual es especialmente relevante en contextos operativos.

Para este propósito se aplicaron diferentes técnicas de explicabilidad.

---

### Importancia de las Variables

Una primera aproximación consiste en analizar la importancia relativa de las variables utilizadas por el modelo.

![Feature Importance](figures/06_model_explainability/feature_importance.png)

El análisis de importancia de variables muestra que los factores más influyentes en la predicción de la demanda están relacionados con:

- niveles recientes de visitas
- tendencias de corto plazo en la demanda
- variables temporales del calendario

Este resultado refuerza la idea observada en el análisis exploratorio de que **la demanda reciente contiene información clave para anticipar el comportamiento futuro**.

---

### Análisis SHAP

Para obtener una interpretación más detallada del comportamiento del modelo, se utilizó **SHAP (SHapley Additive Explanations)**.

SHAP es una técnica ampliamente utilizada para interpretar modelos de machine learning, ya que permite estimar la contribución de cada variable a las predicciones del modelo.

![SHAP Summary](figures/06_model_explainability/shap_summary.png)

El gráfico de resumen de SHAP muestra cómo cada variable influye en las predicciones del modelo.

En particular, se observa que:

- los niveles recientes de demanda tienen un impacto significativo en las predicciones
- ciertas variables temporales contribuyen a explicar variaciones en la demanda
- los efectos de algunas variables pueden variar dependiendo del contexto

Este análisis proporciona una comprensión más profunda de los factores que impulsan la demanda en la red de clínicas.

---

### Interpretación de los Resultados

El análisis de explicabilidad confirma que el comportamiento reciente de la demanda es uno de los factores más importantes para predecir el número de visitas futuras.

Esto es consistente con la naturaleza de muchos sistemas de servicios, donde los patrones de demanda tienden a mostrar **dependencia temporal de corto plazo**.

La capacidad de interpretar el modelo permite no solo generar predicciones precisas, sino también comprender mejor los mecanismos que influyen en la demanda de servicios veterinarios.

---

## Aplicaciones Operacionales

Los modelos de predicción de demanda desarrollados en este proyecto pueden apoyar diversas decisiones operativas dentro de una red de clínicas veterinarias.

Contar con estimaciones confiables del número esperado de visitas permite a las clínicas:

- planificar los turnos del personal veterinario
- anticipar periodos de alta demanda
- optimizar la programación de citas
- mejorar la asignación de recursos médicos

Por ejemplo, si un veterinario puede atender aproximadamente **24 consultas por día**, las predicciones de demanda pueden utilizarse para estimar el número de profesionales necesarios para cubrir la actividad diaria.

Este tipo de información permite mejorar la eficiencia operativa, reducir los tiempos de espera y ofrecer una mejor experiencia a los pacientes y sus propietarios.

---

## Estructura del Proyecto
veterinary-clinic-demand-forecasting

├── notebooks
│
├── 00_executive_summary.ipynb
├── 01_data_generate.ipynb
├── 02_exploratory_analysis.ipynb
├── 03_feature_engineering.ipynb
├── 04_clinic_segmentation.ipynb
├── 05_demand_forecasting.ipynb
└── 06_model_explainability.ipynb

├── data
│   ├── cities.csv
│   ├── clinics.csv
│   ├── services.csv
│   ├── pets.csv
│   ├── visits.csv
│   └── daily_metrics.csv

├── figures
│   └── visualizaciones generadas en los notebooks

└── README.md

---

## Tecnologías Utilizadas

El proyecto fue desarrollado utilizando las siguientes herramientas y librerías:

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- SHAP
- Jupyter Notebook

---

## Autor
Emerson Antonio da Silva