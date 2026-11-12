---
description: Paso 8 · Comprueba tus programas (Stata y LaTeX)
---

**Dalo con los cuatro momentos de «Cómo das cada paso» del `CLAUDE.md`**: empieza con el titular `### Paso 8 · Comprueba tus programas`, «Qué vamos a hacer» y «Para qué te sirve en tu investigación»; antes de cada archivo que crees o cambies, enséñale un trozo y avisa del permiso; antes de cada programa que ejecutes, di cuál y para qué; y al final explica «Lo que acaba de pasar» (qué hay ahora en su carpeta que antes no había) antes del formato de respuesta de abajo.

Estamos en el **paso 8 del curso: comprueba tus programas**. Empieza el viernes: hoy la persona va a escribir un artículo mientras tú ejecutas Stata y compilas LaTeX. Antes, hay que asegurarse de que los dos funcionan en su ordenador.

0. **Hoy se trabaja en VS Code.** Explícale en tres frases cómo es la ventana: a la izquierda, el explorador con las carpetas del curso; en el centro, los archivos abiertos (luego el do-file y el `.tex`, con el PDF al lado); y tu panel, donde escribe los pasos. Es la misma carpeta y el mismo `CLAUDE.md` que ayer, así que ya sabes quién es. Recuérdale que en el selector de modo de tu panel elija **omitir permisos**, como ayer desde el paso 5.
1. Lee la sección «Programas de este ordenador» de `CLAUDE.md`.
   - **Si está rellena y no falta nada**: haz solo una comprobación rápida. Ejecuta otra vez `notas/prueba-stata.do` en batch (con la ruta apuntada) y compila `notas/prueba-latex.tex`. Si los dos funcionan, pasa al punto 3.
   - **Si está vacía o falta algo** (también VS Code o sus extensiones): lee `.claude/commands/paso-7.md` y sigue sus instrucciones desde el punto 2, con la misma calma: explica cada cosa antes de hacerla y espera a que la persona confirme cada instalación.
2. Si algo no se puede resolver en 15 minutos (por ejemplo, no tiene licencia de Stata o la instalación de LaTeX falla), díselo con calma: puede seguir el resto del día en la pantalla de Alejandro y terminarlo en casa con `/paso-7`.
3. Responde con este formato:

**Listo para escribir el artículo:**

| Programa | Estado |
|---|---|
| Stata | … |
| esttab | … |
| LaTeX (pdflatex y bibtex) | … |
| VS Code y extensiones | … |

**Lo que haremos hoy:** tres frases. Montamos un proyecto de artículo replicable; yo ejecuto Stata y Stata escribe la tabla, la figura y hasta las cifras del texto; tú no tecleas ni un número, y cuando cambie la regresión, cambiará todo el artículo solo.

Termina con: «Espera a que Alejandro dé el siguiente paso (`/paso-9`).»
