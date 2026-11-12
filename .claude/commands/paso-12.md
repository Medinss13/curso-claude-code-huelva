---
description: Paso 12 · El ciclo completo
---

**Dalo con los cuatro momentos de «Cómo das cada paso» del `CLAUDE.md`**: empieza con el titular `### Paso 12 · El ciclo completo`, «Qué vamos a hacer» y «Para qué te sirve en tu investigación»; antes de cada archivo que crees o cambies, enséñale un trozo y avisa del permiso; antes de cada programa que ejecutes, di cuál y para qué; y al final explica «Lo que acaba de pasar» (qué hay ahora en su carpeta que antes no había) antes del formato de respuesta de abajo.

Estamos en el **paso 12 del curso: el ciclo completo**. Es el momento clave del día: la persona pide un cambio como lo pediría un evaluador, y ve cómo cambian solos la tabla, el texto y el PDF.

Antes de empezar, lee `articulo/CLAUDE.md`. Si no existe `articulo/texto/main.pdf`, dile que primero hay que hacer el `/paso-11` y no sigas.

1. Explícale en dos frases: es lo que pasa cuando llega el informe de un evaluador; con el proyecto montado así, un cambio de especificación es una frase, y todo el artículo se actualiza sin tocar ni un número a mano.
2. Pregúntale qué cambio quiere, con estas opciones, y espera respuesta:
   1. **Robustez** ⭐: añadir dos columnas a la tabla, una con errores estándar agrupados por medicamento y otra sin el medicamento atípico (Cardilomab, mucho más caro que el resto).
   2. **Otro cambio que se le ocurra**, explicado en una frase (otra variable, otra muestra, otro modelo).
3. Haz el cambio **solo en `02_analisis.do`**:
   - Añade los modelos nuevos a la misma tabla (`tabla1.tex` con varias columnas, numeradas) y una fila que diga cómo se calculan los errores estándar en cada columna.
   - Añade a `numeros.tex` las macros nuevas que hagan falta para citar los resultados en el texto (por ejemplo, `\coefgenericoclus`, `\segenericoclus`, `\coefgenericosin`, `\caidagenericosin`, `\nobssin`), sin cambiar el nombre de las que ya existen.
   - Si se agrupan los errores con solo 10 medicamentos, avísale en una frase de que con tan pocos grupos los errores agrupados no son fiables; es justo lo que diría un evaluador.
4. Ejecuta `00_master.do` desde `articulo/codigo/` y comprueba el log.
5. En `main.tex`, añade al final de la sección de resultados **un párrafo de robustez** de 2-4 frases que use solo las macros nuevas. No toques el resto.
6. Vuelve a compilar desde `articulo/texto/` (`pdflatex`, `bibtex`, `pdflatex`, `pdflatex`). Dile que mire la pestaña del PDF en VS Code: se recarga sola y verá aparecer las columnas nuevas y el párrafo de robustez.
7. Responde con este formato:

**Artículo actualizado:** [articulo/texto/main.pdf](articulo/texto/main.pdf).

**Qué has pedido y qué ha cambiado:** tres viñetas: el cambio en el do-file, la tabla (columnas nuevas) y el párrafo nuevo.

**Lo que acaba de pasar:** una frase. La idea: has cambiado una línea de código y el artículo entero (tabla, cifras y texto) se ha puesto al día solo, sin un número tecleado.

**Verifica tú:** elige una cifra del párrafo de robustez del PDF y búscala en `codigo/00_master.log`. Tiene que ser la misma.

Termina con: «Espera a que Alejandro dé el siguiente paso (`/paso-13`).»
