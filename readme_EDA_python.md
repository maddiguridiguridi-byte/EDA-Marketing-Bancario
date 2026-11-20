# Análisis Exploratorio de Datos (EDA) – Campañas de marketing bancario

## 1. Descripción del proyecto

Este proyecto tiene como objetivo realizar un Análisis Exploratorio de Datos (EDA) de dos conjuntos de datos relacionados con campañas de marketing telefónico de una entidad bancaria portuguesa.

Las campañas tienen como finalidad contactar con clientes para conocer su interés en contratar un depósito a plazo fijo (*term deposit*).

Para enriquecer el análisis, se integran dos fuentes de información: un conjunto de datos sobre las campañas bancarias y otro con información adicional de los clientes.

## 2. Objetivos

- Integrar los dos conjuntos de datos mediante un identificador común.
- Examinar la estructura, calidad y consistencia de los datos.
- Identificar y tratar las posibles incidencias: valores ausentes, tipos de datos incorrectos y columnas innecesarias.
- Analizar las características demográficas, económicas y de comportamiento de los clientes.
- Explorar las variables relacionadas con las campañas de marketing.
- Estudiar la distribución de la variable objetivo (`y`), que indica si el cliente ha contratado o no el depósito.
- Identificar patrones y posibles relaciones entre las variables y el resultado de la campaña.

## 3. Conjuntos de datos

Se han utilizado dos archivos originales:

| Archivo | Descripción | Dimensiones iniciales |
|---|---|---|
| `bank-additional.csv` | Información relacionada con las campañas de marketing bancario. | 43.000 filas y 24 columnas |
| `customer-details.xlsx` | Información adicional sobre los clientes. | 20.115 filas y 7 columnas |

Ambos conjuntos de datos se han integrado mediante una unión interna (`inner join`), utilizando los identificadores `id_` e `ID`, respectivamente.

El conjunto de datos resultante contiene **20.018 registros y 27 variables**.

La unión conserva únicamente los registros cuyo identificador aparece en ambos archivos.

## 4. Tecnologías y herramientas

- Python
- Pandas
- NumPy
- Jupyter Notebook
- Visual Studio Code

## 5. Metodología

El proyecto se ha desarrollado siguiendo las siguientes etapas:

### 5.1. Carga e integración de datos

- Importación de los archivos CSV y Excel.
- Inspección inicial de ambos conjuntos de datos.
- Comprobación de identificadores únicos.
- Integración mediante `merge()` utilizando una unión interna.

### 5.2. Limpieza y preparación de datos

- Comprobación de registros duplicados.
- Identificación y análisis de valores ausentes.
- Conversión de variables numéricas almacenadas inicialmente como texto.
- Conversión de variables temporales al formato `datetime`.
- Eliminación de columnas auxiliares e identificadores que no aportaban valor al análisis.

Los valores ausentes se han conservado cuando no existía una justificación suficiente para eliminarlos o imputarlos.

### 5.3. Análisis exploratorio de datos

Se ha realizado un análisis descriptivo de las principales variables, agrupándolas en diferentes bloques:

- **Variable objetivo:** distribución de las contrataciones (`y`).
- **Características demográficas:** edad, ocupación, estado civil y nivel educativo.
- **Características de la campaña:** tipo de contacto, duración de las llamadas y número de contactos.
- **Variables económicas:** indicadores económicos y de mercado.
- **Información adicional de los clientes:** ingresos, composición del hogar y visitas web.
- **Análisis temporal:** evolución de las campañas y de las contrataciones entre 2015 y 2019.

También se han estudiado las diferencias observadas entre los clientes que contrataron el depósito y aquellos que no lo hicieron.

## 6. Principales resultados

Entre los principales resultados obtenidos destacan:

- La variable objetivo presenta un desequilibrio importante: el 95,41 % de los clientes no contrató el depósito, frente al 4,59 % que sí lo hizo.
- La duración de las llamadas presenta diferencias descriptivas importantes entre ambos grupos.
- Se observan diferencias en las tasas de contratación según el tipo de contacto y determinadas categorías profesionales.
- La tasa de contratación se mantiene relativamente estable durante el periodo analizado (2015-2019).
- Algunas variables presentan valores constantes o escasa variabilidad, por lo que su capacidad para aportar información al análisis es limitada.

Estos resultados describen asociaciones observadas en los datos y no permiten establecer relaciones causales.

## 7. Limitaciones del análisis

- Existencia de valores ausentes en algunas variables.
- Desequilibrio entre las categorías de la variable objetivo.
- Pérdida de registros al integrar los archivos mediante una unión interna.
- Algunas variables presentan valores constantes o categorías con pocos registros.
- La duración de la llamada es una variable conocida una vez finalizada la interacción, por lo que no sería adecuada para un modelo predictivo que pretenda anticipar la contratación antes de realizar la llamada.

## 8. Estructura del proyecto

El proyecto incluye:

- `README.md`: documentación y descripción general del proyecto.
- `bank-additional.csv`: conjunto de datos original de campañas bancarias.
- `customer-details.xlsx`: conjunto de datos original con información de clientes.
- `EDA.ipynb`: cuaderno Jupyter con el desarrollo del análisis exploratorio.

## 9. Conclusiones

El análisis exploratorio ha permitido integrar y examinar dos fuentes de información, evaluar su calidad y estudiar las características de los clientes y de las campañas de marketing bancario.

Se han identificado patrones descriptivos relacionados con la contratación de depósitos, así como limitaciones relevantes de los datos que deberán tenerse en cuenta en posibles análisis posteriores.

Este trabajo constituye una primera fase de conocimiento y preparación de los datos, que podría servir como base para futuros proyectos de análisis predictivo y aplicación de técnicas de Machine Learning.