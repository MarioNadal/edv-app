# Changelog

Formato basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.0.0/).

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
