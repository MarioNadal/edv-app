# EDV — Escuela de Verano de Jaca

PWA single-file para llevar el día a día de un grupo de la Escuela de Verano de Jaca: asistencia diaria, valoración colectiva, actividades y observaciones (redactadas con ayuda de IA), y fotos. Uso interno, mobile-first, funciona offline salvo la generación de observaciones con IA. Sin backend propio.

Este proyecto nace como una adaptación de la arquitectura de [Kortline](https://github.com/MarioNadal/kortline-app) a un caso de uso completamente distinto (no es una app de baloncesto). Comparten enfoque técnico (single-file, sin build, sin framework) pero no comparten código de dominio ni repositorio.

- **Repo:** (pendiente de crear — repo privado recomendado, ver nota de privacidad más abajo)
- **Grupo gestionado:** 2014 (curso de la Escuela de Verano 2026)
- **Versión estable actual:** v1.0.5

## 1. Qué hace

- Alta de niños y niñas con periodo de inscripción flexible: julio completo, agosto completo, o semanas sueltas (para quienes no vienen el mes entero).
- Pase de lista diario (presente / ausente / justificado) mostrando solo a quienes están inscritos ese día.
- Valoración colectiva del día (1–5 estrellas + texto libre).
- Actividades del día: nombre, notas rápidas del monitor, y un botón para generar la observación redactada con IA a partir de esas notas.
- Fotos por actividad, con visor a tamaño completo y descarga individual.
- Historial navegable por día, con filtro por mes.
- Estadísticas de asistencia por niño/a y exportación a PDF y Excel.
- Copia de seguridad manual en JSON (niños, asistencia, actividades — no incluye fotos).

## 2. Lo que NO hace (fuera de alcance en v1.0.0)

- No sincroniza entre dispositivos ni tiene multiusuario (todo vive en el navegador donde se usa).
- No genera automáticamente observaciones sin que el monitor escriba antes unas notas mínimas: la IA nunca inventa incidencias o datos no indicados.
- No incluye gráficas ni cuadros de mando avanzados.
- No gestiona múltiples grupos a la vez (pensado para un único grupo, 2014).

## 3. Arquitectura

| Elemento | Detalle |
|---|---|
| Stack | HTML + CSS + Vanilla JS, sin dependencias propias, sin build |
| Persistencia de datos | `localStorage`, claves con prefijo `edv:` |
| Persistencia de fotos | `IndexedDB` (base `edvFotos`) — evita saturar el límite de `localStorage` |
| Estado central | Objeto `S` en memoria, serializado a `localStorage` en cada cambio |
| Service Worker | `sw.js`, app-shell precacheado, `CACHE_VERSION` versionada |
| CDN | jsPDF 2.5.1 + autotable 3.8.2, SheetJS 0.18.5, Google Fonts (Barlow Condensed + DM Sans) |
| IA | Llamada directa desde el navegador a la API de Mensajes de Anthropic (Claude), con clave aportada por el usuario |
| Paleta | Teal `#14B8A6`, acento sol `#F5A623`, fondo `#081014` |

### Claves de `localStorage`

| Clave | Contenido |
|---|---|
| `edv:cfg` | Nombre del programa, grupo, año, lema |
| `edv:kids` | Lista de niños y niñas con su periodo de inscripción |
| `edv:days` | Registro diario: asistencia, valoración colectiva, actividades y notas/observaciones |
| `edv:logo` | Logo del programa (base64) |
| `edv:apikey` | Clave de API de Anthropic (ver aviso de seguridad) |
| `edv:aimodel` | Modelo de IA seleccionado |

Las fotos de actividades y de perfil de cada niño/a se guardan en IndexedDB, referenciadas por un identificador desde `edv:days` / `edv:kids`.

## 4. Aviso importante sobre la IA integrada

La generación de observaciones llama directamente a la API de Anthropic desde el propio navegador, usando una clave de API que tú introduces en Ajustes. Esto significa:

- La clave se guarda en `localStorage` de este navegador y viaja en cada petición HTTP.
- Cualquiera con acceso al dispositivo, a las herramientas de desarrollador del navegador, o al código fuente publicado (si el repo o el sitio fueran públicos) podría leer esa clave.
- Recomendación: usa una clave con límite de gasto bajo, no la compartas, y mantén el repositorio en privado.

## 5. Aviso sobre privacidad (datos de menores)

Esta app maneja nombres, asistencia y fotos de menores. Aunque los datos reales solo se guardan en el navegador de quien la usa (no se suben a ningún servidor propio, salvo las notas de la actividad que sí viajan a la API de Anthropic al generar una observación), conviene:

- Mantener el repositorio de GitHub en privado.
- Tener en cuenta que GitHub Pages, incluso con repo privado, publica el sitio en una URL accesible por cualquiera que la conozca si se usa un plan Pro/Team (la protección por login solo existe en GitHub Enterprise Cloud). Si se despliega, hazlo en una URL no indexada y no la compartas públicamente, o usa un hosting alternativo con protección por contraseña.
- Las notas y observaciones no deben incluir datos especialmente sensibles (salud, situación familiar, etc.) salvo que sea estrictamente necesario para la gestión del día.

## 6. Roadmap

| Versión | Estado | Resumen |
|---|---|---|
| v1.0.0 | ✅ Publicada | Asistencia, valoración, actividades + IA, fotos, export PDF/Excel |
| v1.0.1 | ✅ Publicada | Visor/descarga de fotos, repaso visual de la pestaña "Hoy" |
| v1.0.2 | ✅ Publicada | Fix recarga en modal de niño/a, semanas sueltas ocultas si el mes está completo |
| v1.0.3 | ✅ Publicada | Fix sensación de recarga en cada botón, feedback táctil |
| v1.0.4 | ✅ Publicada | La IA respeta el nombre literal de la actividad (no lo sustituye por otro juego) |
| v1.0.5 | ✅ Esta versión | Toast desacoplado del render completo: sin salto de scroll ni parpadeo al copiar/guardar |
| v1.1.0 | 💡 Idea | Gráficas de asistencia, gestión de varios grupos |
| v2.0.0 | 💡 Idea | Backend ligero para sincronizar entre dispositivos del equipo de monitores |
