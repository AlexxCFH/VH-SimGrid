<h1 align="center">VH SimGrid</h1>

<div align="center">
  <img src="https://img.shields.io/github/v/release/AlexxCFH/VH-SimGrid?style=for-the-badge&label=Versi%C3%B3n&color=FF073A" alt="Última versión">
  <img src="https://img.shields.io/github/downloads/AlexxCFH/VH-SimGrid/total?style=for-the-badge&label=Descargas&color=00599C" alt="Descargas">
  <img src="https://img.shields.io/badge/Windows-10%2F11-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows">
  <img src="https://img.shields.io/badge/Licencia-Gratis_uso_personal-3DDC84?style=for-the-badge" alt="Licencia">
</div>

<div align="center">
  <img src="https://img.shields.io/badge/Volante-Direct_Drive_FFB-orange?style=for-the-badge&logo=usb&logoColor=white" alt="FFB">
  <img src="https://img.shields.io/badge/Pedalera-3_pedales_(c%C3%A9lula_de_carga)-00979D?style=for-the-badge&logo=arduino&logoColor=white" alt="Pedalera">
  <img src="https://img.shields.io/badge/Aro-Luces_RPM_%2B_botones-FF073A?style=for-the-badge&logo=arduino&logoColor=white" alt="Aro">
  <img src="https://img.shields.io/badge/App-VH_SimGrid-41CD52?style=for-the-badge&logo=qt&logoColor=white" alt="VH SimGrid">
</div>

## Descripción

Ecosistema **simracing DIY completo**, desarrollado y probado sobre hardware real:

- **VH Grid DD15** — volante direct drive de force feedback. Windows lo detecta
  como un volante FFB nativo (USB HID PID): sin drivers ni software residente
- **VH Axis** — pedalera de 3 pedales: acelerador y embrague con sensores Hall,
  y freno con célula de carga (mide fuerza real, no recorrido)
- **VH Formula Apex** — aro con tira de LEDs de RPM y eventos, matriz de
  botones y encoders, configurable al detalle desde la app
- **VH SimGrid** — la aplicación de escritorio que configura los tres
  periféricos en vivo, sin reflashear, y además trae **dash**, **ingeniero de
  pista por voz** y **análisis de telemetría**

Este repositorio contiene **las descargas oficiales** (instalador y firmwares).
Es el único canal de distribución.

## Descargas

En [Releases](../../releases) encontrarás, para cada versión:

| Fichero | Qué es |
|---|---|
| `VH-SimGrid-Setup-vX.Y.Z.exe` | **Instalador de Windows (recomendado)**: la app + los firmwares. Sin permisos de administrador. |
| `VH-GridDD15-firmware-vX.Y.Z.hex` | Firmware del volante, solo para flasheo manual con STM32CubeProgrammer. |
| `VH-Axis-pedalera-vX.Y.Z.hex` | Firmware de la pedalera, solo para flasheo manual con arduino-cli/avrdude. |
| `VH-FormulaApex-aro-vX.Y.Z.hex` | Firmware del aro, solo para flasheo manual con arduino-cli/avrdude. |

## Instalación

1. Descarga y ejecuta el instalador de la última release.
2. Abre **VH SimGrid**: los periféricos se detectan y conectan solos. La
   primera vez, un asistente te guía por el volante, los pedales, el aro y la
   telemetría de tus juegos.
3. Las actualizaciones de firmware se hacen **desde la propia app**, sin
   herramientas externas: al conectar un periférico, si hay firmware nuevo la
   app te ofrece grabarlo con un clic (el volante ni siquiera necesita el jumper
   BOOT0; el aro y la pedalera se graban sin instalar nada).

> El único flasheo manual es el primero del volante (placa nueva, sin firmware):
> ponla en DFU con el jumper BOOT0 y flashea el `.hex` con STM32CubeProgrammer.
> Al actualizar, el instalador conserva perfiles, dashes y calibración.

## Qué incluye

### Volante (VH Grid DD15)

**FFB nativo de DirectInput** — constant force, spring, damper, friction e
inertia con ganancias independientes; rango de giro de 90° a 1440°.

**Ecualizador de efectos por bandas** — 6 bandas de frecuencia (0–200%) para
matizar qué se siente: peso de la dirección, pianos, ABS, grava...

**Registro en vivo** del giro y de la fuerza de los últimos segundos, con la
línea de clipping marcada.

**Anti-cogging** — calibración automática que elimina el rizado magnético del
motor; se guarda en flash.

**Seguridad probada en choques reales** — guardia de sobrevelocidad,
protección térmica, tope de giro progresivo, limitador de regeneración y
detector de oscilaciones.

### Pedalera (VH Axis)

- Curva de respuesta arrastrable **por pedal**, con preajustes, zona muerta e
  inversión del sentido
- **Freno por kg objetivo** gracias a la célula de carga
- Calibración guiada desde la app y **guardado automático** en la EEPROM

### Aro (VH Formula Apex)

- **Luces de RPM por LED**: tablero configurable con umbrales, colores en
  degradado, destello al corte y ajuste automático al régimen real de cada coche
- **Luces por eventos**: banderas, TC/ABS/DRS/ERS, limitador y pit lane,
  spotter de proximidad, barras de freno/acelerador/combustible... con estilos
  (fijo, parpadeo, respiración, desplazamiento) y perfiles por juego y por coche
- **Matriz de botones y encoders** integrados, y brillo que se recuerda aunque
  arranque sin PC

### Dash

Tableros en el monitor que elijas, con **galería y editor integrado**: textos,
agujas, barras, gauges e imágenes, con deshacer y vista previa en vivo. Trae
**una veintena de dashes listos** (GT3, F1, Formula Alpha 2026...) y se pueden
exportar e importar en un `.zip`.

### Ingeniero de pista

**Te habla mientras conduces**: combustible, gomas, presiones, daños,
estrategia, rivales, ritmo, spotter y, al cruzar la meta, tu resultado y qué
mejorar. Elige cuándo hablar para no hacerlo en plena frenada, y **se le
pregunta por voz** con un botón del aro. Voces en **español e inglés**, todo
procesado en tu equipo.

### Análisis

Tus sesiones grabadas, canal a canal, al estilo de **MoTeC i2**: vueltas,
sectores y curvas, comparación contra una vuelta de referencia y zoom común a
todas las gráficas.

### La aplicación

**Telemetría de 18 juegos**: Assetto Corsa, ACC, AC EVO, AC Rally, Le Mans
Ultimate, iRacing, RaceRoom, Automobilista 1 y 2, rFactor 2, F1, DiRT Rally,
EA WRC, BeamNG y los simuladores de camiones, entre otros.

**Perfiles por tipo de coche** (Formula, GT3, GT2, Hypercar, Rally...), con
opción de que se apliquen solos al detectar el juego.

**Copia de seguridad completa**: exporta e importa todos los ajustes y perfiles
en un solo fichero.

Modo oscuro y claro · español e inglés · conexión y reconexión automáticas ·
ventana sin marco con estética propia.

## Hardware

| Pieza | Base |
|---|---|
| Volante | MKS ODrive Mini (STM32F405) + motor de hoverboard |
| Pedalera | Arduino Micro + sensores Hall + célula de carga con INA333 |
| Aro | ATmega32U4 + LEDs WS2812 + matriz de botones + encoders (MCP23017) |

## Privacidad

Nada sale de tu equipo: la voz del ingeniero y el reconocimiento de lo que
dices funcionan en local, y tus grabaciones de telemetría se quedan en tu disco.

## Soporte

Si algo no funciona, abre una [incidencia](../../issues) indicando la versión
instalada y qué periférico falla. Desde la app, **Guardar diagnóstico** genera
un fichero con lo necesario para adjuntarlo.

## Licencia

Los binarios son **gratuitos para uso personal y no comercial**. No está
permitido lucrarse con ellos (venderlos, cobrar por instalarlos, usarlos en
equipos de alquiler o centros de simracing...) ni republicarlos fuera de este
repositorio (ver [LICENSE](LICENSE)). Compartir el enlace a este repositorio es
libre; para usos comerciales, contacta con el autor.

Incorporan componentes MIT de terceros (ODrive, TinyUSB) cuyos avisos de
copyright se conservan en el fichero de licencia. La voz y el reconocimiento
usan [Piper](https://github.com/rhasspy/piper) (MIT) y
[Vosk](https://alphacephei.com/vosk/) (Apache 2.0).

### Créditos de las voces

Cada voz del ingeniero viene de un dataset con su propia licencia:

| Voz | Origen | Licencia |
|---|---|---|
| *Lucía* (es_ES-sharvard) | [Sharvard Corpus](https://datashare.ed.ac.uk/handle/10283/574), V. Aubanel, M. L. García Lecumberri y M. Cooke, The University of Edinburgh | [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/) |
| *Emily* (en_US-libritts_r) | [LibriTTS-R](https://www.openslr.org/141/) | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |
| *Harry* (en_GB-northern_english_male) | [openslr.org/83](https://www.openslr.org/83/) | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) |
| *Sergio* (es_ES-davefx) | — | CC0 (dominio público) |

Las voces se distribuyen sin modificar, cada una con su ficha (`MODEL_CARD`)
junto al modelo.

## Contacto

<div align="center">
  <a href="mailto:avillenaherreros1373@gmail.com">
    <img src="https://img.shields.io/badge/Correo-avillenaherreros1373%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Correo">
  </a>
  <a href="https://www.linkedin.com/in/alejandro-villena-herreros-aaa901388/">
    <img src="https://img.shields.io/badge/LinkedIn-Alejandro_Villena-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
  <a href="https://github.com/AlexxCFH">
    <img src="https://img.shields.io/badge/GitHub-AlexxCFH-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  </a>
</div>

---
<div align="center">Copyright © 2026 VH SimGrid</div>
