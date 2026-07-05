# Changelog

Formato basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.0.0/).

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
