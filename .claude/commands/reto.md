---
description: Reto extra para quien va rápido (opcional)
---

La persona ha terminado el paso en el que estaba antes que el resto y quiere un **reto extra** mientras espera. No es un paso del curso: no lo menciones como obligatorio y no adelantes ningún `/paso-…`.

1. Ofrécele elegir con este formato y espera respuesta:

**Reto extra, elige uno:**
1. **Tu investigación real** — trae unos archivos de tu trabajo y te ayudo a entenderlos y ordenarlos.
2. **Matriz de literatura** — fichamos todos los PDFs de `papers/` y los comparamos en una tabla.
3. **Tu propio comando** — convertimos algo que le pides a menudo a la IA en un comando tuyo, como los `/paso` del curso.

---

## Reto 1 · Tu investigación real

1. Antes de nada, avísale: **nada de datos confidenciales ni personales** (historias clínicas, entrevistas identificables, datos cedidos con acuerdo de confidencialidad).
2. Pídele que cree la subcarpeta `mi-investigacion/` dentro de la carpeta del curso y copie ahí unos pocos archivos de su trabajo (un borrador, un script, un par de papers). Espera a que te diga que ya está.
3. Lee lo que haya y responde con:
   - **Lo que hay:** una tabla (Archivo | Qué es | Comentario breve).
   - **Cómo lo organizaría:** una propuesta de carpetas en forma de árbol, con una línea por carpeta. **Es solo una propuesta: no muevas, no renombres ni borres nada.**
   - **Tres cosas que podrías pedirme sobre este material:** tres ejemplos concretos entre comillas, basados en sus archivos reales.

## Reto 2 · Matriz de literatura

1. Mira los PDFs de `papers/`. Si hay menos de dos, dile que añada alguno más y vuelva a escribir `/reto`.
2. Léelos todos y crea `notas/matriz-literatura.md` con una tabla: una fila por paper y estas columnas: Referencia · Pregunta · Datos · Método · Hallazgo principal (con página) · Limitación.
3. Si un dato no aparece en el paper, escribe «no indicado». Nunca lo completes con lo que suele poner ese tipo de paper.
4. Responde con el enlace a la matriz, dos o tres frases sobre en qué se parecen y en qué se diferencian los papers, y termina con: **«Verifica tú: elige una celda de la columna "Hallazgo principal", abre el PDF por la página citada y comprueba que dice eso.»**

## Reto 3 · Tu propio comando

1. Explícale en dos frases que cada `/paso` es un archivo de texto en `.claude/commands/` con instrucciones guardadas, y que si pega el mismo prompt más de una vez merece la pena convertirlo en comando.
2. Pregúntale qué le pide a la IA a menudo, con opciones, y espera respuesta: 1 resumir un paper en cinco líneas · 2 revisar ortografía y puntuación sin cambiar el estilo · 3 pasar un párrafo a inglés académico · 4 comentar un do-file línea a línea · 5 otra (que la cuente).
3. Crea `.claude/commands/<nombre-corto>.md` (minúsculas, sin acentos ni espacios) con un encabezado `description:`, instrucciones concretas con el formato de salida, y `$ARGUMENTS` donde irá el texto que escriba detrás del comando (explícale qué es en una frase).
4. Responde con el enlace al archivo y: «Pruébalo escribiendo `/<nombre>` seguido de un texto. Si no te aparece al escribir `/`, abre una sesión nueva en la misma carpeta.»

---

Al terminar cualquier reto, recuérdale que cuando Alejandro dé el siguiente paso, lo siga con el resto.
