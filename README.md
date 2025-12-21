# 🚀 Exploradores del Espacio AR

¡Bienvenido a **Exploradores del Espacio AR**! Una aplicación web de Realidad Aumentada (WebAR) diseñada para que los niños exploren planetas en 3D de una manera divertida y educativa.

![WebAR](https://img.shields.io/badge/WebAR-Ready-success)
![A-Frame](https://img.shields.io/badge/A--Frame-1.3.0-red)
![AR.js](https://img.shields.io/badge/AR.js-3.4.7-blue)

## ✨ Características

- 🌍 **Exploración Espacial**: Visualiza planetas como Marte y Júpiter en 3D.
- 📸 **Sin Instalación**: Funciona directamente en el navegador web (Chrome, Safari, Firefox).
- 🖨️ **Marcadores Múltiples**: Soporta múltiples marcadores simultáneamente.
- 🎨 **Interfaz Amigable**: Diseño limpio y fácil de usar, perfecto para niños.
- � **Responsive**: Funciona en móviles, tablets y escritorio.
- ⚙️ **Configuración Fácil**: Panel de configuración para descargar marcadores y compartir la app.

## 📦 Marcadores AR

La aplicación utiliza marcadores especiales que debes imprimir o mostrar en otra pantalla:

| Marcador | Tipo | Modelo 3D | Descripción |
|----------|------|-----------|-------------|
| **Hiro** | Patrón | 🔴 Marte | Marcador de prueba (funciona desde pantallas) |
| **0** | Código de Barras | 🔴 Marte | Requiere impresión para mejor detección |
| **1** | Código de Barras | 🪐 Júpiter | Requiere impresión para mejor detección |
| **2-5** | Código de Barras | 📦 Cajas de Prueba | Para verificar la detección de marcadores |

> **Nota**: Los marcadores de código de barras (0-31) funcionan mucho mejor cuando están impresos en papel blanco. El marcador "Hiro" funciona bien desde pantallas de ordenador/móvil.

## 🚀 Cómo Usar

### 1. Preparación
Necesitas un servidor web local para ejecutar la aplicación (debido a los permisos de cámara).

**Opción A: Python (Recomendado)**
```bash
# En la carpeta del proyecto
python3 -m http.server 8000
```

**Opción B: Node.js**
```bash
npx serve
```

### 2. Iniciar la Aventura
1. Abre tu navegador y ve a `http://localhost:8000` (o la URL de tu servidor).
2. Permite el acceso a la cámara cuando se te solicite.
3. Apunta tu cámara a los marcadores.

### 3. Descargar Marcadores
- Haz clic en el botón de configuración (⚙️).
- Descarga los marcadores individuales o todos en un archivo ZIP.
- ¡Imprímelos para la mejor experiencia!

## 🛠️ Estructura del Proyecto

```
ARTK/
├── index.html          # Aplicación principal (WebAR)
├── models/             # Modelos 3D (formato GLB)
│   ├── Mars_1_6792.glb
│   └── Jupiter_1_142984.glb
├── markers/            # Imágenes de los marcadores
│   ├── hiro.png
│   └── 3x3_parity_6_5/ # Marcadores de código de barras
└── README.md           # Este archivo
```

## 🔧 Tecnologías

- **A-Frame**: Framework para realidad virtual en la web.
- **AR.js**: Biblioteca ligera para realidad aumentada en la web.
- **Three.js**: Motor de renderizado 3D.

## 🐛 Solución de Problemas

- **¿No ves la cámara?**: Asegúrate de estar usando HTTPS o `localhost`. Los navegadores bloquean la cámara en sitios no seguros.
- **¿Modelos oscuros?**: Asegúrate de que hay buena iluminación en la habitación.
- **¿Marcadores no detectados?**: Intenta imprimir los marcadores. Las pantallas a veces reflejan luz que confunde a la cámara.

## 📄 Licencia

Este proyecto es de código abierto y gratuito para uso educativo y personal.

---
¡Disfruta explorando el universo! 🚀🪐
