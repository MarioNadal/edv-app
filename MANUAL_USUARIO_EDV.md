# Manual de usuario — EDV (v1.0.0)

## 1. Primeros pasos

1. Abre `index.html` en el navegador del móvil o del ordenador que vayas a usar cada día.
2. Ve a **Ajustes** y revisa el nombre del programa, el grupo (por defecto "2014") y el año. Sube tu logo si quieres personalizarlo.
3. Si quieres usar la generación de observaciones con IA, ve a **Ajustes → Generación de observaciones con IA** y pega tu clave de API de Anthropic. Lee antes el aviso de seguridad que aparece justo encima del campo.
4. Añade a los niños y niñas del grupo en la pestaña **Niños**.

La app funciona offline salvo el botón "Generar observación con IA", que necesita conexión.

## 2. Añadir niños y niñas

En **Niños**, pulsa el botón `+`. Para cada uno indica:

- Nombre.
- Periodo de inscripción:
  - **Julio completo** / **Agosto completo**: actívalo si viene todos los días lectivos de ese mes.
  - **Semanas sueltas**: si no viene el mes entero, marca solo las semanas concretas en las que sí participa. No hace falta combinar esto con los interruptores de mes completo — usa una cosa u otra según el caso de cada niño/a.
- Foto (opcional).

Puedes editar o eliminar a un niño/a en cualquier momento tocando su fila. Eliminarlo no borra los registros de asistencia ya guardados en días anteriores.

## 3. El día a día (pestaña "Hoy")

Al abrir la app verás el día de hoy. Usa las flechas `‹` `›` para moverte a otro día (por ejemplo, para completar un día que se te olvidó).

**Asistencia:** aparecen solo los niños y niñas inscritos ese día concreto. Para cada uno, marca `P` (presente), `A` (ausente) o `J` (justificado). Tocar de nuevo el mismo botón lo deja sin marcar.

**Valoración colectiva:** puntúa el día con estrellas (1 a 5) y añade, si quieres, un comentario general sobre cómo ha ido el grupo.

**Actividades:**
1. Pulsa "+ Añadir actividad" y ponle un nombre (por ejemplo, "Datchball", "Piscina", "Taller de manualidades").
2. Escribe unas notas rápidas: qué se ha hecho, cómo ha ido, y cualquier incidencia relevante (un retraso en una recogida, un pequeño conflicto, etc.). Cuanto más claras sean las notas, mejor será la observación generada.
3. Pulsa "✨ Generar observación con IA". En unos segundos aparecerá un párrafo redactado listo para compartir con las familias o guardar como registro. Puedes editar las notas y volver a generar cuantas veces quieras — cada generación sustituye a la anterior.
4. Añade fotos de la actividad con el botón de la cámara. Toca cualquier miniatura para verla a tamaño completo. Con "💾 Guardar en galería" se abre la hoja de compartir del móvil: elige la opción "Guardar imagen" o "Guardar en Fotos" para que quede en la galería del dispositivo (por seguridad, ninguna web puede guardar ahí directamente sin ese paso). También puedes eliminar la foto desde el mismo visor.

La IA nunca inventa incidencias que no hayas escrito en las notas: solo redacta a partir de lo que le indiques.

## 4. Historial

En **Historial** puedes ver todos los días registrados, con filtro por Julio/Agosto. Tocar un día te lleva directamente a su vista de "Hoy" para revisarlo o completarlo.

## 5. Estadísticas y exportación

En **Estadísticas** verás el porcentaje de asistencia de cada niño/a (calculado solo sobre los días en los que estaba inscrito). Desde ahí puedes:

- **Exportar PDF**: informe resumen con días, presentes, ausentes, justificados y % de asistencia por niño/a.
- **Exportar Excel**: cuadrícula completa de asistencia día a día, lista para revisar o compartir.

## 6. Copia de seguridad

En **Ajustes → Copia de seguridad**:

- **Exportar copia de seguridad**: descarga un archivo `.json` con niños, asistencia y actividades (las fotos no se incluyen en este archivo, ya que se guardan aparte en el dispositivo).
- **Restaurar desde copia de seguridad**: sustituye los datos actuales por los del archivo elegido. Úsalo con cuidado — es una sustitución completa, no una fusión.

Se recomienda exportar una copia de seguridad al menos una vez por semana durante el verano.

## 7. Borrar datos

En **Ajustes → Zona de peligro** puedes borrar todos los datos del dispositivo (niños, asistencia, actividades y fotos). Pide confirmación dos veces porque no se puede deshacer.

## 8. Preguntas frecuentes

**¿Por qué no aparece un niño/a en la lista de asistencia de hoy?**
Revisa su periodo de inscripción en la pestaña Niños: puede que ese día no esté dentro de su mes completo ni de sus semanas sueltas.

**¿Puedo usar la app en varios dispositivos a la vez?**
No en esta versión: los datos se guardan solo en el navegador del dispositivo donde se usa. Si varios monitores necesitan ver o editar los mismos datos, exporta e importa la copia de seguridad, o usa siempre el mismo dispositivo.

**La generación con IA da error.**
Comprueba que has guardado correctamente la clave de API en Ajustes y que el dispositivo tiene conexión a internet. El mensaje de error suele indicar la causa (clave inválida, sin conexión, límite de uso alcanzado, etc.).
