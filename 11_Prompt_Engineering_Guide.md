# Masterclass de Prompt Engineering 2026 🧙‍♂️✨

> **Domina el Lenguaje de la IA.**
> Guía avanzada de metodologías de prompting específicas para el ecosistema Google AI Pro. Aprende a "hablar" con Antigravity, Flow, Whisk y Gemini 3 Pro.

[![Status](https://img.shields.io/badge/Status-Living_Document-success?style=for-the-badge)](https://one.google.com/ai)
[![Level](https://img.shields.io/badge/Level-Advanced-red?style=for-the-badge)](https://deepmind.google)

---

## 🧠 Paradigmas de Prompting 2026

La ingeniería de prompts ha evolucionado. Ya no se trata solo de "instrucciones claras". En 2026, con modelos multimodales y agentes autónomos, utilizamos nuevas metodologías:

1.  **Context Caching Optimization**: Estructurar prompts para reutilizar el caché de contexto de Gemini y reducir latencia.
2.  **Multimodal Anchoring**: Usar imágenes/video como "anclas" de estilo irremplazables por texto.
3.  **Agentic Goal-Setting**: Definir el "qué" y las "restricciones", dejando el "cómo" al agente (Antigravity).

---

## ⚡ 1. Google Antigravity: Prompting para Agentes

Para Antigravity, no escribes un simple prompt, escribes un **Manifiesto de Agente**. Usamos la metodología **G.C.R. (Goal, Constraints, Resources)**.

### Metodología: G.C.R.
*   **Goal (Objetivo)**: El resultado final deseado, no los pasos.
*   **Constraints (Restricciones)**: Qué NO hacer (crítico para agentes autónomos).
*   **Resources (Recursos)**: Qué herramientas o archivos tiene permiso de usar.

### 📝 Ejemplo de Prompt (System Instruction)

```yaml
# Agent Manifesto: Tech_Lead_Bot
Role: "Eres un Arquitecto de Software Senior especializado en Python y Clean Code."

Goal: "Refactorizar cualquier función de código que se te pase para reducir su complejidad ciclomática por debajo de 5."

Constraints:
  - "NUNCA rompas la funcionalidad existente (verifica con tests)."
  - "NO uses librerías externas nuevas sin pedir permiso explícito."
  - "Si el código es ilegible, pide aclaración antes de tocar nada."

Resources:
  - Access: "Read/Write actual directory"
  - Tool: "Python Interpreter for running unittests"
```

---

## 🎬 2. Flow: Dirección de Cine Generativa

En Flow, el prompt actúa como el Director, el Director de Fotografía y el Escenógrafo simultáneamente. Usamos la metodología **"Layered Directing" (Dirección por Capas)**.

### Metodología: Layered Directing
Estructura el prompt en capas técnicas separadas por paréntesis o bloques lógicos.
1.  `(Cámara & Movimiento)`
2.  `(Iluminación & Atmósfera)`
3.  `(Acción & Sujeto)`
4.  `(Estilo Fílmico)`

### 📝 Ejemplo de Prompt

> **Prompt:**
> `(Camera: Tracking shot, nivel del suelo, movimiento rápido hacia adelante)`
> `(Lighting: Hora dorada, lens flares, alto contraste, sombras largas)`
> `(Action: Un coche deportivo rojo clásico derrapando en una curva de tierra, levantando polvo volumétrico)`
> `(Style: Cine, 35mm film grain, 4k, hiperrealista)`

**Consejo Pro:** Usa términos técnicos de cine (*dolly zoom, rack focus, bokeh*) para controlar la "lente" de la IA.

---

## 🎨 3. Whisk: Remix Visual y Control de Estilo

Whisk brilla cuando necesitas consistencia. La metodología aquí es **"Style Anchoring"**.

### Metodología: Style Anchoring
No describas el estilo con palabras si puedes usar una referencia.
1.  Sube una **Imagen de Ancla** (ej. tu guía de marca).
2.  Escribe el prompt de **Sujeto** (lo que cambia).
3.  Usa el parámetro `--stickiness` (adherencia) para forzar el estilo.

### 📝 Ejemplo de Flujo

*   **Imagen Ancla**: Un render 3D minimalista con colores pastel (marca de la empresa).
*   **Prompt de Texto**: "Un par de zapatillas deportivas flotando en el aire".
*   **Modificador**: `--style-weight: 0.9` (Forzar que se vea idéntico al estilo ancla, ignorando el realismo fotográfico si es necesario).

---

## 📓 4. NotebookLM: Investigación Socrática

Para investigación profunda, usa el **"Interrogatorio Socrático"**. No pidas resúmenes; pide contrastes y huecos en la información.

### Metodología: Socratic Gaps
Pide a la IA que encuentre lo que *falta* o lo que *se contradice* entre tus fuentes.

### 📝 Ejemplos de Prompt

*   **Básico:** "Resume estos 10 PDFs." (❌ Malo)
*   **Pro:** "Actúa como un inversor escéptico. Basado ÚNICAMENTE en estos documentos financieros, identifica 3 inconsistencias entre la estrategia de marketing propuesta y el presupuesto asignado para 2026." (✅ Excelente)
*   **Creativo:** "Genera un diálogo de podcast donde dos expertos debaten acaloradamente sobre la viabilidad de la 'Fase 2' descrita en el documento."

---

## 👨‍💻 5. Developer Program (Vibecoding)

Con *Jules* y *Gemini Code Assist*, el código se escribe describiendo la **intención** y la **vibe**, no la sintaxis.

### Metodología: Intent-First Prompting
Describe el problema de negocio y la experiencia de usuario esperada.

### 📝 Ejemplo de Prompt (en IDE)

> "Crea un componente React para una tarjeta de producto.
> **Vibe**: Tiene que sentirse 'premium', con sombras suaves y una animación sutil al hacer hover (elevarse).
> **Datos**: Muestra precio, título y un botón de 'Comprar' que sea gradiente.
> **Tech**: Usa TailwindCSS y Framer Motion para las animaciones."

---

## 🧠 6. Gemini App: Razonamiento Profundo (Chain-of-Thought)

Para problemas complejos de lógica o estrategia con **Gemini 3 Pro**.

### Metodología: Thread-of-Thought
Pide explícitamente al modelo que "piense en voz alta" antes de dar la respuesta final.

### 📝 Ejemplo de Prompt

> "Necesito diseñar el plan de lanzamiento para el producto X.
> Antes de darme el plan, genera una lista de **Posibles Riesgos** y **Factores de Mercado**.
> Analiza paso a paso cómo cada riesgo podría afectar la fecha de lanzamiento.
> Finalmente, basándote en ese análisis, dame el cronograma óptimo."

---

> *Este documento es parte de la suite de documentación de Google AI Pro.*
