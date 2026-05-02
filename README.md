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
```

```mermaid
flowchart TD
    A[Frontend] --> B[API Gateway]

    B --> C1[Servicio EEG]
    B --> C2[Servicio ML]
    B --> C3[Auth]

    C1 --> D[(Storage EEG)]
    C2 --> E[(Modelos ML)]
    C3 --> F[(Usuarios DB)]
```

```mermaid
flowchart TD
    A[Upload EEG] --> B[API]
    B --> C[(Storage)]
    B --> D[Queue]

    D --> E[Worker]
    E --> F[Procesamiento]
    F --> G[(Resultados)]

    G --> H[Frontend]
```

```mermaid
flowchart TD
    A[EEG] --> B[Normalización]
    B --> C[Segmentación]
    C --> D[FFT]

    D --> E1[Delta]
    D --> E2[Theta]
    D --> E3[Alpha]
    D --> E4[Beta]

    E1 --> F[Clasificación]
    E2 --> F
    E3 --> F
    E4 --> F

    F --> G[Fases]

```
```mermaid
flowchart TD
    A[Usuario] --> B[Frontend]
    B --> C[Sube EEG]

    C --> D[Backend]
    D --> E[(Storage)]

    D --> F[Queue]
    F --> G[Worker]

    G --> H[Procesamiento]
    H --> I[Clasificación]

    I --> J[(Resultados)]
    J --> B
```

```mermaid
flowchart LR
    A[MVP] --> B[Backend]
    B --> C[Servicios]
    C --> D[Microservicios]
```
```mermaid
flowchart TD
    A[Usuario]
    B[API]
    C[(Storage)]
    D[Queue]
    E[Worker]
    F[Procesamiento]
    G[(Resultados)]
    H[Frontend]

    A --> B
    B --> C
    B --> D
    D --> E
    E --> F
    F --> G
    G --> H
