# Google Home Premium 🏠

> **Next-Gen Ambient Intelligence**
> *Gemini Home OS: El fin de Google Assistant. Inteligencia ambiental nativa.*

⚠️ **Aviso Importante (Feb 2026):** Google Assistant Legacy se ha eliminado oficialmente en favor de **Gemini Home OS**. Todos los dispositivos Nest operan ahora bajo este nuevo kernel.

[![Platform](https://img.shields.io/badge/Platform-Google_Home-orange?style=for-the-badge&logo=google-home)](https://home.google.com)
[![Processing](https://img.shields.io/badge/Processing-Edge_AI_%2B_Cloud-blue?style=for-the-badge)](https://home.google.com)

---

## 🏢 Casos de Uso Startup: Oficina Inteligente

### 1. Gestión de Espacios y Eficiencia (CIO/Facilities)
Automatización de la oficina física para ahorrar costes.
*   **Caso**: Apagado de sistemas fuera de horario.
*   **Automatización Gemini**: *"Si no detectas movimiento en la zona de 'Open Space' durante 30 minutos y es después de las 19:00, apaga todas las luces, el aire acondicionado y envía un comando de suspensión a las pantallas de dashboard."*

### 2. Seguridad Física (Vigilancia)
Monitorización inteligente sin personal 24/7.
*   **Caso**: Acceso no autorizado a sala de servidores.
*   **Script**: Si la cámara del rack detecta una **persona** que no lleva el chaleco reflectante (reconocimiento visual avanzado) fuera de horario de mantenimiento -> Alerta crítica al móvil del CTO y grabación en la nube segura.

---

## 📡 Arquitectura IoT Híbrida

Google Home con Gemini utiliza un modelo híbrido. Las consultas rápidas se procesan en el dispositivo (Edge) para latencia cero, mientras que el razonamiento complejo viaja a la nube.

```mermaid
graph TD
    Sensors[Cámaras / Sensores Nest] -->|Video Stream| EdgeTPU[Local Edge TPU]
    EdgeTPU -->|Detección Básica (Persona)| LocalAction[Encender Luz Porche]
    
    Sensors -->|Evento Complejo| CloudGemini[Gemini Cloud Vision]
    UserVoice[Comando de Voz] --> CloudGemini
    
    CloudGemini -->|Razonamiento Multimodal| AutomationEngine
    AutomationEngine -->|Acción Coordinada| Actuators[Luces / Termostato / Cerradura]
    
    CloudGemini -->|Notificación Rica| PhoneApp[App Google Home]
```

---

## 🗣️ Scripting con Lenguaje Natural

Ya no necesitas aprender la sintaxis YAML del "Script Editor" de Google Home. Gemini escribe las automatizaciones por ti.

**Input Usuario:**
> "Quiero que cuando empiece a ver una película en la tele del salón, si es de noche, bajes las persianas, atenúes las luces a azul oscuro y pongas el teléfono en no molestar."

**Output Generado (YAML):**

```yaml
automation:
  starter:
    - type: device.state.SamsungTV
      state: isPlaying
      is: true
      device: Living Room TV
  condition:
    - type: time.between
      after: SUNSET
      before: SUNRISE
  actions:
    - type: device.command.Blinds
      command: close
    - type: device.command.Lights
      params:
        brightness: 20
        color: dark_blue
    - type: assistant.command.Broadcast
      message: "Movie Mode Activated"
```
