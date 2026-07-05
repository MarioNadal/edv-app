# Changelog

Formato basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.0.0/).

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
