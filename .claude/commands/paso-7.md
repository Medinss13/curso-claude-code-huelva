---
description: Paso 7 · Prepara el viernes - Stata, LaTeX y VS Code
---

Estamos en el **paso 7 del curso: prepara el viernes**. Lo hacéis todos juntos al final del jueves, con Alejandro. El viernes se trabaja en **VS Code**, y allí ejecutarás Stata y compilarás LaTeX por la persona mientras escribe un artículo. Ahora compruebas que Stata, LaTeX y VS Code están en su ordenador, la ayudas a instalar lo que falte y apuntas las rutas para no tener que buscarlas otra vez. **Ve paso a paso y explica cada cosa antes de hacerla**: es la parte en la que más gente se pierde.

Dalo con los cuatro momentos de «Cómo das cada paso» del `CLAUDE.md`: antes de cada búsqueda, prueba o instalación, di en una línea qué vas a hacer y por qué.

1. **Antes de empezar.** Titular `### Paso 7 · Prepara el viernes` y:
   - Qué vamos a hacer: buscar Stata y LaTeX en su ordenador, hacer una prueba pequeña con cada uno, instalar VS Code con sus extensiones y apuntarlo todo en `CLAUDE.md`.
   - Para qué le sirve: el viernes, en VS Code, verá en una sola ventana el do-file, el artículo en PDF y a ti trabajando; Claude no sustituye a Stata ni a LaTeX, los lanza por ella.
   - Si no da tiempo, puede terminarlo en casa escribiendo otra vez `/paso-7`.
   - **Recuérdale que vuelva al modo manual** (selector de modo, junto al cuadro donde escribe): vas a instalar programas y tiene que ver y aceptar cada aviso.

2. **Averigua el sistema** (Windows o Mac) con un comando sencillo y díselo en una línea.

3. **Stata**
   - Búscalo en las rutas habituales:
     - Windows: `C:\Program Files\Stata*`, `C:\Program Files\StataNow*` y `C:\Program Files (x86)\Stata*`. El ejecutable se llama `StataMP-64.exe`, `StataSE-64.exe`, `StataBE-64.exe` o `Stata-64.exe`.
     - Mac: `/Applications/Stata*`. El ejecutable está dentro de la app, en `Contents/MacOS/` (`stata-mp`, `stata-se`, `stata-be` o `stata`).
   - **Si no lo encuentras**, pregúntale si tiene Stata y dónde. Si no tiene, díselo con calma: el viernes podrá seguir en la pantalla de Alejandro. Pasa al punto 4.
   - **Prueba**: crea `notas/prueba-stata.do` con `display "Stata funciona"` y `which esttab`. Ejecútalo en modo batch **desde la carpeta `notas/`**, para que el `.log` se guarde ahí:
     - Windows: `"<ruta al .exe>" /e do prueba-stata.do`. Si lo lanzas desde PowerShell, usa `Start-Process ... -Wait` para esperar a que termine; si no, el log aún no existirá cuando lo leas.
     - Mac: `"<ruta al ejecutable>" -b do prueba-stata.do`.
   - Lee `notas/prueba-stata.log`. Si sale «Stata funciona», Stata va bien.
   - **`esttab`** (del paquete `estout`) es lo que convierte una regresión en una tabla de LaTeX. Si el log dice que no está, **pregúntale si lo instalas** y, si dice que sí, ejecuta en batch un do-file con `ssc install estout, replace` (hace falta internet).

4. **LaTeX**
   - Comprueba si existen `pdflatex` y `bibtex` (`pdflatex --version`). Si no están en el PATH, mira también las rutas habituales:
     - Windows (MiKTeX): `%LOCALAPPDATA%\Programs\MiKTeX\miktex\bin\x64\` y `C:\Program Files\MiKTeX\miktex\bin\x64\`.
     - Mac (MacTeX): `/Library/TeX/texbin/`.
   - **Si no está instalado**, guíale según su sistema, **de un paso en un paso** y esperando a que te diga que ya lo ha hecho:
     - **Windows**: ofrécete a instalar MiKTeX con `winget install --id MiKTeX.MiKTeX -e`. **Pregunta antes.** Si Windows pide permiso de administrador, que acepte. Si `winget` no funciona, que lo descargue de miktex.org/download con las opciones por defecto. Después, que abra una vez **MiKTeX Console** y, en **Settings**, marque que instale los paquetes que falten **automáticamente** («Always install missing packages on-the-fly»). Por último, que abra una **sesión nueva** en la carpeta del curso y vuelva a escribir `/paso-7`.
     - **Mac**: que descargue **MacTeX** de tug.org/mactex (unos 5 GB: mejor con buena conexión) y lo instale con las opciones por defecto; el instalador le pedirá su contraseña del Mac, que escribe ella, no tú. Después, sesión nueva y `/paso-7` otra vez.
   - **Prueba**: crea `notas/prueba-latex.tex`, un documento mínimo que use `booktabs` y `graphicx` y diga «LaTeX funciona», y compílalo desde `notas/` con `pdflatex -interaction=nonstopmode prueba-latex.tex`. En Windows, la primera vez MiKTeX puede tardar porque descarga paquetes. Comprueba que se ha creado `notas/prueba-latex.pdf`.
   - No uses `latexmk`: en Windows necesita Perl, que casi nadie tiene. El viernes compilaremos con `pdflatex` y `bibtex` directamente.

5. **VS Code** (Visual Studio Code; no confundir con «Visual Studio», que es otro programa)
   - Comprueba si está instalado (`code --version`; en Windows mira también `%LOCALAPPDATA%\Programs\Microsoft VS Code\`; en Mac, `/Applications/Visual Studio Code.app`).
   - **Si no está**, guíale **de un paso en un paso**:
     - **Windows**: ofrécete a instalarlo con `winget install --id Microsoft.VisualStudioCode -e` (**pregunta antes**), o que lo descargue de code.visualstudio.com con las opciones por defecto y marque «Agregar a PATH».
     - **Mac**: que lo descargue de code.visualstudio.com, lo descomprima y arrastre la app a *Aplicaciones*.
   - **Extensiones**: la carpeta del curso ya trae `.vscode/extensions.json` con las dos que hacen falta. Explícale para qué sirve cada una: **Claude Code** (Anthropic: tú, dentro de VS Code) y **LaTeX Workshop** (el PDF en una pestaña, al lado del `.tex`). Ofrécete a instalarlas con `code --install-extension anthropic.claude-code` y `code --install-extension james-yu.latex-workshop` (**pregunta antes**). Si `code` no funciona, que abra la carpeta del curso en VS Code (*Archivo → Abrir carpeta*) y acepte el aviso «¿Instalar las extensiones recomendadas?».
   - Explícale que `.vscode/settings.json` ya deja LaTeX Workshop configurado para compilar con `pdflatex` y `bibtex`, sin `latexmk`.
   - **Prueba**: que abra la carpeta del curso en VS Code, pulse el icono de Claude (barra lateral o arriba a la derecha), inicie sesión con su cuenta de Claude y escriba «hola». Si le da la bienvenida al curso, está listo.

6. **Apúntalo en `CLAUDE.md`**: sustituye solo la línea «(vacío: se rellena en el `/paso-7` o en el `/paso-8`)» de la sección «Programas de este ordenador» por viñetas con: sistema · Stata (ruta completa del ejecutable, edición y cómo se lanza en batch) · `esttab` instalado sí/no · `pdflatex` y `bibtex` (ruta o «en el PATH») · VS Code y sus dos extensiones · fecha de la prueba. Si algo falta, escribe «falta» y qué hay que hacer. **No toques nada más del archivo.**

7. **Lo que acaba de pasar** (viñetas: qué has buscado, qué pruebas has hecho en `notas/`, qué has instalado si lo has hecho y qué has escrito en `CLAUDE.md`) y después esta tabla:

**Tu ordenador para el viernes:**

| Programa | Estado | Qué falta |
|---|---|---|
| Stata | … | … |
| esttab | … | … |
| LaTeX (pdflatex y bibtex) | … | … |
| VS Code y extensiones | … | … |

**Lo he apuntado en `CLAUDE.md`**, así el viernes no hay que buscar nada.

**Lo que te llevas:** Claude puede usar los programas que ya tienes; tú sigues decidiendo. **Compruébalo tú:** que abra `notas/prueba-latex.pdf` y vea la frase «LaTeX funciona», y que el «hola» en VS Code le dé la bienvenida.

Si todo está en verde: «Listo para el viernes.» Si falta algo: una frase con lo que tiene que hacer en casa y «Cuando lo tengas, vuelve a escribir `/paso-7` y lo comprobamos».

Termina con: «Espera a que Alejandro dé el siguiente paso.»
