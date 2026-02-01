# NotebookLM 📓

> **RAG-Powered Knowledge Assistant**
> *Tu base de conocimiento personal con capacidades de síntesis de audio (Deep Dive).*

[![Tech](https://img.shields.io/badge/Tech-RAG_%2B_Long_Context-blue?style=for-the-badge)](https://blog.google/technology/ai/notebooklm-google-ai/)
[![Limit](https://img.shields.io/badge/Context-500_Sources-green?style=for-the-badge)](https://notebooklm.google)

---

## 🏢 Casos de Uso Startup: Gestión del Conocimiento y Calidad

### 1. Encuestas de Calidad y Feedback de Clientes
Análisis cualitativo masivo.
*   **Problema**: Tienes 500 respuestas de texto libre de una encuesta NPS.
*   **Solución**: Subir el CSV a NotebookLM.
*   **Query**: *"Identifica los 3 temas de dolor más recurrentes mencionados por los usuarios detractores. Extrae citas literales que representen estos problemas."*
*   **Resultado**: Insights inmediatos para el equipo de producto sin leer 500 filas.

### 2. Onboarding y Formación de Empleados (Audio)
Convertir manuales aburridos en contenido consumible.
*   **Caso**: Nuevo Manual de Cultura y Procesos (100 páginas).
*   **Acción**: Generar un **Audio Overview (Deep Dive)** tipo podcast donde dos hosts discuten las políticas de la empresa con ejemplos prácticos.
*   **Uso**: Enviar a los nuevos empleados para que lo escuchen en su trayecto al trabajo. Aumenta la retención de información vs lectura obligatoria.

### 3. Soporte y Mantenimiento: "La Biblia del Error"
Base de conocimiento de incidencias.
*   **Acción**: Crear un Notebook con todos los post-mortems de incidencias pasadas y documentación técnica.
*   **Uso**: Cuando ocurre una incidencia crítica, el ingeniero de guardia pregunta: *"¿Hemos tenido problemas de latencia en la base de datos similares a este en el último año? ¿Cómo se solucionaron?"*.

---

## 🧠 Arquitectura RAG (Retrieval-Augmented Generation)

NotebookLM se diferencia de ChatGPT o Gemini estándar porque *groundea* (basa) sus respuestas **exclusivamente** en tus documentos subidos, reduciendo drásticamente las alucinaciones.

```mermaid
graph LR
    subgraph "Ingestión de Datos"
        PDFs[PDF Files] --> Parser
        Web[Web Links] --> Crawler
        Drive[Google Drive] --> Connector
        Parser & Crawler & Connector --> Chunker[Text Chunker]
        Chunker --> Embed[Embedding Model]
        Embed --> VectorDB[Vector Database (User Index)]
    end
    
    subgraph "Inferencia (Query)"
        UserQ[User Question] --> QueryEmbed[Query Embedding]
        QueryEmbed <-->|Similarity Search| VectorDB
        VectorDB -->|Top-K Context| LLM[Gemini 1.5 Pro]
        UserQ --> LLM
        LLM --> Answer[Answer with Citations]
    end
```

---

## 📚 Flujo de Trabajo para Investigadores

### Caso: Tesis Doctoral / Paper Científico

1.  **Source Assembly**: Crea un Notebook llamado "Tesis Cap 1". Sube los 200 papers más relevantes de tu bibliografía (hasta 500 fuentes permitidas).
2.  **Cross-Analysis**:
    *   Query: *"Encuentra contradicciones entre el autor A (2023) y el autor B (2025) respecto a la metodología X"*.
    *   Result: Tabla comparativa con citas clicables que llevan al párrafo exacto del PDF.
3.  **Drafting Support**:
    *   Query: *"Basándote en estas fuentes, escribe un esquema detallado para un estado del arte"*.
4.  **Learning on the Go**: Genera el Audio Overview y escúchalo en el gimnasio para interiorizar las conexiones entre los documentos.
