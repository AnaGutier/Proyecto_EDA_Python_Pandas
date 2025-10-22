# :card_index: Proyecto_EDA_Python_Pandas

**:round_pushpin:Descripción del proyecto:** Proyecto con el que desarrollo de forma autónoma un EDA en Python gracias al uso de Pandas, NumPy, Matplotlib y Seaborn. Los datos, divididos en dos archivos, corresponden a campañas de marketing de una institución bancaria portuguesa, desarrollada a base de llamadas telefónicas. 

**:round_pushpin:Objetivos:**
- **Transformación y limpieza de los datos:** Mostrar la capacidad de detectar y corregir errores, manejar datos faltantes y realizar modificaciones adecuadas a las columnas y tipos de datos.

- Demostrar un **dominio claro de estructuras de datos** como listas, diccionarios, funciones, manejo de archivos, y uso eficiente de Pandas para la manipulación de datos.

- **Análisis descriptivo de los datos:** Realizar un análisis estadístico adecuado para describir los principales atributos del conjunto de datos (medias, medianas, desviaciones estándar, correlaciones, etc.).

-  **Visualización:** Crear gráficos claros y efectivos utilizando matplotlib y seaborn, para ilustrar patrones y relaciones relevantes en los datos.

- **Uso eficiente de pandas:** Realizar operaciones como filtrado, agrupamiento, agregaciones, creación de nuevas columnas, y combinaciones de dataframes para extraer insights de los datos.

-  **Optimización del código en Python:** Aplicar buenas prácticas de programación, como evitar duplicidades, uso eficiente de bucles y comprensión de listas.

-  **Informe explicativo del análisis:** Presentar de manera clara los resultados del análisis con justificaciones basadas en datos y conclusiones bien fundamentadas.

-  **Readme del proyecto:** Incluir un README detallado que describa el propósito del proyecto, los pasos para ejecutarlo y los principales hallazgos.

## :mailbox: 1. Fuente de datos
Todos los dos archivos de datos con los que he trabajado han sido brindados por The Power Education. Se adjunta la siguiente información sobre los conjuntos de datos:

Estos conjuntos de datos están relacionados con campañas de marketing directo de una institución bancaria portuguesa. Las campañas de marketing se basaron en llamadas telefónicas. A menudo, se requería más de un contacto con el mismo cliente para determinar si el producto (depósito a plazo bancario) sería suscrito o no. Las columnas que tenemos en el primer dataset ('bank-additional.csv') son:

●  	age: La edad del cliente.

●  	job: La ocupación o profesión del cliente.

●  	marital: El estado civil del cliente.

●  	education: El nivel educativo del cliente.

●  	default: Indica si el cliente tiene algún historial de incumplimiento de pagos (1: Sí, 0: No).

●  	housing: Indica si el cliente tiene un préstamo hipotecario (1: Sí, 0: No).

●  	loan: Indica si el cliente tiene algún otro tipo de préstamo (1: Sí, 0: No).

●  	contact: El método de contacto utilizado para comunicarse con el cliente.

●  	duration: La duración en segundos de la última interacción con el cliente.

●  	campaign: El número de contactos realizados durante esta campaña para este cliente.

●  	pdays: Número de días que han pasado desde la última vez que se contactó con el cliente durante esta campaña.

●  	previous: Número de veces que se ha contactado con el cliente antes de esta campaña.

●  	poutcome: Resultado de la campaña de marketing anterior.

●  	emp.var.rate: La tasa de variación del empleo.

●  	cons.price.idx: El índice de precios al consumidor.

●  	cons.conf.idx: El índice de confianza del consumidor.

●  	euribor3m: La tasa de interés de referencia a tres meses.

●  	nr.employed: El número de empleados.

●  	y: Indica si el cliente ha suscrito un producto o servicio (Sí/No).

●  	date: La fecha en la que se realizó la interacción con el cliente.

●  	contact_month: Mes en el que se realizó la interacción con el cliente durante la campaña de marketing.

●  	contact_year: Año en el que se realizó la interacción con el cliente durante la campaña de marketing.

●  	id_: Un identificador único para cada registro en el dataset.

El segundo set de datos ('customer-details.xlsx') es un archivo Excel que nos da información sobre las características demográficas y comportamiento de compra de los clientes del banco. Este Excel consta de 3 hojas de trabajo diferentes, en cada una de ellas tenemos los clientes que entraron en el banco en diferentes años. Sus columnas son:

●  	Income: Representa el ingreso anual del cliente en términos monetarios.

●  	Kidhome: Indica el número de niños en el hogar del cliente.

●  	Teenhome: Indica el número de adolescentes en el hogar del cliente.

●  	Dt_Customer: Representa la fecha en que el cliente se convirtió en cliente de la empresa.

●  	NumWebVisitsMonth: Indica la cantidad de visitas mensuales del cliente al sitio web de la empresa.

●  	ID: Identificador único del cliente.


## 2. :open_file_folder: Estructura del repositoio
```
|--> datos_proyecto #Carpeta con datos crudos
|-------> bank-additional.csv
|-------> customer-details.xlsx
|--> EDA_proceso.ipynb #Archivo de código del EDA
|--> README.md
```

## 3. :hourglass: Fases de realización del proyecto
- **Carga y organización de los datos:** En primer lugar importo las librerías que necesito para trabajar en el EDA, cargo los archivos de datos brindados y decido unificarlos todos en un mismo dataframe para trabajar mejor con estos, comprobando la buena ejecución de estos pasos.

- **Transformación y limpieza de datos:** Reviso el tipo de datos con los que trabajo, las columnas más o menos relevantes (eliminando las que no aportan información), y generando las necesarias como pueden ser agrupaciones de datos como la edad. Al realizar las modificaciones necesarias, obtengo un conjunto de datos más limpio y listo para ser analizado.

- **Análisis y visualización de los datos:** Realiizo un estudio de cada variable, priorizando la variable 'y' que indica la suscripción o no al producto al que se enfoca la campaña. Además de esto, paso a estudiar la relación de esta variable con el resto de datos. Así logro identificar el perfil de los principales clientes que han suscrito el producto y elementos destacables en el proceso de suscripción como puede ser la duración de la llamada.

- **Informe explicativo del análisis:** Una vez realizado el análisis repaso todos los pasos realizados así como las hipótesis y conlcusiones obtenidas para generar un informe claro y eficiente de cara a planificar nuevas estrategias de marketing para la entidad.

## 4. :paperclip: Informe explicativo del análisis
-  El primer elemento destacable que revela el análsis es el bajo nivel de aceptación del producto ofertado, lo que puede señalizar un desbalace en los datos. Realizo un conteo y un gráfico de barras de la variable principal (y). Los datos confirman un fuerte desbalance, con solo un **11.1%** de éxito (yes). Esto es crucial para entender que debo analizar las proporciones de éxito en lugar de los números absolutos.

- Realizo un análisis del perfil demográfico del cliente (edad, trabajo, estado civil) para comprobar si este influye en su decisión de suscribir el producto. Creo gráficos de barras apiladas comparando la proporción de 'yes' y 'no' para cada categoría de las variables `job`, `marital`, `education` y `age_group`. Identifico patrones claros: los perfiles con una tasa de conversión significativamente más alta fueron los estudiantes y los jubilados, así como los grupos de edad más jóvenes y más mayores.

- Identifico elementos destacables como laa duración de la interacción telefónica, que es un indicador del interés del cliente y, por tanto, de la probabilidad de éxito. Uso un boxplot para comparar la distribución de la variable `duration` entre los clientes que suscribieron y los que no. La hipótesis de duración de la llamada como indicador de problale éxito en la susceipción del producto se validó de forma contundente. La duración media de una llamada exitosa es de **544 segundos**, más del doble que la de una llamada sin éxito (220 segundos).

- Continúo con otros factores como el comportamiento pasado del cliente en campañas anteriores, para comprobar si este es un buen predictor del comportamiento actual. Estudio la variable `poutcome` (resultado de la campaña anterior) en relación con la variable `y` actual, calculando la tasa de conversión para cada categoría ('success', 'failure', 'nonexistent'). Este fue el hallazgo más revelador: los clientes que tuvieron éxito en una campaña previa mostraron una espectacular tasa de conversión del **65.5%** en la actual.

## 5. :newspaper: Resultados y conclusiones

Tras el EDA realizado puedo conluir que la calve para la suscripción del producto es la calidad de la interacción con el cliente. La duración de la llamada (duration) es un fuerte indicador de éxito. Las llamadas que terminan en una suscripción duran, en promedio, más del doble que las que no (544 vs. 220 segundos). El interés del cliente y el tiempo que el agente dedica a la conversación son determinantes. A su vez, la fidelización con el banco con productos previos también resulta crucial para la nueva acptación de otro.

Teniendo en cuenta el perfil de los suscriptores, me aventuro a recomendat que las futuras campañas deberían optimizarse enfocando los recursos en los segmentos de mayor probabilidad de conversión: clientes leales, estudiantes y jubilados. Para estos grupos, se debería potenciar una interacción de mayor calidad y duración.

En el ámbito personal, este proyecto me ha permitido aplicar mis conocimientos e las librerías de Pyhton mencionadas, mediante buenas prácticas y un proceso estructurado, completando satisfactoriamente los objetivos planteados en un inicio.

## 6. :black_nib:Próximos pasos
Personalmente, creo que los próximos pasos a realizar con los datos presentes, pasan por la realización de un **dashboard interactivo** que pueda proporcionar a la entidad un entendimiento claro y conciso del perfil del cliente más propenso a comprar el producto (para ello puede resultar últi el último dataframe generado con únicamente aquellos clientes que aceptaron el producto). A su vez, este debería mostrar elementos clave en el proceso de suscripción como puede ser la duración de la llamada, para configurar nuevas estrategias más efectivas que las presentes.

## 7. :closed_book: Autores

Proyecto realizado por **Ana Gutiérrez Hernández**

Datos proporcionados por **The Power: formación en Data & Analytics**