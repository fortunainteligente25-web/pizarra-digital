# 🖐️ Pizarra Digital Gestual

Pizarra digital controlada 100% por gestos de mano, sin tocar la pantalla. Construida con **MediaPipe Hands** y **HTML5 Canvas**, corriendo directamente en el navegador — sin instalación ni backend.

🔗 **Demo en vivo:** https://fortunainteligente25-web.github.io/pizarra-digital/

## ✨ Características

- Dibujo en tiempo real siguiendo la punta del dedo índice
- Selector de color y grosor de trazo ajustable
- Detección de gestos mediante los 21 landmarks de MediaPipe Hands
- Funciona enteramente en el cliente (no requiere servidor propio en producción)

## 🖐️ Gestos disponibles

| Gesto | Acción |
|---|---|
|  Solo índice extendido | Dibujar |
|  Dos dedos extendidos | Borrador |
|  Palma abierta | Pausa |
|  Pellizco (índice + pulgar) | Zoom in / out |

## 🛠️ Stack técnico

- **MediaPipe Hands** — detección de landmarks de mano en tiempo real
- **HTML5 Canvas** — renderizado del trazo
- **JavaScript vanilla** — lógica de detección de gestos y dibujo
- **camera_utils.js** — gestión del stream de la cámara

## 🚀 Cómo ejecutarlo en local

Como usa `getUserMedia` (acceso a cámara), el navegador requiere `https://` o `localhost` — no funciona abriendo el archivo directamente con doble clic.

1. Clona el repositorio:
   ```bash
   git clone https://github.com/fortunainteligente25-web/pizarra-digital.git
   ```
2. Sirve la carpeta con un servidor local, por ejemplo:
   ```bash
   python -m http.server 8000
   ```
3. Abre `http://localhost:8000` en el navegador y concede permiso de cámara.

##  El reto técnico

La parte más delicada no fue conectar la cámara, sino diferenciar con fiabilidad un dedo "extendido" de uno "doblado". Esto se resuelve comparando la posición de la punta de cada dedo respecto a sus articulaciones intermedias (landmarks), en vez de usar umbrales fijos de posición absoluta.

## 📌 Estado del proyecto

Proyecto #2 de una serie de experimentos de aprendizaje ("Building in Public"). Precedido por [URL Guardian](https://github.com/fortunainteligente25-web/agente-phising), una herramienta de detección de phishing en C++.

## 📄 Licencia

MIT
