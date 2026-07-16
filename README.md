# Pitch Up 🎬

Teleprompter web para grabar videopitches de concursos: scroll automático, control de velocidad, modo espejo, y un indicador de ritmo que compara tu avance real contra los tiempos objetivo de cada sección del guion.

Nació como herramienta para grabar el videopitch de [Licit AR](https://github.com/Lucho-code/Licit_AR) en el Concurso Soluciones Innovadoras BNA, con el guion de esa presentación ya cargado.

## Uso

Abrí `index.html` en el navegador (o publicá el repo con GitHub Pages) y ponelo al lado de la cámara mientras grabás.

- **▶ Iniciar / ⏸ Pausar** — controla el scroll automático del guion.
- **Velocidad (–/+)** — ajustá el ritmo de scroll a tu forma de hablar.
- **Tamaño de letra (–/+)** — legibilidad según distancia a la pantalla.
- **⇋ Espejo** — invierte el texto para uso con vidrio de teleprompter físico.
- **⛶ Pantalla completa** — sin distracciones al grabar.
- **Chips de sección** (arriba) — saltan a cualquier parte del guion con su tiempo objetivo.
- **Indicador de ritmo** — muestra si vas en horario, adelantado o atrasado respecto al guion.

### Atajos de teclado

| Tecla | Acción |
|---|---|
| `Espacio` | Play / pausa |
| `↑` / `↓` | Subir / bajar velocidad |
| `M` | Modo espejo |
| `F` | Pantalla completa |
| `R` | Reiniciar |

## Personalizar el guion

El contenido está en las secciones `<section data-time="...">` dentro de `index.html`. Cada `data-time` es el segundo objetivo (según el tiempo total del pitch) en el que esa sección debería empezar — usalo para adaptar la herramienta a tu propio guion y duración.

## Stack

HTML, CSS y JavaScript vanilla, sin dependencias ni build step — un solo archivo.
