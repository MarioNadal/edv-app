# Changelog

Formato basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.0.0/).

## [1.2.0] — 2026-07-07

### Cambiado — asistencia simplificada a 2 estados
- Eliminado el estado "Justificado" como marca de asistencia independiente: en la práctica no aportaba nada distinto de "Ausente" a efectos de estadísticas. Ahora el ciclo de asistencia es Sin marcar → Presente → Ausente → Sin marcar.
- El motivo de una ausencia (si se conoce) se sigue registrando en **Ausencias**, y aparece como nota informativa junto al niño/a — ya no como un color de estado aparte.
- Migración automática de los días ya guardados con "Justificado" a "Ausente", sin perder ningún dato.
- Historial, Estadísticas, exportación a PDF y a Excel actualizados al nuevo modelo de 2 estados.

### Añadido
- **Archivar niño/a** en vez de solo eliminar: saca al niño/a de "Niños" y "Hoy" pero conserva su historial de asistencia y sus estadísticas (antes, eliminar hacía invisibles esos datos aunque no se borraran). Filtro "Activos / Archivados" en la pestaña Niños, y opción de reactivar en cualquier momento. La eliminación permanente sigue disponible como acción secundaria, más discreta.
- Aviso de nombre duplicado al guardar un niño/a.
- **Compartir resumen del día**: nuevo botón en "Hoy" que junta asistencia, valoración y observaciones de todas las actividades en un único texto, listo para compartir por WhatsApp/email (o copiarlo si el dispositivo no soporta compartir).
- **Ficha individual en PDF**: en Estadísticas, toca un niño/a para exportar su ficha con detalle día a día, sus ausencias justificadas y sus observaciones — útil para compartir con una sola familia sin exponer al resto del grupo.
- **PDF de grupo mucho más cuidado**: logo del programa, colores de marca, resumen general (activos/archivados/días/% medio), tabla con el % de asistencia coloreado (verde ≥90%, ámbar ≥75%, rojo por debajo), apéndice con el detalle de ausencias justificadas y sus motivos, y pie de página con fecha de generación y número de página.

## [1.1.0] — 2026-07-07

### Añadido
- Campo "Motivo" opcional en cada ausencia justificada (p. ej. "vacaciones familiares", "cita médica"), visible junto al rango de fechas.
- Foto/avatar del niño/a en cada fila de la lista de Asistencia de "Hoy", para identificar más rápido al pasar lista.
- Aviso en "Hoy" si llevas 7 días o más sin exportar una copia de seguridad (o si nunca has exportado ninguna), con acceso directo a Ajustes.
- Autocompletado del nombre de actividad con las que ya se han usado en días anteriores (evita reescribir "Piscina" o "Datchball" cada vez).

### Corregido
- Estadísticas, exportación a PDF y exportación a Excel ahora calculan el estado de asistencia igual que "Hoy" (marca explícita, o "Justificado" si hay una ausencia activa ese día), en vez de leer el dato en bruto. Antes, un día con ausencia activa que nunca se hubiera abierto en "Hoy" aparecía como "sin marcar" en los informes.
- Historial muestra también el número de justificados por día (antes solo presentes/ausentes).

## [1.0.12] — 2026-07-07

### Cambiado
- Si un niño/a tiene una ausencia justificada activa ese día y todavía no se ha marcado nada, su asistencia aparece ya como "Justificado" por defecto (antes solo se mostraba un aviso 🟡, pero había que marcarlo a mano). Se puede cambiar en cualquier momento tocando su botón de asistencia, igual que cualquier otra marca.

## [1.0.11] — 2026-07-07

### Cambiado
- Las ausencias justificadas ya no se registran en la ficha de alta/edición de cada niño/a (que solo admitía un rango de fechas). Ahora viven en una sección de grupo nueva, "Ausencias", accesible desde la barra inferior, donde puedes añadir tantos periodos como haga falta por niño/a a lo largo del verano, ver su estado (Activa hoy / Próxima / Finalizada) y editarlos o borrarlos.
- Migración automática: los rangos que ya tuvieran guardados los niños/as se trasladan solos a la nueva sección la primera vez que se abre esta versión, sin perder ningún dato.

## [1.0.10] — 2026-07-05

### Añadido
- Marcado masivo de asistencia: tres botones ("Presentes", "Ausentes", "Justif.") para poner de golpe a todos los niños/as inscritos ese día en el mismo estado, y un enlace para quitar todas las marcas del día. Pide confirmación antes de aplicar, porque sustituye cualquier marca ya puesta.

## [1.0.9] — 2026-07-05

### Cambiado
- Sustituidos los tres botones de asistencia (P/A/J) por un único botón por niño/a que cicla entre Sin marcar → Presente → Ausente → Justificado → Sin marcar, cambiando de color y de texto en cada toque.
- El resumen superior de "Hoy" ahora muestra Presentes, Ausentes, Justificados y Sin marcar (antes incluía el nº de actividades, que ya se ve en su propia sección).

## [1.0.8] — 2026-07-05

### Cambiado
- Los botones de asistencia (P/A/J) se han rediseñado como un único control segmentado (una sola píldora con las tres opciones dentro), igual que el estilo de pestañas ya usado en Historial y en Kortline, en vez de tres botones sueltos con borde individual.

### Añadido
- Rango de fechas opcional para ausencias justificadas ("Desde" / "Hasta") en la ficha de cada niño/a, para los casos en los que se sabe con antelación que no va a venir un tiempo. Se muestra como recordatorio (🟡) en la lista de Niños y junto al nombre en la Asistencia de "Hoy".

## [1.0.7] — 2026-07-05

### Añadido
- Campo "Observaciones" en la ficha de cada niño/a (recordatorios, cambios puntuales de asistencia, alergias, etc.). Se muestra con 📌 tanto en la lista de "Niños" como, sobre todo, junto al nombre en la lista de Asistencia de "Hoy" para no olvidarlo al pasar lista.
- Los nombres de niños/as se guardan siempre en mayúsculas (con migración automática de los que ya estuvieran guardados en minúscula).

### Corregido — CRÍTICO
- El nombre de un niño/a se borraba si, tras escribirlo, se tocaba "Julio completo", "Agosto completo" o una semana suelta antes de pulsar Guardar. El campo de nombre no estaba enlazado al estado de la app mientras se escribía, así que el siguiente render (al tocar cualquier otro botón del modal) lo reconstruía con el valor anterior (vacío). Corregido este input y, por el mismo motivo, el de nombre de actividad nueva y el de la clave de API en Ajustes.

## [1.0.6] — 2026-07-05

### Cambiado
- El botón "Guardar en galería" (antes "Descargar foto") ahora usa la hoja de compartir nativa del móvil (Web Share API) con la opción "Guardar imagen"/"Guardar en Fotos", que sí deja la foto en la galería del dispositivo. La descarga directa por enlace (`<a download>`) no era fiable en móvil — en iOS normalmente no hacía nada, y en Android acababa en la carpeta de Descargas, no en la galería. En ordenador se mantiene la descarga normal a la carpeta de descargas.

## [1.0.5] — 2026-07-05

### Corregido
- El aviso "toast" (p. ej. al copiar una observación, guardar, etc.) forzaba un render completo de la pantalla aunque no cambiara ningún dato, y en algunos navegadores móviles eso provocaba un salto de scroll hacia arriba. El toast ahora es un elemento independiente que se muestra/oculta directamente, sin tocar el resto de la pantalla.
- `render()` restaura explícitamente la posición de scroll tras cada actualización que no cambia de pantalla, como refuerzo adicional frente a saltos del navegador al reemplazar contenido.

## [1.0.4] — 2026-07-05

### Corregido
- La IA a veces sustituía el nombre literal de una actividad por el de otro juego parecido (p. ej. "Datchball" → "dodgeball"). Ahora se le indica explícitamente que use el nombre exacto tal cual lo escribe el monitor, sin traducirlo ni "corregirlo".

## [1.0.3] — 2026-07-05

### Corregido
- `render()` reconstruía toda la pantalla en cada interacción (marcar asistencia, un toast, tocar dentro de un modal…) reiniciando el scroll y repitiendo la animación de entrada, dando sensación de recarga. Ahora el scroll y la animación de "Hoy"/vista solo se disparan al cambiar realmente de pantalla o de día, y el modal solo se desliza hacia arriba la primera vez que se abre.
- Añadido feedback táctil (pequeña presión al tocar) en botones, pills de asistencia, pestañas, filas y estrellas.

## [1.0.2] — 2026-07-05

### Corregido
- El modal de "Nuevo niño/a" recargaba la página al tocar cualquier botón (gesto nativo de "pull-to-refresh" del móvil, activado por el scroll interno del modal). Contenido con `overscroll-behavior`.
- Las semanas sueltas de julio/agosto ahora se ocultan del selector en cuanto ese mes se marca como "completo", evitando el solapamiento confuso entre ambos campos.

## [1.0.1] — 2026-07-05

### Añadido
- Visor de fotos a tamaño completo (toca cualquier miniatura de una actividad) con botón de descarga y de eliminar.
- Resumen rápido del día (presentes, ausentes, justificados, actividades) en la pestaña "Hoy".

### Cambiado
- Repaso visual de la pestaña "Hoy": cabeceras de sección con icono, tarjetas de actividad con más jerarquía y separación, miniaturas de foto más grandes y con mejor tacto.
- `CACHE_VERSION` del Service Worker actualizada a `edv-v1.0.1` para que los dispositivos con la PWA instalada reciban la actualización.

## [1.0.0] — 2026-07-04

### Añadido
- Gestión de niños y niñas del grupo 2014 con periodo de inscripción flexible: julio completo, agosto completo o semanas sueltas.
- Pase de lista diario (presente / ausente / justificado), mostrando solo a quienes están inscritos ese día.
- Valoración colectiva diaria (estrellas 1–5 + texto libre).
- Actividades del día con notas rápidas del monitor y generación de observación redactada con IA (Claude, vía API de Anthropic con clave propia del usuario).
- Adjuntar fotos por actividad (almacenadas en IndexedDB para no saturar `localStorage`).
- Historial de días registrados, filtrable por mes.
- Estadísticas de asistencia por niño/a.
- Exportación de informe de asistencia a PDF y a Excel.
- Copia de seguridad manual en JSON (niños, asistencia, actividades) y restauración desde archivo.
- Logo personalizable desde Ajustes.
- PWA instalable con Service Worker y aviso de actualización disponible.

### Notas
- La clave de API de IA se guarda en `localStorage` del navegador — ver aviso de seguridad en el README antes de desplegar.
- Sin backend: todo el dato vive en el dispositivo donde se usa la app.
