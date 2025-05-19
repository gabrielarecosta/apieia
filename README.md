# apieia
# 📊 EIA Electricity Data Pipeline

Este proyecto implementa un pipeline de datos **end-to-end** que extrae, transforma y almacena información sobre **el consumo y las ventas de electricidad en Estados Unidos**, proveniente de la API pública de la **Administración de Información Energética (EIA)**.

El pipeline fue desarrollado como proyecto final para la especialización en Ingeniería de Datos de la UTN BA.

---

## 🧠 Objetivos del proyecto

- Implementar una arquitectura moderna de Data Lake (**Bronze, Silver, Gold**).
- Extraer datos históricos y realizar extracción incremental desde una API.
- Almacenar los datos en formato **Delta Lake**.
- Realizar limpieza y transformación de datos usando **Pandas**.
- Automatizar el proceso con buenas prácticas de modularización y gestión de credenciales.

---

## 🛠️ Tecnologías y herramientas

- **Python 3**
- **Pandas**
- **Delta Lake** (`deltalake` library)
- **Requests**
- **Google Colab**
- **API EIA**
- **Data Lake (local y simulado en Colab)**

---

## ⚙️ Arquitectura

El pipeline se estructura en tres capas:

| Capa    | Contenido                                    | Propósito                            |
|---------|----------------------------------------------|--------------------------------------|
| Bronze  | Datos crudos obtenidos directamente de la API | Fuente de verdad                     |
| Silver  | Datos limpiados y estructurados               | Listos para análisis exploratorio    |
| Gold    | Datos refinados                               | Optimizados para dashboards o ML     |

Además, se implementa una lógica para realizar:
- **Extracción full** (todos los datos históricos).
- **Extracción incremental** (último día disponible).

---

> 💡 Nota: en este entorno se simula un data lake en el sistema de archivos local. En producción, esto puede implementarse en Azure Data Lake, S3, etc.

---

## 🔐 Gestión de credenciales

Las credenciales de la API se almacenan de forma segura en un archivo externo llamado `pipeline.conf`, que **no está incluido en el repositorio** (por seguridad) y se encuentra excluido por el archivo `.gitignore`.

### 📄 Cómo crear el archivo `pipeline.conf`

Para ejecutar el pipeline, necesitás crear manualmente este archivo en la raíz del proyecto con el siguiente contenido:

```ini
[tmdb_api]
access_token = TU_TOKEN_AQUI

---

🔑 ¿Cómo obtener el token?
Registrate en la API pública de la EIA.

Una vez que obtengas tu token de acceso, reemplazá TU_TOKEN_AQUI por tu token real.

---

## 🧪 Cómo ejecutar este proyecto

### Opción 1: en Google Colab
1. Abrí el notebook `pipeline.ipynb` en [Google Colab](https://colab.research.google.com).
2. Subí el archivo `pipeline.conf` (token de API).
3. Ejecutá las celdas paso a paso.

### Opción 2: en tu máquina local

1. Cloná el repositorio:
```bash
git clone https://github.com/tu-usuario/eia-electricity-pipeline.git
cd eia-electricity-pipeline

---

## 📬 Contacto

**Gabriela Recosta**  
📍 General Deheza, Córdoba, Argentina  
📧 gabrielarecosta@gmail.com  
🌐 [LinkedIn](https://www.linkedin.com/in/grecosta)

---

## 🏁 Estado

✅ Proyecto finalizado y funcional.  
🚀 En proceso de mejora continua para futuras integraciones cloud y automatización.
