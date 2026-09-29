# Granja de cerdas en bandas

Simulador 3D docente del manejo de cerdas reproductoras en **banda semanal**. Muestra cómo se mueven los lotes entre cubrición-control, gestación y maternidad. Calcula los **partos por hembra y año** a partir de dos variables: el número de cerdas y el intervalo medio destete–cubrición efectiva (IDC).

**Autor:** Anastasio Argüello Henríquez
Catedrático de Producción Animal, Universidad de Las Palmas de Gran Canaria
ORCID: [0000-0002-4426-0678](https://orcid.org/0000-0002-4426-0678)

## Cómo abrirlo

- **En línea:** una vez activado GitHub Pages en este repositorio (Settings → Pages), la dirección que aparece allí abre el simulador en cualquier navegador, sin necesidad de cuenta.
- **Descargado:** basta con abrir `index.html` en Chrome, Edge o Firefox. Necesita conexión a internet para cargar la librería 3D (Three.js) y las fuentes.

## Qué permite hacer

- Elegir el número de cerdas (42–1500) y el IDC medio (5–40 días).
- Reproducir, pausar y acelerar el tiempo (de 0,5 a 14 días por segundo).
- Ir directamente a cada nave y tocar una cerda para ver su ficha: lote, fase, día de gestación, parto previsto y número de partos.
- Seguir en paneles el resultado teórico y el simulado, las plazas necesarias frente a las construidas y el tamaño de los lotes semana a semana.

## Modelo productivo

| Fase | Duración | Lotes semanales |
|---|---|---|
| Cubrición-control (destete → diagnóstico) | IDC + 21 d | 3,7 con IDC = 5 |
| Gestación (diagnóstico → 7 d antes del parto) | 114 − 21 − 7 = 86 d | 12,3 (12 o 13 a la vez) |
| Maternidad (7 d antes del parto → destete) | 7 + 28 = 35 d | 5 (+ 1 sala en vacío sanitario) |
| **Ciclo** | **114 + 28 + IDC** | **21 con IDC = 5** |

Partos por hembra y año = 365 / (114 + 28 + IDC). Con IDC = 5 días: 365 / 147 = **2,48**.

Supuestos de la simulación:

- El lote es la semana de cubrición. El diagnóstico de gestación, la entrada a maternidad y el destete se hacen por lote, el mismo día. La cubrición y el parto son individuales.
- Cada cerda recibe un IDC al azar: 3 días más una distribución gamma (forma 4) con la media elegida. Si queda cubierta fuera de su semana, pasa a un lote posterior.
- Las instalaciones están dimensionadas para el objetivo de IDC = 5 días: jaulas de cubrición-control para 4 lotes más un 10 %, 13 corrales de gestación y 6 salas de maternidad con parideras para un lote más un 15 %.
- No se modelan reposición, bajas, abortos ni mortalidad de lechones.

## Cómo citarlo

Argüello Henríquez, A. (2026). *Granja de cerdas en bandas: simulador 3D del manejo en banda semanal* (versión 1.0.0) [Software docente]. Universidad de Las Palmas de Gran Canaria.

GitHub ofrece también la cita en el botón **Cite this repository**, a partir del archivo `CITATION.cff`.

## Licencia

© 2026 Anastasio Argüello Henríquez.

Esta obra está bajo una licencia [Creative Commons Reconocimiento-NoComercial-CompartirIgual 4.0 Internacional (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.es). Puede usarse, copiarse y adaptarse en docencia e investigación con estas condiciones:

- **Reconocimiento:** hay que citar al autor.
- **No comercial:** no se permite su uso con fines comerciales.
- **Compartir igual:** las versiones modificadas deben distribuirse con esta misma licencia.

El texto legal completo está en [`LICENSE`](LICENSE).

Componentes de terceros, que conservan sus propias licencias:

- [Three.js](https://threejs.org) (licencia MIT), cargado desde jsDelivr.
- Fuentes Barlow, Barlow Condensed e IBM Plex Mono (SIL Open Font License 1.1), cargadas desde Google Fonts.

## Desarrollo

El modelo productivo y los criterios docentes son del autor. El código se desarrolló con la asistencia de Claude (Anthropic).
