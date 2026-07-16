# Pitch Up 🎬

Teleprompter web para grabar videopitches: scroll automático, control de velocidad, modo espejo, y un indicador de ritmo que compara tu avance real contra los tiempos objetivo de cada sección del guion.

Un solo archivo HTML, sin dependencias ni build — abrilo en el navegador y listo.

![Captura de Pitch Up](assets/screenshot.png)

## Características

- **Scroll automático** del guion, con velocidad ajustable a tu ritmo de lectura.
- **Acotaciones de cámara diferenciadas** del texto que se lee en voz alta.
- **Indicador de ritmo** ("En horario" / "Adelantado" / "Atrasado") que compara tu posición real de scroll contra el tiempo transcurrido.
- **Navegación por secciones**: chips arriba de la pantalla para saltar a cualquier bloque del guion y practicarlo por partes.
- **Modo espejo**, para usar con un vidrio de teleprompter físico.
- **Pantalla completa** para grabar sin distracciones.

El guion que trae por defecto es una **plantilla de ejemplo** (Apertura, Problema → Solución, Mercado → Producto, Ventaja competitiva, Modelo de negocio, Equipo → Recorrido, Cierre) con placeholders entre corchetes — pensada para reemplazar por tu propio contenido antes de grabar.

## Instalación y uso

### Opción 1 — Online, sin instalar nada (recomendado)

1. Andá a **Settings → Pages** en este repositorio.
2. En "Build and deployment", elegí **Deploy from a branch**, rama `main`, carpeta `/ (root)`, y guardá.
3. A los pocos minutos la app queda publicada en:
   `https://lucho-code.github.io/pitch_up/`
4. Abrí esa URL en el dispositivo que vas a usar para grabar (celular, tablet, laptop).

### Opción 2 — Local, en tu computadora

No requiere Node, ni instalación de paquetes, ni build. Alcanza con:

```bash
git clone https://github.com/Lucho-code/pitch_up.git
cd pitch_up
```

Y después abrir `index.html` con doble clic, o servirlo con cualquier servidor estático simple:

```bash
python3 -m http.server 8000
# abrí http://localhost:8000 en el navegador
```

## Cómo usarlo para grabar

1. Reemplazá el guion de ejemplo por el tuyo (ver sección siguiente).
2. Ubicá la pantalla con Pitch Up justo al lado de (o superpuesta a) la cámara que va a grabar.
3. Presioná **▶ Iniciar** para arrancar el scroll automático.
4. Ajustá la **velocidad** (`–` / `+`, o `↑` `↓` del teclado) hasta encontrar tu ritmo natural de lectura.
5. Mirá el **indicador de ritmo** arriba a la derecha: te avisa en vivo si vas en horario respecto al guion.
6. Los bloques con fondo oscuro e itálica son **acotaciones de cámara** (ej. "[Cámara, mirada directa]") — no se leen en voz alta, son indicaciones de puesta en escena.
7. Usá los **chips de sección** para practicar un bloque puntual sin tener que rebobinar todo el guion.

### Atajos de teclado

| Tecla | Acción |
|---|---|
| `Espacio` | Play / pausa |
| `↑` / `↓` | Subir / bajar velocidad |
| `M` | Modo espejo |
| `F` | Pantalla completa |
| `R` | Reiniciar |

## Personalizar con tu propio guion

Todo el contenido vive en las secciones `<section data-time="...">` dentro de `index.html`. Cada atributo `data-time` es el segundo, sobre el tiempo total del pitch, en el que esa sección debería arrancar — es lo que alimenta la navegación por chips y el indicador de ritmo. Para adaptar la herramienta a tu propio guion:

1. Editá o agregá bloques `<section>` con tu texto, manteniendo `data-time` en segundos crecientes.
2. Usá `<p class="line">` para el texto que se lee en voz alta y `<p class="cue">` para acotaciones de cámara.
3. Ajustá `TOTAL` en el `<script>` al final del archivo si tu pitch dura más o menos de 3 minutos (180 segundos).

## Stack

HTML, CSS y JavaScript vanilla — sin frameworks, sin dependencias, sin paso de build. Un solo archivo (`index.html`) que corre en cualquier navegador moderno.
