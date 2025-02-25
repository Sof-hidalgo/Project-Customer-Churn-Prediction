# Project-Customer-Churn-Prediction

# 📌 Predicción de Cancelación de Clientes - Interconnect

## 📖 Descripción del Proyecto:
Interconnect, un operador de telecomunicaciones, busca reducir la tasa de cancelación de clientes ofreciendo incentivos a aquellos que tienen mayor probabilidad de abandonar el servicio. Para ello, se desarrolló un modelo de machine learning capaz de predecir la cancelación de clientes a partir de sus datos personales, información contractual y uso del servicio.

## 🎯 Objetivo del Proyecto:
Desarrollar un modelo predictivo que identifique clientes con alta probabilidad de cancelación para que la empresa pueda implementar estrategias de retención, optimizando sus esfuerzos y recursos.

### Servicios de Interconnect

Interconnect proporciona principalmente dos tipos de servicios:

1. Comunicación por teléfono fijo. El teléfono se puede conectar a varias líneas de manera simultánea.
2. Internet. La red se puede configurar a través de una línea telefónica (DSL, *línea de abonado digital*) o a través de un cable de fibra óptica.

Algunos otros servicios que ofrece la empresa incluyen:

- Seguridad en Internet: software antivirus (*ProtecciónDeDispositivo*) y un bloqueador de sitios web maliciosos (*SeguridadEnLínea*).
- Una línea de soporte técnico (*SoporteTécnico*).
- Almacenamiento de archivos en la nube y backup de datos (*BackupOnline*).
- Streaming de TV (*StreamingTV*) y directorio de películas (*StreamingPelículas*)

La clientela puede elegir entre un pago mensual o firmar un contrato de 1 o 2 años. Puede utilizar varios métodos de pago y recibir una factura electrónica después de una transacción.

### Descripción de los datos

Encuentra los datos en: `*final.provider.zip*`

Los datos consisten en archivos obtenidos de diferentes fuentes:

- `contract.csv` — información del contrato;
- `personal.csv` — datos personales del cliente;
- `internet.csv` — información sobre los servicios de Internet;
- `phone.csv` — información sobre los servicios telefónicos.

En cada archivo, la columna `customerID` (ID de cliente) contiene un código único asignado a cada cliente. La información del contrato es válida a partir del 1 de febrero de 2020.

- Característica objetivo: la columna `'EndDate'` es igual a `'No'`.
- Métrica principal: AUC-ROC.
- Métrica adicional: exactitud

## Etapas del proyecto:

Se dividió el proyecto en tres diferentes Jupyter Notebook para mayor organización:

1. Plan de trabajo - análisis exploratorio en donde se concluirán los pasos a seguir en todo el proyecto
2. Código de Solución - donde se construye el modelo
3. Informe de solución - donde se responderán estas preguntas:
    - ¿Qué pasos del plan se realizaron y qué pasos se omitieron (explica por qué)?
    - ¿Qué dificultades se encontraron y cómo se lograron resolverlas?
    - ¿Cuáles fueron algunos de los pasos clave para resolver la tarea?
    - ¿Cuál es el modelo final y qué nivel de calidad tiene?
  
------

## 📊 Conclusiones Finales:
- 1️⃣ Modelo Predictivo: Se probaron varios algoritmos de machine learning, incluyendo Regresión Logística, Árboles de Decisión, Random Forest y LightGBM.
  El modelo seleccionado fue Regresión Logística, ya que alcanzó un F1-score de 0.8292 y un AUC-ROC de 0.9505, lo que indica una excelente capacidad de clasificación.
- 2️⃣ Factores Claves en la Cancelación:
  - Se encontró que el tipo de contrato y los cargos mensuales tienen una alta correlación con la cancelación de clientes.
  - Los clientes con contratos mensuales tienen una mayor tasa de cancelación en comparación con aquellos con contratos a largo plazo.
- 3️⃣ Manejo del Desequilibrio de Clases:
  - Se aplicó SMOTE (Synthetic Minority Over-sampling Technique) para balancear las clases y mejorar la predicción de los clientes que cancelan el servicio.
- 4️⃣ Optimización y Generalización:
  - Se ajustaron hiperparámetros para mejorar la precisión sin sobreajustar el modelo, logrando una buena generalización en datos no vistos.

✅ Impacto del Modelo:
  - El modelo puede ser utilizado para detectar clientes en riesgo y tomar acciones preventivas, como ofrecer promociones o beneficios personalizados para aumentar la retención y reducir pérdidas.
