# Whisk 🧪

> **Experimental Style Transfer & Image-to-Video Lab**
> *The creative sandbox for visual remixing and motion injection.*

[![Lab](https://img.shields.io/badge/Google_Labs-Experimental-yellow?style=for-the-badge&logo=google)](https://labs.google)
[![Tech](https://img.shields.io/badge/Tech-Diffusion_Transformers-green?style=for-the-badge)](https://research.google)

---

## 🏢 Casos de Uso Startup: Diseño y Branding Ágil

### 1. Newsletter Corporativa Dinámica
Olvídate de las cabeceras estáticas.
*   **Caso**: Newsletter semanal de novedades de la startup.
*   **Acción**:
    *   Tomar el logo de la empresa o la imagen destacada del post del blog.
    *   Usar Whisk para añadir un movimiento sutil (ej. brillo recorriendo el logo, o nubes moviéndose tras el edificio de la oficina).
    *   Exportar como GIF ligero e incrustar en el email.
    *   **Resultado**: Aumento del CTR por impacto visual.

### 2. Mockups de Producto Vivos (UX/UI)
Presentación de prototipos a stakeholders.
*   **Caso**: Mostrar cómo se vería la nueva app en un móvil.
*   **Acción**:
    *   Subir captura de pantalla de la UI (Figma).
    *   Usar "Motion Brush" para simular el scroll de una lista o la pulsación de un botón (efecto ripple).
    *   Integrar en diapositivas de presentación sin necesidad de programar el prototipo real.

### 3. A/B Testing de Anuncios (Ads)
Generación masiva de variaciones creativas.
*   **Caso**: Facebook/Instagram Ads.
*   **Acción**:
    *   Tener una sola imagen de producto "ganadora".
    *   Usar **Style Swap** para generar 20 variantes artísticas (estilo cómic, estilo neon, estilo acuarela, estilo 3D clay).
    *   Lanzar campaña para ver qué estética resuena mejor con la audiencia sin contratar a 20 ilustradores.

---

## 🖌️ Concepto Técnico: "Visual Remixing"

Whisk utiliza un pipeline avanzado de **ControlNet** y **Image-to-Image** para separar el contenido (estructura) del estilo (textura/iluminación).

### Pipeline de Procesamiento

```mermaid
graph TD
    Input[Input Image] --> Encoder
    Style[Style Prompt / Reference Image] --> StyleEncoder
    
    Encoder --> LatentSpace
    StyleEncoder --> LatentSpace
    
    LatentSpace -->|Fusion & Denoising| Diffusion[Diffusion Model]
    Diffusion -->|Inject Motion Vectors| Motion[Motion Module]
    
    Motion --> VideoOutput[Looping Video (MP4/GIF)]
```

---

## 🕹️ Funcionalidades Clave

### 1. Motion Brushing (Pinceles de Movimiento)
En lugar de animar toda la imagen, pintas una máscara de "flujo".
*   **Vector Arrows**: Dibuja flechas sobre el agua para indicar la dirección de la corriente.
*   **Anchors**: Coloca puntos de ancla sobre elementos que deben permanecer estáticos (ej. rocas, edificios).

### 2. Style Swap (Intercambio de Estilo)
*   **Input**: Foto de un boceto en servilleta.
*   **Style Reference**: "Van Gogh Starry Night".
*   **Output**: Tu boceto renderizado con pinceladas de óleo giratorias, manteniendo la composición exacta de la servilleta.
