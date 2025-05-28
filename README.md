# Proyecto: Telecom X - Etapa 1 - Churn de Clientes

![telecom_x](https://github.com/user-attachments/assets/77e0d960-db83-4d26-abb7-3a990f2fee92)



## Índice 📋

1. Descripción del proyecto.
2. Acceso al proyecto
3. Etapas del proyecto.
4. Descripción de los datos
5. Resultados y conclusiones
6. Tecnologías utilizadas.
7. Agradecimientos.
8. Desarrollador del proyecto.

## 1. Descripción del proyecto 📚

Proyecto "Churn de Clientes" para la compañía Telecom X.

Un proveedor de servicios de telecomunicación se encuentra ante una alta tasa de evasión de clientes.

El objetivo de este proyecto fue analizar distintos factores y características que impactan en el abandono de clientes para la empresa en cuestión.
A lo largo del análisis, se desarrollaron distintas hipótesis y experimentos que permitieran evaluar las razones por las cuales los clientes deciden abandonar la compañía.

A través del análisis de datos, se encontraron relaciones entre distintas variables que permiten segmentar los grupos de clientes que cancelaron sus servicios y los que permancen en la empresa.

Finalmente, se desarrolló un reporte ejecutivo con los puntos clave del análisis, acompañado de visualizaciones e insights que justifican las conclusiones. Se incluyen también sugerencias estratégicas para aumentar la retención de clientes.<br>
Dicho reporte se encuentra en el directorio **reports**📂 del presente repositorio en formato PDF y PowerPoint.<br><br>

### *Nota: Estandarización y transformación de datos*

Inicialmente los valores Yes y No no fueron mapeados a 1 y 0, ya que es con el objetivo de realizar un resumen ejecutivo, resulta más intuitivo leer palabras como **Yes** y **No**, que identificar que 1 es positivo y 0 es negativo.

En cuanto al nombre de las columnas, opté por dejar sus nombres como están, y marcar siempre que se mencionen en negritas, traducirlas yo mismo, y dejar entre paréntesis el nombre de la columna original, es decir, por ejemplo, cuando hablo de "Churn" mantuve un formato como el siguiente: Evasión (Churn) de clientes, o Método de pago (PaymentMethod).

Si bien este es un proyecto provisto por la academia Alura en un programa de estudio, creo que la idea es abordar los proyectos como si estuviesemos en el mundo real, entonces, con el contexto que tengo, pienso lo siguiente: Si la base de datos ya está en inglés, lo más probable es que la empresa maneje clientes/directivos/mercados internacionales, por lo qué remover completamente los términos en inglés no me parece del todo adecuado.

Además debo admitir que en muchas ocasiones el inglés es más breve, evitando que los nombres de columnas se vuelvan excesivamente largos, y también evitando acentos y otros caracteres que pueden traer problemas en el entorno computacional.

Por lo que he decidido no mapear ni traducir las columnas. El mapeo de Yes/No a valores 1 y 0 se hará al final al guardar ***(load)*** los datos preprocesados.

## Acceso al proyecto 📂

Para obtener el proyecto tienes dos opciones:

1. Clonar el repositorio utilizando la línea de comandos. Solo debes dirigirte al directorio donde deseas clonar el mismo e ingresar el comando:
   `git clone https://github.com/ignaciomajo/proyecto_TelecomX`

2. O puedes descargarlo directamente desde el repositorio en GitHub en el siguiente enlace:
   <p><a href="https://github.com/ignaciomajo/proyecto_TelecomX">https://github.com/ignaciomajo/proyecto_TelecomX</p>

   Esto te llevará a la siguiente pantalla, donde deberás seguir los siguientes pasos:

![download-zip](https://github.com/user-attachments/assets/08d5b505-c404-4421-bbd5-e16c04feb58d)

   
Esto descargará un archivo comprimido `.zip`, que podras alojar en el directorio que desees.


## 3. Etapas del proyecto 📝

1. Descripción del proyecto.
2. Importación de librerías y configuraciones.
   - Importación de librerías.
   - Paths
   - Funciones
4. Extracción y Transformación de datos
   - Exploración de datos
   - Transformación de datos.
5. Análisis Exploratorio (EDA) y Visualización de Datos.
   - Antigüedad y Facturación.
   - Servicios.
   - Perfil del cliente.
6. Bulletpoints: Análisis y Visualización de Datos
7. Análisis de Correlación.
8. Carga de datos preprocesados

## 4. Descripción de los datos 📊


* El dataset original cuenta con: 7267 registros
   - En este se encontraron 224 registros con valores nulos en la variable objetivo `Churn`, los cuales fueron descartados
<br>

### Variables

| Variable           | Tipo       | Descripción breve                         | Valores originales                             | Preprocesado          |
| ------------------ | ---------- | ----------------------------------------- | ---------------------------------------------- | --------------------- |
| `customerID`       | Categórica | Identificador único del cliente           | String                                         | -                     |
| `Churn`            | Categórica | Si el cliente abandonó la empresa         | `'Yes'`, `'No'`                                | `1`, `0`              |
| `gender`           | Categórica | Género del cliente                        | `'Male'`, `'Female'`                           | One-hot               |
| `SeniorCitizen`    | Categórica | Indica si el cliente es mayor de 65 años  | `0`, `1`                                       | Igual                 |
| `Partner`          | Categórica | Si el cliente tiene pareja                | `'Yes'`, `'No'`                                | `1`, `0`              |
| `Dependents`       | Categórica | Si el cliente tiene personas a cargo      | `'Yes'`, `'No'`                                | `1`, `0`              |
| `tenure`           | Numérica   | Antigüedad en meses                       | `0` a `72`                                     | Igual                 |
| `PhoneService`     | Categórica | Si tiene servicio telefónico              | `'Yes'`, `'No'`                                | `1`, `0`              |
| `MultipleLines`    | Categórica | Si tiene múltiples líneas telefónicas     | `'Yes'`, `'No'`, `'No phone service'`          | `1`, `0`              |
| `InternetService`  | Categórica | Tipo de conexión a internet               | `'DSL'`, `'Fiber optic'`, `'No'`               | `1`, `0`              |
| `OnlineSecurity`   | Categórica | Seguridad en línea                        | `'Yes'`, `'No'`, `'No internet service'`       | `1`, `0`              |
| `OnlineBackup`     | Categórica | Respaldo en línea                         | `'Yes'`, `'No'`, `'No internet service'`       | `1`, `0`              |
| `DeviceProtection` | Categórica | Protección de dispositivo                 | `'Yes'`, `'No'`, `'No internet service'`       | `1`, `0`              |
| `TechSupport`      | Categórica | Soporte técnico                           | `'Yes'`, `'No'`, `'No internet service'`       | `1`, `0`              |
| `StreamingTV`      | Categórica | TV en streaming                           | `'Yes'`, `'No'`, `'No internet service'`       | `1`, `0`              |
| `StreamingMovies`  | Categórica | Películas en streaming                    | `'Yes'`, `'No'`, `'No internet service'`       | `1`, `0`              |
| `Contract`         | Categórica | Tipo de contrato                          | `'Month-to-month'`, `'One year'`, `'Two year'` | One-hot               |
| `PaperlessBilling` | Categórica | Si el cliente usa facturación electrónica | `'Yes'`, `'No'`                                | `1`, `0`              |
| `PaymentMethod`    | Categórica | Método de pago                            | 4 categorías                                   | One-hot               |
| `ChargesMonthly`  | Numérica   | Costo mensual del servicio                | float                                          | Igual                 |
| `ChargesTotal`    | Numérica   | Costo total acumulado del cliente         | float                                          | Limpiado y convertido |
| `ChargesDaily`    | Numérica   | Estimación diaria del costo del cliente   | float (`Charges.Monthly/30`)                   | Nueva variable        |


*Nota: Se eliminaron los valores correspondientes a `No phone service` y `No internet service`, dejando solo dos valores para los feature correspondientes.**

<br><br>
## 5. Resultados y conclusiones ✍️

* Se identificaron patrones claros de abandono relacionados con la **antigüedad del cliente *(Tenure)*** y el **gasto total acumulado *(ChargesTotal)***, siendo estos indicadores clave para predecir la evasión.

* Los clientes que abandonan en **etapas tempranas** representan la mayoría, aunque **se detectó un grupo de clientes de alto valor que también desertan**, lo cual amerita un análisis más profundo.

* El **gasto mensual elevado *(ChargesMonthly > 79 USD)*** muestra relación con un mayor Churn, indicando posible **sensibilidad al precio** en segmentos medios-altos.

* El tipo de servicio contratado influye directamente en el abandono: los clientes con **Fibra Óptica *(Fiber Optic)* presentan tasas de churn más altas**, mientras que los que tienen solo Servicio Telefónico (PhoneService) muestran mayor fidelidad.

* Los contratos de tipo **Mes a Mes *(Month-to-Month)*** y la **contratación de pocos servicios** se asocian a una **mayor probabilidad de cancelación**.

* El método de pago por **Factura Electrónica *(Electronic Check)*** muestra una **alta incidencia en el abandono**, especialmente entre clientes mayores, lo que sugiere barreras digitales o problemas de experiencia de usuario.

* El **género del cliente no es un factor relevante** en la evasión, mostrando una distribución homogénea entre hombres y mujeres.

* Los **adultos mayores *(SeniorCitizen)* tienen una tasa de abandono elevada**, particularmente cuando combinan su perfil con el uso de Electronic Check.

* Los clientes sin pareja o sin personas a cargo presentan una mayor propensión a cancelar sus servicios, lo que destaca la **necesidad de estrategias específicas para clientes individuales**.

### Los hallazgos permiten definir segmentos de riesgo y orientar acciones preventivas, como mejoras en experiencia digital, promociones por servicios combinados, y ajustes de precios personalizados.

## 6. Tecnologías utilizadas 🛠️

![Static Badge](https://img.shields.io/badge/Python-3.11.7-blue) <br>
![Static Badge](https://img.shields.io/badge/Numpy-1.26.4-green) ![Static Badge](https://img.shields.io/badge/pandas-2.2.2-green) ![Static Badge](https://img.shields.io/badge/matplotlib-3.10.0-green)
![Static Badge](https://img.shields.io/badge/seaborn-0.13.2-green)

* `Jupyter Notebook`
* `Git and GitHub`

## 7. Agradecimientos 🤝

Quiero agradecer a Oracle y Alura LATAM por proporcionar las bases y el material necesarios para la realización de este proyecto, y por su alianza que hace posible este programa de capacitación para el desarrollo del futuro en tecnología.

![Alura LATAM](https://github.com/user-attachments/assets/92a155ab-bcbb-41c6-8bbc-a0e8f552eb0f) ![Oracle](https://github.com/user-attachments/assets/f399257d-d637-44be-809e-4bac2232fe25)

![ONE](https://github.com/user-attachments/assets/368ff23a-e3f2-4f08-a987-0f736996779c)

## 8. Desarrollador del proyecto 👷

![imagen-readme](https://github.com/user-attachments/assets/133bc743-0424-4120-a7a6-7245d2f28f8c)

**| Ignacio Majo | Data Scientist Junior |**

📫 Contacto: ignacio.majoo@gmail.com | 💻[LinkedIn](https://www.linkedin.com/in/ignacio-majo/)
