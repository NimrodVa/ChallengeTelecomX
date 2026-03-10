El objetivo de este proyecto es analizar los factores que influyen en la cancelación de servicios (churn) de los clientes de Telecom X. A través de un proceso de limpieza, transformación y análisis exploratorio de datos (EDA), se busca:

Identificar patrones y características comunes entre los clientes que abandonan la compañía.

Proveer un conjunto de datos limpio y listo para modelamiento predictivo.

Generar insights que permitan diseñar estrategias de retención efectivas.

Este análisis constituye la primera fase de un proyecto más amplio de ciencia de datos, cuyo fin último es reducir la tasa de evasión y mejorar la satisfacción del cliente.

📁 Estructura del proyecto
La organización de archivos y carpetas es la siguiente:

text
📁 TelecomX_Churn_Analysis/
│
├── 📄 README.md                # Este archivo
├── 📓 TelecomX_Churn_Analysis.ipynb   # Notebook principal en Google Colab
│
├── 📁 data/
│   ├── telecom_churn_clean.csv        # Dataset limpio (generado al ejecutar)
│   └── (otros archivos si se requieren)
│
├── 📁 images/                         # Gráficos generados durante el análisis
│   ├── churn_global.png
│   ├── boxplots_churn.png
│   ├── churn_contract.png
│   ├── correlation_matrix.png
│   └── ...
│
└── 📁 informe/
    └── informe_final.md               # Informe detallado con conclusiones y recomendaciones
Nota: Las carpetas data/, images/ e informe/ se crean automáticamente al ejecutar el notebook o pueden ser creadas manualmente.

📊 Ejemplos de gráficos e insights obtenidos
A continuación se muestran algunos de los gráficos más representativos del análisis y los hallazgos clave derivados de ellos.

1. Distribución global de Churn
Insight: La tasa de cancelación general es del 26.5%, lo que indica un problema significativo que requiere atención prioritaria.

2. Comparación de antigüedad y cargo mensual según Churn


Insight: Los clientes que cancelan tienen una menor antigüedad promedio (18 meses vs. 38 meses de los que permanecen) y pagan cargos mensuales ligeramente superiores (74$ vs. 61$). Esto sugiere que los clientes nuevos y aquellos con planes más costosos son más propensos a irse.

3. Tasa de churn por tipo de contrato


Insight: El contrato mes a mes presenta una tasa de churn del 43%, mientras que los contratos de uno y dos años tienen tasas del 11% y 3% respectivamente. Fomentar contratos de largo plazo podría ser una estrategia efectiva de retención.

4. Matriz de correlación


Insight: Las variables más correlacionadas con el churn son el tipo de contrato (negativa) y la antigüedad (negativa). Los cargos mensuales tienen una correlación positiva débil.

🚀 Instrucciones para ejecutar el notebook en Google Colab
Sigue estos pasos para reproducir el análisis en tu entorno de Google Colab:

1. Abrir Google Colab
Ve a colab.research.google.com e inicia sesión con tu cuenta de Google.

2. Subir el notebook
Haz clic en Archivo > Subir notebook.

Selecciona el archivo TelecomX_Churn_Analysis.ipynb desde tu computadora o súbelo desde Google Drive.

3. Ejecutar las celdas
El notebook está dividido en secciones que deben ejecutarse en orden:

Configuración inicial: Instalación de librerías (si es necesario) y montaje de Google Drive (opcional).

Carga de datos: Los datos se obtienen directamente desde una URL pública usando pandas.read_json().

Limpieza y transformación: Se desanidan las columnas, se convierten tipos de datos y se manejan valores nulos.

Análisis exploratorio: Se generan estadísticas descriptivas y visualizaciones.

Exportación de resultados: El dataset limpio se guarda en un archivo CSV y las imágenes se almacenan en la carpeta images/.

Recomendación: Para evitar la descarga de archivos grandes, puedes ejecutar todo el notebook en una sola sesión. Si deseas guardar las imágenes localmente, habilita la opción de descarga automática o móntalo en Google Drive.

4. Acceso a los datos
La URL de los datos raw es:

text
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Cargar datos
url = "https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/refs/heads/main/TelecomX_Data.json"
df = pd.read_json(url)

# Ver primeras filas
df.head()El notebook ya incluye esta dirección, por lo que no necesitas descargar nada manualmente.

5. Personalización
Si tu DataFrame final tiene nombres de columna diferentes (por ejemplo, en minúsculas), ajusta las referencias en las celdas de visualización según la salida de df_clean.columns.
