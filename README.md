# VH SimGrid

<div align="center">
  <img src="https://img.shields.io/github/v/release/AlexxCFH/VH-SimGrid?style=for-the-badge&label=Versi%C3%B3n&color=FF073A" alt="Última versión">
  <img src="https://img.shields.io/github/downloads/AlexxCFH/VH-SimGrid/total?style=for-the-badge&label=Descargas&color=00599C" alt="Descargas">
  <img src="https://img.shields.io/badge/Windows-10%2F11-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows">
  <img src="https://img.shields.io/badge/Licencia-Gratis_uso_personal-3DDC84?style=for-the-badge" alt="Licencia">
</div>

<div align="center">
  <img src="https://img.shields.io/badge/Volante-Direct_Drive_FFB-orange?style=for-the-badge&logo=usb&logoColor=white" alt="FFB">
  <img src="https://img.shields.io/badge/Pedalera-3_pedales_(c%C3%A9lula_de_carga)-00979D?style=for-the-badge&logo=arduino&logoColor=white" alt="Pedalera">
  <img src="https://img.shields.io/badge/App-VH_Configurador-41CD52?style=for-the-badge&logo=qt&logoColor=white" alt="Configurador">
</div>

## 📋 Descripción

Ecosistema **simracing DIY completo**, desarrollado y probado sobre hardware real:

- **VH Grid DD15** — volante direct drive de force feedback. Windows lo detecta
  como un volante FFB nativo (USB HID PID): sin drivers ni software residente
- **VH Axis** — pedalera de 3 pedales: acelerador y embrague con sensores Hall,
  y freno con célula de carga (mide fuerza real, no recorrido)
- **VH Configurador** — la aplicación de escritorio que lo configura todo en
  vivo, sin reflashear

Este repositorio contiene **las descargas oficiales** (instalador y firmwares).
Es el único canal de distribución.

## 📥 Descargas

En [Releases](../../releases) encontrarás, para cada versión:

| Fichero | Qué es |
|---|---|
| `VH-SimGrid-Setup-vX.Y.Z.exe` | 🟢 **Instalador de Windows (recomendado)**: la app + los firmwares. Sin permisos de administrador. |
| `VH-GridDD15-firmware-vX.Y.Z.hex` | Firmware del volante, solo para flasheo manual con STM32CubeProgrammer. |
| `VH-Axis-pedalera-vX.Y.Z.hex` | Firmware de la pedalera, solo para flasheo manual con arduino-cli/avrdude. |

## 🚀 Instalación

1. Descarga y ejecuta el instalador de la última release.
2. Abre **VH Configurador**: los periféricos se detectan y conectan solos.
3. Las actualizaciones de firmware se hacen **desde la propia app**, sin
   herramientas externas (el volante ni siquiera necesita el jumper BOOT0).

> El único flasheo manual es el primero del volante (placa nueva, sin firmware):
> ponla en DFU con el jumper BOOT0 y flashea el `.hex` con STM32CubeProgrammer.
> Al actualizar, el instalador conserva perfiles y calibración.

## ✨ Qué incluye

### 🎮 Volante (VH Grid DD15)

🧲 **FFB nativo de DirectInput** — constant force, spring, damper, friction e
inertia con ganancias independientes; rango de giro de 90° a 1440°.

🎛️ **Ecualizador de efectos por bandas** — 6 bandas de frecuencia (0–200%) para
matizar qué se siente: peso de la dirección, pianos, ABS, grava...

🧈 **Anti-cogging** — calibración automática que elimina el rizado magnético del
motor; se guarda en flash.

🛡️ **Seguridad probada en choques reales** — guardia de sobrevelocidad,
protección térmica, tope de giro progresivo, limitador de regeneración y
detector de oscilaciones.

### 🦶 Pedalera (VH Axis)

- Curva de respuesta arrastrable **por pedal**, con preajustes, zona muerta e
  inversión del sentido
- **Freno por kg objetivo** gracias a la célula de carga
- Calibración guiada desde la app y **guardado automático** en la EEPROM

### 🖥️ VH Configurador

📊 Estado en vivo, ajustes en tiempo real y **perfiles por tipo de coche**
(Formula, GT3, GT2, Hypercar, Rally...).

🚦 **Luces de RPM en el aro**: la app lee la telemetría del juego (Assetto
Corsa / ACC, más juegos en camino) y las alimenta sola en segundo plano.

🎨 Modo oscuro y claro · 🌍 5 idiomas (español, inglés, catalán, gallego y
euskera) · 🔌 conexión y reconexión automáticas · 🪟 ventana sin marco con
estética propia.

## 🔧 Hardware

| Pieza | Base |
|---|---|
| Volante | MKS ODrive Mini (STM32F405) + motor de hoverboard |
| Pedalera | Arduino Micro + sensores Hall + célula de carga con INA333 |
| Aro (provisional) | Arduino Leonardo + LEDs WS2812 (luces de RPM) |

## 🆘 Soporte

Si algo no funciona, abre una [incidencia](../../issues) indicando la versión
instalada y qué periférico falla.

## 📜 Licencia

Los binarios son **gratuitos para uso personal y no comercial**. No está
permitido lucrarse con ellos (venderlos, cobrar por instalarlos, usarlos en
equipos de alquiler o centros de simracing...) ni republicarlos fuera de este
repositorio (ver [LICENSE](LICENSE)). Compartir el enlace a este repositorio es
libre; para usos comerciales, contacta con el autor.

Incorporan componentes MIT de terceros (ODrive, TinyUSB) cuyos avisos de
copyright se conservan en el fichero de licencia.

---
<div align="center">Copyright © 2026 VH SimGrid</div>
