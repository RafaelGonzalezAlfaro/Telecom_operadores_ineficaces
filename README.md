# Telecom_operadores_ineficaces
Proyecto 14

# Introducción
CallMeMaybe está desarrollando una función para identificar operadores ineficaces.
Esta función analizará métricas como llamadas perdidas (internas y externas), tiempo de espera
prolongado y, para los roles que requieren llamadas salientes, un bajo volumen de las mismas.
Esto permitirá a los supervisores identificar áreas de mejora en el rendimiento de su equipo.

# Metodología
**Preprocesamiento de datos:** Se limpiaron y estandarizaron los datos, eliminando inconsistencias y verificando la ausencia de duplicados y valores faltantes.
**Exploratory Data Analysis (EDA):** Se analizaron distintos datos, se crearon histogramas y graficas para visualizacion de datos mas claramente
**Pruebas de Hipotesis:** Se realizaron pruebas de hipotesis para observar si la tasa de llamadas perdidas no está correlacionada con el tiempo de espera y si hay alguna diferencia en el tiempo de espera entre operadores eficientes e ineficientes.

Herramientas utilizadas en este proyecto:

![Python](https://img.shields.io/badge/python-357ebd?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23357ebd.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-357ebd?style=for-the-badge)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23357ebd.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Limpieza de datos](https://img.shields.io/badge/Limpieza_de_datos-295F98?style=for-the-badge)
![Transformación de datos](https://img.shields.io/badge/Transformación_de_datos-295F98?style=for-the-badge)
![Análisis de datos](https://img.shields.io/badge/Análisis_de_datos-295F98?style=for-the-badge)
![Modelos de predicción](https://img.shields.io/badge/Modelos_de_predicción-295F98?style=for-the-badge)

# Objetivos:
### - ¿Qué queremos conseguir con esta información?
El objetivo de nuestro análisis es desarrollar un sistema para identificar operadores ineficaces con el cual,
se busca **mejorar** la calidad del servicio, **reducir** la pérdida de clientes y **optimizar** la asignación de
recursos.
### - ¿A quién va dirigido?
Este enfoque va dirigido a supervisores y gerencia, los cuales utilizarán esta información para la
gestión del rendimiento, la formación de operadores y la planificación de la capacidad.
Los cuales se beneficiarán de una **mayor eficiencia** operativa y satisfacción del cliente.

### - ¿Qué decisiones se tomarán?
Se tomarán decisiones sobre la capacitación adicional de los operadores, la reasignación de tareas, la
optimización de los flujos de trabajo e incluso posibles medidas disciplinarias o de incentivos.
El análisis también puede ayudar a identificar problemas sistémicos que contribuyen a la ineficiencia.

# Conclusiones generales y recomendaciones:
## En base al análisis:
de acuerdo al tiempo de espera en las llamadas, tasa de llamadas perdidas y la eficiencia de los operadores
eficientes e ineficientes en base al tiempo de espera de las llamadas, podemos concluir que:

● No hay una gran diferencia en la tendencia central de la tasa de llamadas perdidas entre los diferentes
cuartiles de tiempo de espera.
● Existe una correlación negativamente significativa entre el tiempo de espera y la tasa de llamadas perdidas.
A medida que aumenta el tiempo de espera, la tasa de llamadas perdidas disminuye.
● Existe una diferencia estadísticamente significativa entre los operadores eficientes e ineficientes, es decir,
los operadores clasificados como "ineficientes" tienden a tener tiempos de espera considerablemente más
largos que los operadores "eficientes".
● Las llamadas sin identificación (desconocidas) representan una gran parte de los datos, creando
posibles sesgos en los datos.

# Acciones recomendadas:
❖ Optimizar procesos:
➢ Analizar los flujos de trabajo y sistemas actuales para identificar posibles cuellos de botella.
➢ Implementar mejoras en los procesos para agilizar el manejo de llamadas y reducir el tiempo que los
clientes pasan esperando.

❖ Mejorar la capacitación:
➢ Proporcionar a los operadores capacitación adicional sobre el manejo eficiente de llamadas, incluyendo
técnicas de comunicación, manejo de objeciones y resolución de problemas.

❖ Ajustar la asignación de personal:
➢ Analizar la demanda de llamadas en diferentes horarios y días de la semana para optimizar la programación
del personal y asegurar una cobertura adecuada en los momentos de mayor demanda.

❖ Implementar sistemas de enrutamiento inteligente:
➢ Utilizar sistemas que distribuyan las llamadas de manera más eficiente entre los operadores disponibles,
teniendo en cuenta la experiencia y habilidades de cada uno, con una mejor clasificación del cliente que llama.

# Diccionario de datos:

Los datasets contienen información sobre el uso del servicio de telefonía virtual CallMeMaybe. Sus clientes son organizaciones que necesitan distribuir gran cantidad de llamadas entrantes entre varios operadores, o realizar llamadas salientes a través de sus operadores. Los operadores también pueden realizar llamadas internas para comunicarse entre ellos. Estas llamadas se realizan a través de la red de CallMeMaybe.

El dataset comprimido `telecom_dataset_us.csv` contiene las siguientes columnas:

- `user_id`: ID de la cuenta de cliente
- `date`: fecha en la que se recuperaron las estadísticas
- `direction`: "dirección" de llamada (`out` para saliente, `in` para entrante)
- `internal`: si la llamada fue interna (entre los operadores de un cliente o clienta)
- `operator_id`: identificador del operador
- `is_missed_call`: si fue una llamada perdida
- `calls_count`: número de llamadas
- `call_duration`: duración de la llamada (sin incluir el tiempo de espera)
- `total_call_duration`: duración de la llamada (incluido el tiempo de espera)

El conjunto de datos `telecom_clients_us.csv` tiene las siguientes columnas:

- `user_id`: ID de usuario/a
- `tariff_plan`: tarifa actual de la clientela
- `date_start`: fecha de registro de la clientela
