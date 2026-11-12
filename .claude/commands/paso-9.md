---
description: Paso 9 · El proyecto del artículo
---

**Dalo con los cuatro momentos de «Cómo das cada paso» del `CLAUDE.md`**: empieza con el titular `### Paso 9 · El proyecto del artículo`, «Qué vamos a hacer» y «Para qué te sirve en tu investigación»; antes de cada archivo que crees o cambies, enséñale un trozo y avisa del permiso; antes de cada programa que ejecutes, di cuál y para qué; y al final explica «Lo que acaba de pasar» (qué hay ahora en su carpeta que antes no había) antes del formato de respuesta de abajo.

Estamos en el **paso 9 del curso: el proyecto del artículo**. El objetivo es que la persona vea cómo se organiza un artículo de economía replicable y que deje escritas las reglas del proyecto, para que tú las cumplas sin que te lo recuerde.

1. Explícale en tres frases como máximo:
   - Que un artículo replicable separa cuatro cosas: los datos en bruto (que no se tocan nunca), el código que lo calcula todo, los resultados que genera el código y el texto que solo los incluye.
   - Que así, si un evaluador pide otra especificación, se cambia una línea de código y se vuelve a generar todo.
   - Que vas a crear esa estructura y un `CLAUDE.md` propio del artículo con sus reglas.
2. Crea esta estructura dentro de la carpeta del curso:
   ```
   articulo/
   ├── CLAUDE.md
   ├── datos/
   │   ├── brutos/      ← copia aquí datos/medicamentos-ejemplo.csv
   │   └── limpios/
   ├── codigo/
   ├── resultados/
   │   ├── tablas/
   │   └── figuras/
   └── texto/
   ```
   Copia `datos/medicamentos-ejemplo.csv` a `articulo/datos/brutos/` (sin modificarlo).
3. Escribe `articulo/CLAUDE.md` con:
   - **Qué es**: un ejercicio del curso sobre la entrada de genéricos y el precio de los medicamentos de marca, con un panel ficticio de 10 medicamentos (2019-2023).
   - **Mapa**: una línea por carpeta.
   - **Reglas del proyecto** (numeradas):
     1. `datos/brutos/` no se modifica nunca; toda limpieza va en el código y guarda en `datos/limpios/`.
     2. Todo se ejecuta con `codigo/00_master.do`, lanzado en batch desde la carpeta `codigo/` (la ruta de Stata está en el `CLAUDE.md` del curso).
     3. **Ningún número de un resultado se teclea a mano**: las tablas las escribe `esttab` en `resultados/tablas/`, las figuras van a `resultados/figuras/` y las cifras que se citan en el texto las escribe Stata como macros de LaTeX en `resultados/numeros.tex`.
     4. El texto está en `texto/main.tex` y se compila desde `texto/` con `pdflatex`, `bibtex`, `pdflatex` y `pdflatex` (sin `latexmk`).
     5. Solo se citan referencias que estén en `texto/referencias.bib`. Nunca se inventa una.
     6. Si cambia la especificación: se edita el do-file, se ejecuta el master y se vuelve a compilar. Nada se corrige a mano en las tablas ni en el PDF.
     7. Nombres de archivo en minúsculas, sin acentos ni espacios.
4. Responde con este formato:

**Proyecto creado:** el árbol de carpetas en un bloque de código y el enlace a [articulo/CLAUDE.md](articulo/CLAUDE.md).

**Las tres reglas que más importan:** tres viñetas (datos brutos intocables · todo sale del master · ningún número tecleado).

**Por qué así:** una frase. La idea: dentro de un año, tú (o el editor de la revista) podrás reproducir cada número del artículo con un solo clic.

Termina con: «Espera a que Alejandro dé el siguiente paso (`/paso-10`).»
