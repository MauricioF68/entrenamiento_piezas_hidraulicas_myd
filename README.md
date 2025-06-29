# Proyecto de Entrenamiento de Piezas Hidráulicas (DD MYD)

Este repositorio contiene el código y los modelos para el entrenamiento y diagnóstico de piezas hidráulicas, desarrollado como parte del proyecto de Visión Computacional.

## Estructura del Proyecto

A continuación, se describe la función y el contenido de cada directorio y archivo principal:

* **`.ipynb_checkpoints/`**: Este directorio es generado automáticamente por Jupyter Notebook para guardar puntos de control de las sesiones. No es necesario subirlo al repositorio, por lo que está incluido en el `.gitignore`.

* **`Dataset/`**: Esta carpeta contiene los datos brutos utilizados para el entrenamiento y la validación de los modelos. Debido a su tamaño considerable, esta carpeta ha sido excluida del control de versiones de Git mediante el archivo `.gitignore`. Si deseas replicar el entorno o el entrenamiento, deberás obtener el conjunto de datos por separado y colocarlo en esta ubicación.
    * **Formato del Contenido:** Los archivos dentro de esta carpeta son los datos de entrenamiento (por ejemplo, archivos CSV, imágenes, u otros formatos de datos).

* **`env/`**: Este directorio alberga el entorno virtual de Python del proyecto. Contiene todas las librerías y dependencias específicas necesarias para ejecutar el código de forma aislada. También está incluido en el `.gitignore` para evitar conflictos de dependencias entre diferentes sistemas.

* **`entrenar_y_guardar.ipynb`**: Este es un cuaderno de Jupyter Notebook que contiene el código fuente para el proceso de entrenamiento del modelo de diagnóstico. Incluye la carga de datos, preprocesamiento, definición del modelo, entrenamiento y el guardado de los artefactos generados (modelos y encoders).
    * **Formato:** Cuaderno de Jupyter (`.ipynb`).

* **`estado_encoder.joblib`**: Este archivo es un codificador (encoder) serializado, guardado en formato `joblib`. Se utiliza para transformar la característica 'estado' (categórica) en un formato numérico que el modelo pueda procesar.
    * **Formato:** Archivo `joblib`.

* **`modelo_diagnostico_v1.keras`**: Este es el archivo del modelo de red neuronal entrenado, guardado en formato Keras (`.keras`). Representa la versión 1 del modelo capaz de realizar diagnósticos sobre las piezas hidráulicas.
    * **Formato:** Archivo de modelo Keras (`.keras`).

* **`pieza_encoder.joblib`**: Similar a `estado_encoder.joblib`, este archivo es un codificador serializado para la característica 'pieza', también en formato `joblib`.
    * **Formato:** Archivo `joblib`.

* **`verificar_modelo.ipynb`**: Este cuaderno de Jupyter Notebook está diseñado para la verificación y evaluación del modelo entrenado. Permite cargar el modelo guardado y los encoders para probar su rendimiento con nuevos datos o datos de prueba.
    * **Formato:** Cuaderno de Jupyter (`.ipynb`).

## Pasos para Desplegar y Ejecutar el Proyecto

Para poner en marcha este proyecto en tu entorno local, sigue las siguientes instrucciones:

1.  **Clonar el Repositorio:**
    Abre tu terminal (o la terminal integrada de VS Code) y clona el repositorio:
    ```bash
    git clone [https://github.com/MauricioF68/entrenamiento_piezas_hidraulicas_myd.git](https://github.com/MauricioF68/entrenamiento_piezas_hidraulicas_myd.git)
    cd entrenamiento_piezas_hidraulicas_myd
    ```

2.  **Crear y Activar el Entorno Virtual:**
    Es altamente recomendable usar un entorno virtual para gestionar las dependencias.
    ```bash
    python -m venv env
    # Para Windows:
    .\env\Scripts\activate
    # Para macOS/Linux:
    # source env/bin/activate
    ```

3.  **Instalar Dependencias:**
    Asegúrate de tener un archivo `requirements.txt` con todas las librerías necesarias (por ejemplo, `tensorflow`, `scikit-learn`, `pandas`, `numpy`, `joblib`, `jupyter`). Si no lo tienes, puedes crearlo con `pip freeze > requirements.txt` después de instalar las librerías manualmente, o instalar las librerías directamente.
    ```bash
    pip install -r requirements.txt
    ```
    (Si no tienes `requirements.txt`, instala las librerías principales: `pip install tensorflow scikit-learn pandas numpy jupyter joblib`)

4.  **Obtener el Conjunto de Datos:**
    Dado que la carpeta `Dataset/` no está en el repositorio, deberás obtenerla por separado y colocarla en la raíz del proyecto (dentro de la carpeta `entrenamiento_piezas_hidraulicas_myd`).

5.  **Ejecutar los Cuadernos de Jupyter:**
    Una vez que las dependencias estén instaladas y el dataset en su lugar, puedes iniciar Jupyter Notebook:
    ```bash
    jupyter notebook
    ```
    Esto abrirá una interfaz en tu navegador. Desde allí, podrás navegar y ejecutar los cuadernos `entrenar_y_guardar.ipynb` y `verificar_modelo.ipynb` para entender y replicar el proceso de entrenamiento y verificación del modelo.

Esperamos que esta guía te sea de gran utilidad para explorar y utilizar este proyecto. ¡Adelante con el estudio de las piezas hidráulicas!
