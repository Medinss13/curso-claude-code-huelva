---
description: Paso 10 · Stata desde Claude
---

**Dalo con los cuatro momentos de «Cómo das cada paso» del `CLAUDE.md`**: empieza con el titular `### Paso 10 · Stata desde Claude`, «Qué vamos a hacer» y «Para qué te sirve en tu investigación»; antes de cada archivo que crees o cambies, enséñale un trozo y avisa del permiso; antes de cada programa que ejecutes, di cuál y para qué; y al final explica «Lo que acaba de pasar» (qué hay ahora en su carpeta que antes no había) antes del formato de respuesta de abajo.

Estamos en el **paso 10 del curso: Stata desde Claude**. El objetivo es que la persona vea cómo escribes los do-files, ejecutas Stata, lees el log y dejas listos la tabla, la figura y las cifras del texto, sin teclear ningún número.

Antes de empezar, lee `articulo/CLAUDE.md` y la sección «Programas de este ordenador» de `CLAUDE.md`. Si `articulo/` no existe, dile que primero hay que hacer el `/paso-9` y no sigas.

1. Explícale en dos frases lo que vas a hacer: escribir tres do-files (limpieza, análisis y uno que los ejecuta todos), lanzarlos en Stata y comprobar el resultado.
2. Escribe en `articulo/codigo/`, con comentarios en español:
   - **`01_limpieza.do`**: importa `../datos/brutos/medicamentos-ejemplo.csv`, pone etiquetas a las variables (en español), crea `log_precio = ln(precio_envase)` y una variable que distinga los medicamentos que reciben genérico en algún momento de los que no, y guarda `../datos/limpios/medicamentos.dta`.
   - **`02_analisis.do`**:
     - Abre `../datos/limpios/medicamentos.dta`, declara el panel (`xtset id anio`) y estima `xtreg log_precio generico n_laboratorios i.anio, fe`.
     - Exporta la tabla con `esttab` a `../resultados/tablas/tabla1.tex`, **solo el `tabular`** (sin entorno `table`, que ya lo pone el texto): opción `booktabs`, etiquetas de las variables, errores estándar entre paréntesis, estrellas `* 0.10 ** 0.05 *** 0.01`, solo los coeficientes de `generico` y `n_laboratorios`, y al pie el número de observaciones, el número de medicamentos y el R² *within*, con una fila que diga que hay efectos fijos de medicamento y de año.
     - Hace la figura: el precio medio en logaritmos por año, con una línea para los medicamentos que reciben genérico y otra para los que no, títulos en español, y la exporta con `graph export ../resultados/figuras/figura1.pdf, replace`.
     - Escribe con `file write` el archivo `../resultados/numeros.tex` con **exactamente** estas macros de LaTeX (punto decimal):
       - `\nobs` (observaciones) y `\nmedicamentos` (número de medicamentos), sin decimales.
       - `\coefgenerico` y `\segenerico`: coeficiente y error estándar de `generico`, con 3 decimales.
       - `\coeflabs` y `\selabs`: lo mismo para `n_laboratorios`.
       - `\caidagenerico` y `\caidalabs`: la caída del precio en porcentaje, calculada como el valor absoluto de `100*(exp(b)-1)`, con 1 decimal.
       - `\rdos`: el R² *within*, con 2 decimales.
   - **`00_master.do`**: ejecuta `01_limpieza.do` y `02_analisis.do`, en ese orden.
3. Ejecuta `00_master.do` en batch **desde `articulo/codigo/`**, con la ruta y la forma de lanzarlo apuntadas en `CLAUDE.md`. Espera a que termine y lee `00_master.log`.
   - Si hay un error, léelo, explícale en una frase qué ha fallado, corrígelo y vuelve a ejecutar (como mucho tres intentos).
   - Si `esttab` no está instalado, pregúntale antes de instalarlo.
4. Comprueba que existen `tabla1.tex`, `figura1.pdf` y `numeros.tex`, y que los números de `numeros.tex` coinciden con los del log.
5. Responde con este formato:

**Stata ha terminado.** Enlaces a los tres do-files y a `tabla1.tex`, `figura1.pdf` y `numeros.tex`.

**El resultado, en una frase:** el coeficiente de la entrada de genérico tal como sale en el log y lo que significa en porcentaje. Recuerda que los datos son ficticios.

**Verifica tú:** abre [articulo/codigo/00_master.log](articulo/codigo/00_master.log), busca la fila de `generico` y comprueba que el coeficiente es el mismo que el de `tabla1.tex` y el de `\coefgenerico` en `numeros.tex`.

Termina con: «Espera a que Alejandro dé el siguiente paso (`/paso-11`).»
