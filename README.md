# Modelo para Datos Hospitalarios

Objetivo.- En este proyecto se realiza el análisis de datos exploratorio, limpieza de datos, modelo de machine learning de regresión logistica y evaluación del modelo.

Se comparte el archivo de extensión ipynb donde se tiene la referencia del código utilizado, de manera general muestro algunas partes interesantes del proyecto.
Los datos usados estan en el archivo de excel Hospitalizacion.xlsx
El análisis exploratorio se hará sobre un set de datos de pacientes de un Hospital que han sido hospitalizados y no hospitalizados.

### Requerimiento
Nuestro cliente desea saber las características más importantes que tienen los pacientes de cierto tipo de enfermedad que terminan en hospitalización.

##  Análisis exploratorio de datos(EDA)
Responderemos algunas preguntas que nos hacemos al iniciar todo proyecto como:¿De qué tamaño es el set de datos? , ¿Hay registros duplicados?, ¿Hay valores nulos?,¿Cuáles son las variables o columnas?, para responder estas preguntas ejecutaremos algunas lineas de código y observamos que tenemos.

![image](https://github.com/OscarMoralesMejia/Modelo_DatosHospitalarios/assets/159685580/90635a4c-b6fe-4835-8600-c2efa2dde32e)

#### Outlayers en variables numericas
![image](https://github.com/OscarMoralesMejia/Modelo_DatosHospitalarios/assets/159685580/c27e46cd-e2c4-45a6-aa3a-260c52bdf255)

#### Análisis de variables categóricas
![image](https://github.com/OscarMoralesMejia/Modelo_DatosHospitalarios/assets/159685580/b9870b9d-aaae-40fd-8c27-f9f4eca41fda)
![image](https://github.com/OscarMoralesMejia/Modelo_DatosHospitalarios/assets/159685580/ca8c96fd-de3f-4e4f-9986-4d558da2e633)

#### Limpieza de datos
Quitamos valores nulos, limpiando los outlayers de la variable edad

#### Selección de variables
Para esto tuve que leer un poco sobre el tema de PSA y adentrarme en el tema de antígeno prostático específico.
Cómo primer acercamiento selecciones 3 variables y la etiqueta objetivo
En este punto ya habia analizado que se trata de un problema de  Clasificación de acuerdo al requerimiento del cliente

![image](https://github.com/OscarMoralesMejia/Modelo_DatosHospitalarios/assets/159685580/9a2b19be-8e43-45c8-90c7-760ffb3b4b0a)


#### Modelo
De acuerdo al requerimiento se trata de un problema de clasificación, en este caso comenzaremos por aplicar regresión logistica, iniciando con un set de datos de 3 variables independientes y una variable dependiente.

En la siguiente grafica podemos ver que el set de datos esta desbalanceado asi que aplicaremos oversampling
![image](https://github.com/OscarMoralesMejia/Modelo_DatosHospitalarios/assets/159685580/77eafa79-85da-4f48-883c-ed3cd8a7d30c)

Generamos el modelo y obtenemos la siguiente matriz de confusión

![image](https://github.com/OscarMoralesMejia/Modelo_DatosHospitalarios/assets/159685580/df82005c-cb22-4841-80a4-9a0691b2e861)



#### Evaluación del modelo

![image](https://github.com/OscarMoralesMejia/Modelo_DatosHospitalarios/assets/159685580/e08a6079-6770-4974-bc5a-7b36a4567632)

Aplicamos accuracy score y obtenemos inicial que predice que 6 de cada 10 pacientes seran hospitalizados.Para ser un primer acercamiento no esta nada mal, asi que incluiremos mas variables y veremos los resultados.
El código está en el archivo modelo_v1.ipynb
#### Conclusiones
Se desarrollaron más versiones del mismo modelo de regresión logistica incrementando el número de variables llegando a un total de 9 variables las cuales son:
'EDAD','BIOPSIAS PREVIAS','PSA','VOLUMEN PROSTATICO','ANTIBIOTICO UTILIAZADO EN LA PROFILAXIS','NUMERO DE MUESTRAS TOMADAS','CUP','BIOPSIA','NUMERO DE DIAS POST BIOPSIA EN QUE SE PRESENTA LA COMPLICACIÓN INFECCIOSA','HOSPITALIZACION' 
y con las cuales llegamos a un buen modelo para generalizar cuando un paciente será hospitalizado.
Por lo que las variables usadas son las de mayor peso, para cuando un paciente es hospitalizado.
Esto lo podemos ver en el archivo modelo_v2.ipynb



