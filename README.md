# plataforma-egg---hackton-v0
proyecto desarrollado para la presentación de la hakaton
# 🧠 EEG Brain Phase Classifier

Aplicación web para analizar señales de electroencefalograma (EEG) y convertirlas en **fases del cerebro** (vigilia, sueño ligero, profundo, REM).

---

# 🚀 Visión

Democratizar el análisis de EEG haciéndolo visual, accesible y rápido desde el navegador.

---

# 🧩 Arquitectura

## 🧠 MVP (Frontend Only)

```mermaid
flowchart TD
    A[Usuario] --> B[Upload EEG]
    B --> C[Parsing JS]
    C --> D[Análisis básico]
    D --> E[Clasificación reglas]
    E --> F[Visualización]
