# Proyecto: Telecom X - Etapa 1 - Churn de Clientes



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

El objetivo de este proyecto será analizar, a partir de los datos provistos por la empresa, cuales son los factores que más influyen en la cancelación de los servicios, como así también entender las características de aquellos clientes que permanecen en la empresa, justificando los hallazgos a través del storytelling detrás de los datos.

A lo largo del análisis, se desarrollarán distintas hipótesis y se realizarán los experimentos necesarios para que estas sean aprobadas o refutadas, permitiendo así desarrollar estrategias orientadas a mejorar la experiencia del usuario y de esta manera disminuir la tasa de evasión por parte de los clientes.

Finalmente se desarrollará un reporte ejecutivo con los puntos claves descubiertos a lo largo del presente análisis.

## Acceso al proyecto 📂

Para obtener el proyecto tienes dos opciones:

1. Clonar el repositorio utilizando la línea de comandos. Solo debes dirigirte al directorio donde deseas clonar el mismo e ingresar el comando:
   `git clone https://github.com/ignaciomajo/proyecto_TelecomX`

2. O puedes descargarlo directamente desde el repositorio en GitHub en el siguiente enlace:
   <p><a href="(https://github.com/ignaciomajo/proyecto_TelecomX)">https://github.com/ignaciomajo/proyecto_TelecomX</p>

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

### Variables

`CustomerID:` Código identificador único de cliente

`Gender:` Género biológico del cliente.
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`SeniorCitizen:` Condición de adulto mayor (65 años o más)
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`Partner:` Condición de pareja estable
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`Dependents:` Condición de personas a cargo
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`Tenure:` Antigüedad del cliente en meses
   Variable Numérica: 
   Tipo: int
   
`PhoneService:` Condición de servicio de servicio de teléfono
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`MultipleLines:` Condición de servicio de múltiples lineas de teléfono
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`InternetService:` Condición de servicio de servicio de internet
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`OnlineSecurity:` Condición de servicio de seguridad online
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1

`OnlineBackup:` Condición de servicio de copias de seguridad online
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`DeviceProtection:` Condición de servicio de seguro de dispositivos
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`TechSupport:` Condición de servicio de soporte técnico
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`StreamingTV:` Condición de servicio de transmisión cable (televisión)
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`StreamingMovies:` Condición de servicio de transmisión de películas
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`Contract:` Tipo de contrato adquirido por el cliente
   Variable Categórica:
   Etiquetas: Two Year (dos años), One year (un año), Month-To-Month (Mes a Mes)
   
`PaperlessBilling:` Condición de factura digital
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1
   
`PaymentMethod:` Metodo de pago utilizado para pagar por los servicios contratados
   Variable Categórica
   Etiquetas: Mailed check (Factura por correo), Electronic check (factura electrónica), Credit card (automatic) (Tarjeta de Crédito (automático), 
              Bank transfer (automatic) (Transferencia Bancaria (automático)

`ChargesDaily:` Gasto diario del cliente
   Variable Numérica
   Tipo: float
   
`ChargesMonthly:` Gasto mensual del cliente
   Variable Numérica
   Tipo: float
   
`ChargesTotal:` Gasto total acumulado en el ciclo de vida del cliente
   Variable Numérica
   Tipo: float
   
`Churn:` Condición de abandono del cliente
   Variable Categórica 
   Binaria: Sí, No
   Preprocesados: 0, 1

   
## 5. Resultados y conclusiones ✍️

* Se identificaron patrones claros de abandono relacionados con la antigüedad del cliente (Tenure) y el gasto total acumulado (ChargesTotal), siendo estos indicadores clave para predecir la evasión.

* Los clientes que abandonan en etapas tempranas representan la mayoría, aunque se detectó un grupo de clientes de alto valor que también desertan, lo cual amerita un análisis más profundo.

* El gasto mensual elevado (ChargesMonthly > 79 USD) muestra relación con un mayor churn, indicando posible sensibilidad al precio en segmentos medios-altos.

* El tipo de servicio contratado influye directamente en el abandono: los clientes con Fibra Óptica (Fiber Optic) presentan tasas de churn más altas, mientras que los que tienen solo Servicio Telefónico (PhoneService) muestran mayor fidelidad.

* Los contratos de tipo Mes a Mes (Month-to-Month) y la contratación de pocos servicios se asocian a una mayor probabilidad de cancelación.

* El método de pago por Factura Electrónica (Electronic Check) muestra una alta incidencia en el abandono, especialmente entre clientes mayores, lo que sugiere barreras digitales o problemas de experiencia de usuario.

* El género del cliente no es un factor relevante en la evasión, mostrando una distribución homogénea entre hombres y mujeres.

* Los adultos mayores (SeniorCitizen) tienen una tasa de abandono elevada, particularmente cuando combinan su perfil con el uso de Electronic Check.

* Los clientes sin pareja o sin personas a cargo presentan una mayor propensión a cancelar sus servicios, lo que destaca la necesidad de estrategias específicas para clientes individuales.

### Los hallazgos permiten definir segmentos de riesgo y orientar acciones preventivas, como mejoras en experiencia digital, promociones por servicios combinados, y ajustes de precios personalizados.

## 6. Tecnologías utilizadas 🛠️

![Static Badge](https://img.shields.io/badge/Python-3.11.7-blue) <br>
![Static Badge](https://img.shields.io/badge/Numpy-1.26.4-green) ![Static Badge](https://img.shields.io/badge/pandas-2.2.2-green) ![Static Badge](https://img.shields.io/badge/matplotlib-3.10.0-green)
![Static Badge](https://img.shields.io/badge/seaborn-0.13.2-green) ![Static Badge](https://img.shields.io/badge/folium-0.19.5-green) ![Static Badge](https://img.shields.io/badge/scikit_learn-1.5.2-green)

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
