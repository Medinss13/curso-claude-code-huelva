---
description: Paso 11 · LaTeX desde Claude
---

**Dalo con los cuatro momentos de «Cómo das cada paso» del `CLAUDE.md`**: empieza con el titular `### Paso 11 · LaTeX desde Claude`, «Qué vamos a hacer» y «Para qué te sirve en tu investigación»; antes de cada archivo que crees o cambies, enséñale un trozo y avisa del permiso; antes de cada programa que ejecutes, di cuál y para qué; y al final explica «Lo que acaba de pasar» (qué hay ahora en su carpeta que antes no había) antes del formato de respuesta de abajo.

Estamos en el **paso 11 del curso: LaTeX desde Claude**. El objetivo es que la persona vea cómo la tabla, la figura y las cifras que ha producido Stata entran solas en el artículo, y cómo compilas el PDF por ella.

Antes de empezar, lee `articulo/CLAUDE.md`. Si no existen `articulo/resultados/tablas/tabla1.tex` y `articulo/resultados/numeros.tex`, dile que primero hay que hacer el `/paso-10` y no sigas.

1. Explícale en dos frases: el texto del artículo no lleva ningún número escrito a mano; la tabla y la figura se incluyen con `\input` e `\includegraphics`, y las cifras del texto son macros (como `\coefgenerico`) que ha escrito Stata.
2. Copia `recursos/plantilla-articulo.tex` a `articulo/texto/main.tex` y `recursos/referencias.bib` a `articulo/texto/referencias.bib`.
3. En `main.tex`:
   - Cambia `[NOMBRE]` por el nombre de la persona (está en la sección «Sobre mí y mi investigación» de `CLAUDE.md`; si está vacía, pregúntaselo).
   - Sustituye el comentario `% [RESULTADOS] …` por **un párrafo de resultados** de 4-6 frases que cite la Tabla y la Figura con `\ref` y use **solo las macros** de `numeros.tex` para las cifras (coeficientes, errores estándar, caídas en porcentaje, observaciones, R²). Habla de asociación, no de causalidad.
   - No toques nada más de la plantilla.
4. Compila **desde `articulo/texto/`**, con las rutas de `CLAUDE.md` si los programas no están en el PATH:
   `pdflatex -interaction=nonstopmode main.tex` → `bibtex main` → `pdflatex -interaction=nonstopmode main.tex` → `pdflatex -interaction=nonstopmode main.tex`.
   - Si hay un error, busca en `main.log` la primera línea que empiece por `!`, explícale en una frase qué pasa, corrígelo y vuelve a compilar (como mucho tres intentos).
   - En Windows, la primera compilación puede tardar porque MiKTeX descarga paquetes.
5. **Ponlo todo en una sola ventana.** Dile que en el explorador de VS Code abra `articulo/texto/main.tex` y que, con el `.tex` abierto, pulse el botón de vista previa de LaTeX Workshop (arriba a la derecha del editor, un icono de lupa sobre una hoja) o haga clic en `main.pdf`: el PDF se abre en una pestaña al lado. Explícale que esa pestaña se recarga sola cada vez que compiles.
6. Responde con este formato:

**Tu artículo está compilado:** [articulo/texto/main.pdf](articulo/texto/main.pdf). En VS Code tienes ahora el `.tex` y el PDF uno al lado del otro, y a mí en el panel.

**Lo que acaba de pasar:** dos frases. La idea: la tabla, la figura y cada cifra del párrafo de resultados vienen de Stata; en `main.tex` no hay ni un número tecleado.

**Compruébalo tú:** abre `main.tex`, busca el párrafo de resultados y fíjate en que donde el PDF pone una cifra, el `.tex` pone una macro.

Termina con: «Espera a que Alejandro dé el siguiente paso (`/paso-12`).»
