# Manual de usuario — EDV (v1.2.0)

## 1. Primeros pasos

1. Abre `index.html` en el navegador del móvil o del ordenador que vayas a usar cada día.
2. Ve a **Ajustes** y revisa el nombre del programa, el grupo (por defecto "2014") y el año. Sube tu logo si quieres personalizarlo.
3. Si quieres usar la generación de observaciones con IA, ve a **Ajustes → Generación de observaciones con IA** y pega tu clave de API de Anthropic. Lee antes el aviso de seguridad que aparece justo encima del campo.
4. Añade a los niños y niñas del grupo en la pestaña **Niños**.

La app funciona offline salvo el botón "Generar observación con IA", que necesita conexión.

## 2. Añadir niños y niñas

En **Niños**, pulsa el botón `+`. Para cada uno indica:

- Nombre (se guarda automáticamente en mayúsculas).
- Periodo de inscripción:
  - **Julio completo** / **Agosto completo**: actívalo si viene todos los días lectivos de ese mes.
  - **Semanas sueltas**: si no viene el mes entero, marca solo las semanas concretas en las que sí participa. No hace falta combinar esto con los interruptores de mes completo — usa una cosa u otra según el caso de cada niño/a.
- **Observaciones**: para cualquier otro recordatorio o cambio puntual que te comenten (por ejemplo, "recogida solo por su madre", una alergia, etc.). Se muestra con 📌 tanto en la lista de Niños como junto a su nombre en la lista de Asistencia de "Hoy".
- Foto (opcional).

Puedes editar a un niño/a en cualquier momento tocando su fila. Si deja el grupo, lo normal es **archivarlo** en vez de eliminarlo (ver más abajo): conserva su historial de asistencia y sus estadísticas, y puedes reactivarlo si vuelve. Si ya has registrado un niño/a con un nombre igual, la app te avisa antes de guardar por si es un duplicado sin querer.

**Archivar / reactivar / eliminar:** dentro de la ficha de un niño/a activo verás el botón **"🗄️ Archivar niño/a"** — lo saca de "Niños" y de "Hoy", pero mantiene todo su histórico visible en Estadísticas y en las exportaciones. En la pestaña Niños aparece entonces un filtro **Activos / Archivados** para verlo y, si hace falta, tocar **"↩️ Reactivar niño/a"** en su ficha. Si de verdad quieres borrarlo todo sin dejar rastro (incluidas sus ausencias registradas), usa el enlace pequeño **"Eliminar definitivamente"** al final de su ficha — a diferencia de archivar, esto no se puede deshacer y deja de aparecer en Estadísticas.

## 3. Ausencias justificadas

Si un niño/a avisa con antelación de que va a faltar un tiempo, apúntalo en la pestaña **Ausencias** (no en su ficha, para poder guardar varios periodos distintos a lo largo del verano si hace falta). Pulsa `+`, elige el niño/a, pon la fecha "Desde" y/o "Hasta" que se sepan (puedes rellenar solo una de las dos si no conoces la otra) y, si quieres, un motivo breve (por ejemplo, "vacaciones familiares" o "cita médica").

Cada periodo se muestra con su estado — **Activa hoy**, **Próxima** o **Finalizada** — y aparece como recordatorio 🟡 tanto en la lista de Niños como junto al nombre en la Asistencia de "Hoy" (solo en los días dentro de ese rango). Además, si ese día todavía no habías marcado nada para ese niño/a, la asistencia aparece ya puesta como "Ausente" en cuanto entras en la pantalla, con el motivo visible como nota — puedes cambiarla en cualquier momento tocando su botón de asistencia, por ejemplo si al final sí ha venido.

## 4. El día a día (pestaña "Hoy")

Al abrir la app verás el día de hoy. Usa las flechas `‹` `›` para moverte a otro día (por ejemplo, para completar un día que se te olvidó).

**Asistencia:** aparecen solo los niños y niñas inscritos ese día concreto. Cada uno tiene un único botón que cambia de color y de texto cada vez que lo tocas, en este orden: Sin marcar → Presente → Ausente → Sin marcar (y vuelta a empezar). Arriba del todo tienes un resumen con el número de presentes, ausentes y sin marcar del día.

Si un día viene (o falta) todo el grupo, usa los botones "Marcar todo el grupo" (Presentes / Ausentes) para marcar a todos de golpe, o "Quitar todas las marcas de hoy" para empezar de cero. Estas acciones piden confirmación porque sustituyen cualquier marca que ya hubieras puesto ese día.

**Valoración colectiva:** puntúa el día con estrellas (1 a 5) y añade, si quieres, un comentario general sobre cómo ha ido el grupo.

**Actividades:**
1. Pulsa "+ Añadir actividad" y ponle un nombre (por ejemplo, "Datchball", "Piscina", "Taller de manualidades"). Si ya has usado ese nombre otro día, te aparecerá como sugerencia al escribir.
2. Escribe unas notas rápidas: qué se ha hecho, cómo ha ido, y cualquier incidencia relevante (un retraso en una recogida, un pequeño conflicto, etc.). Cuanto más claras sean las notas, mejor será la observación generada.
3. Pulsa "✨ Generar observación con IA". En unos segundos aparecerá un párrafo redactado listo para compartir con las familias o guardar como registro. Puedes editar las notas y volver a generar cuantas veces quieras — cada generación sustituye a la anterior.
4. Añade fotos de la actividad con el botón de la cámara. Toca cualquier miniatura para verla a tamaño completo. Con "💾 Guardar en galería" se abre la hoja de compartir del móvil: elige la opción "Guardar imagen" o "Guardar en Fotos" para que quede en la galería del dispositivo (por seguridad, ninguna web puede guardar ahí directamente sin ese paso). También puedes eliminar la foto desde el mismo visor.

La IA nunca inventa incidencias que no hayas escrito en las notas: solo redacta a partir de lo que le indiques.

**Compartir resumen del día:** al final de la pantalla, el botón "📤 Compartir resumen del día" junta la asistencia, la valoración colectiva y las observaciones de todas las actividades en un único texto, y abre la hoja de compartir del móvil (WhatsApp, email...) para mandarlo de una vez. Si el dispositivo no permite compartir, lo copia al portapapeles.

## 5. Historial

En **Historial** puedes ver todos los días registrados, con filtro por Julio/Agosto. Tocar un día te lleva directamente a su vista de "Hoy" para revisarlo o completarlo.

## 6. Estadísticas y exportación

En **Estadísticas** verás el porcentaje de asistencia de cada niño/a (calculado solo sobre los días en los que estaba inscrito; los niños/as archivados también aparecen, marcados como "(archivado)"). Desde ahí puedes:

- **Exportar PDF**: informe de grupo con logo y colores del programa, un resumen general (activos, archivados, días registrados y % de asistencia medio), la tabla de días/presente/ausente/% por niño/a con el porcentaje coloreado (verde ≥90%, ámbar ≥75%, rojo por debajo), y un apéndice con el detalle de las ausencias justificadas registradas y su motivo.
- **Exportar Excel**: cuadrícula completa de asistencia día a día, lista para revisar o compartir.
- **Ficha individual en PDF**: toca directamente sobre un niño/a en la lista para exportar solo su ficha (detalle día a día, sus ausencias justificadas y sus observaciones) — útil si necesitas compartir el informe de un único niño/a con su familia sin exponer al resto del grupo.

## 7. Copia de seguridad

En **Ajustes → Copia de seguridad**:

- **Exportar copia de seguridad**: descarga un archivo `.json` con niños, asistencia, actividades y ausencias justificadas (las fotos no se incluyen en este archivo, ya que se guardan aparte en el dispositivo).
- **Restaurar desde copia de seguridad**: sustituye los datos actuales por los del archivo elegido. Úsalo con cuidado — es una sustitución completa, no una fusión.

Se recomienda exportar una copia de seguridad al menos una vez por semana durante el verano. Si llevas 7 días o más sin hacerlo (o no has exportado ninguna todavía), verás un aviso arriba de la pantalla "Hoy" — toca para ir directo a Ajustes.

## 8. Borrar datos

En **Ajustes → Zona de peligro** puedes borrar todos los datos del dispositivo (niños, asistencia, actividades, ausencias y fotos). Pide confirmación dos veces porque no se puede deshacer.

## 9. Preguntas frecuentes

**¿Por qué no aparece un niño/a en la lista de asistencia de hoy?**
Revisa su periodo de inscripción en la pestaña Niños: puede que ese día no esté dentro de su mes completo ni de sus semanas sueltas.

**¿Cuándo debo archivar a un niño/a en vez de eliminarlo?**
Prácticamente siempre que deje el grupo: archivar es reversible y conserva su historial y estadísticas. Elimínalo definitivamente solo si te has equivocado al crearlo o no quieres conservar ningún rastro suyo.

**¿Puedo usar la app en varios dispositivos a la vez?**
No en esta versión: los datos se guardan solo en el navegador del dispositivo donde se usa. Si varios monitores necesitan ver o editar los mismos datos, exporta e importa la copia de seguridad, o usa siempre el mismo dispositivo.

**La generación con IA da error.**
Comprueba que has guardado correctamente la clave de API en Ajustes y que el dispositivo tiene conexión a internet. El mensaje de error suele indicar la causa (clave inválida, sin conexión, límite de uso alcanzado, etc.).
