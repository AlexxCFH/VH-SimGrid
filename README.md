# VH SimGrid

Ecosistema DIY de simracing: volante de transmision directa, pedalera y
aplicacion de escritorio para configurarlo todo.

- **VH Grid DD15** — base de volante direct drive (STM32, FOC) con force feedback
  propio: efectos HID PID, curva de respuesta, ecualizador de efectos por bandas
  y anti-cogging.
- **VH Axis** — pedalera de 3 pedales (sensores Hall + celula de carga en el
  freno) con curvas por pedal, zona muerta y calibracion guiada.
- **VH Configurador** — aplicacion de Windows para ajustarlo todo en vivo:
  perfiles por tipo de coche, telemetria del juego para las luces del aro,
  modo claro/oscuro y 5 idiomas.

Este repositorio contiene **solo las descargas** (instalador y firmwares).
El codigo fuente se desarrolla en un repositorio privado.

## Descargas

En [Releases](../../releases) encontraras, para cada version:

| Fichero | Que es |
|---|---|
| `VH-SimGrid-Setup-vX.Y.Z.exe` | **Instalador de Windows (recomendado)**: la app + los firmwares. No requiere permisos de administrador. |
| `VH-GridDD15-firmware-vX.Y.Z.hex` | Firmware del volante, solo para flasheo manual con STM32CubeProgrammer. |
| `VH-Axis-pedalera-vX.Y.Z.hex` | Firmware de la pedalera, solo para flasheo manual con avrdude/arduino-cli. |

## Instalacion

1. Descarga y ejecuta el instalador de la ultima release.
2. Abre **VH Configurador**: los perifericos se detectan y conectan solos.
3. Las actualizaciones de firmware se hacen **desde la propia app**, sin
   herramientas externas (el volante ni siquiera necesita el jumper BOOT0).

El unico flasheo manual es el primero del volante (placa nueva, sin firmware):
ponla en DFU con el jumper BOOT0 y flashea el `.hex` con STM32CubeProgrammer.

## Hardware

| Pieza | Base |
|---|---|
| Volante | MKS ODrive Mini (STM32F405, clon ODrive v3.6) + motor hoverboard |
| Pedalera | Arduino Micro + sensores Hall (acelerador/embrague) + celula de carga con INA333 (freno) |
| Aro (provisional) | Arduino Leonardo + LEDs WS2812 (luces de RPM) |

## Soporte

Si algo no funciona, abre una [incidencia](../../issues) indicando la version
instalada y que periferico falla.

## Licencia

Los binarios son **gratuitos para uso personal y no comercial**. No esta
permitido lucrarse con ellos (venderlos, cobrar por instalarlos, usarlos en
equipos de alquiler o centros de simracing...) ni republicarlos fuera de este
repositorio (ver [LICENSE](LICENSE)). Compartir el enlace a este repositorio
es libre; para usos comerciales, contacta con el autor.

Incorporan componentes MIT de terceros (ODrive, TinyUSB) cuyos avisos de
copyright se conservan en el fichero de licencia.

---
Copyright (c) 2026 VH SimGrid
