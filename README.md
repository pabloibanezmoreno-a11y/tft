# TFT Stallion Forecasting Boilerplate

Este es un proyecto base altamente documentado para el desarrollo y entrenamiento del modelo **Temporal Fusion Transformer (TFT)** utilizando la librería `pytorch-forecasting` y el dataset integrado `Stallion`.

La arquitectura TFT es idónea para el pronóstico de múltiples series temporales continuas y categóricas cruzadas, proporcionando predicciones probabilísticas en base a intervalos (cuantiles).

---

## 🛠️ Requisitos e Instalación

Sigue estos pasos en tu terminal (PowerShell o Símbolo del Sistema en Windows) para crear tu entorno virtual de Python, activar el entorno e instalar las dependencias necesarias.

### 1. Crear el Entorno Virtual
En la raíz de este proyecto, ejecuta el siguiente comando para crear un entorno virtual limpio llamado `.venv`:

```bash
python -m venv .venv
```

### 2. Activar el Entorno Virtual (en Windows)

* **Si usas PowerShell:**
  ```powershell
  .venv\Scripts\Activate.ps1
  ```
  *(Nota: Si te aparece un error de políticas de ejecución, puedes usar temporalmente `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process` en tu sesión).*

* **Si usas Símbolo del Sistema (CMD):**
  ```cmd
  .venv\Scripts\activate.bat
  ```

Una vez activado, verás que el prefijo `(.venv)` aparece al inicio de tu línea de comandos.

### 3. Instalar las Dependencias
Con el entorno activo, instala todas las librerías necesarias con:

```bash
pip install -r requirements.txt
```

---

## 🚀 Cómo Ejecutar el Proyecto

Para entrenar el modelo (por defecto configurado a 3 épocas rápidas para validación técnica) y generar el gráfico de predicción probabilístico, ejecuta el siguiente comando:

```bash
python tft_stallion_boilerplate.py
```

Al finalizar el script, se generará una imagen llamada **`tft_prediction_plot.png`** en la carpeta raíz que muestra el valor real frente a la predicción mediana ($p50$) y los intervalos de incertidumbre de la demanda ($p10$ - $p90$).

---

## 🐙 Configuración del Repositorio de GitHub

He creado un script automatizado llamado **`push_to_github.bat`** en la carpeta raíz del proyecto, preconfigurado específicamente con tu dirección de repositorio: `https://github.com/pabloibanezmoreno-a11y/tft.git`.

### Cómo usar el script de subida automática:
1. Asegúrate de tener Git instalado en tu máquina.
2. Haz doble clic sobre el archivo **`push_to_github.bat`** (o ejecútalo desde tu terminal con `.\push_to_github.bat`).
3. El script se encargará automáticamente de:
   * Inicializar el repositorio Git local.
   * Añadir todos los archivos del proyecto (respetando las reglas del `.gitignore`).
   * Crear el commit inicial.
   * Vincular tu repositorio con `https://github.com/pabloibanezmoreno-a11y/tft.git`.
   * Subir la rama `main` a GitHub.

*(Nota: Si es la primera vez que usas Git, es posible que el script te pida iniciar sesión en GitHub mediante una ventana emergente para autorizar la subida).*

---

## 📁 Estructura del Proyecto

* **`tft_stallion_boilerplate.py`**: Script de Python consolidado con la implementación paso a paso comentada del preprocesamiento, `TimeSeriesDataSet`, entrenamiento con `pytorch-lightning` y visualización.
* **`requirements.txt`**: Listado de librerías Python requeridas para el entorno.
* **`push_to_github.bat`**: Script de automatización en Windows para subir el código a GitHub con un solo clic.
* **`.gitignore`**: Configuración para omitir de Git archivos compilados, temporales de entrenamiento e imágenes resultantes.
* **`README.md`**: Guía detallada de uso e instrucciones del entorno.
