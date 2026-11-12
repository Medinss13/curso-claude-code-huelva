---
description: Ayuda · Estoy atascado instalando algo
argument-hint: describe el problema, por ejemplo «no me encuentra Stata»
---

La persona está **atascada con una instalación o con algo que no funciona** (Claude Code, Git, VS Code y sus extensiones, Stata, LaTeX…) y Alejandro no puede atenderla ahora. Esto es lo que te ha contado:

$ARGUMENTS

Tu trabajo es resolverlo con calma, **de una cosa en una**, explicando cada paso.

1. **Si no ha escrito nada** detrás del comando, pregúntale qué le pasa y espera respuesta: qué estaba haciendo, qué esperaba que pasara y **el texto exacto del error** (que lo copie y lo pegue, o que te pase una captura).
2. **Averigua el sistema** (Windows o Mac) y, si hace falta, comprueba lo que ya está instalado (`git --version`, `code --version`, `pdflatex --version`, rutas de Stata…). Antes de cada comprobación, di en una línea qué vas a mirar y por qué. Si la sección «Programas de este ordenador» de `CLAUDE.md` está rellena, léela primero.
3. **Di qué crees que pasa** en una o dos frases, en lenguaje sencillo, y **propón un solo arreglo**. Antes de instalar o cambiar nada, **pídele permiso**. Después, comprueba si ha funcionado.
4. Causas frecuentes en este curso:
   - **Windows pide Git**: falta Git for Windows → `winget install --id Git.Git -e` o git-scm.com, y después cerrar y volver a abrir la aplicación o VS Code.
   - **Acaba de instalar algo y «no lo encuentra»**: el programa no está en el PATH de esta sesión → abrir una sesión nueva (o reiniciar VS Code). En Windows, si sigue sin aparecer, busca el ejecutable en su ruta habitual y úsalo con la ruta completa.
   - **No tiene permisos de administrador** (ordenador de la universidad): instalar en modo usuario cuando se pueda (MiKTeX y VS Code lo permiten) o dejarlo para casa.
   - **Claude Code dice que su plan no lo incluye**: hace falta Claude Pro o superior.
   - **No sale la bienvenida al curso**: no ha abierto la carpeta `curso-claude-code-huelva` entera, sino otra.
   - **MiKTeX no compila por un paquete**: activar en *MiKTeX Console → Settings* que instale los paquetes que falten automáticamente.
   - **Mac pide una contraseña**: la escribe ella en la ventana del sistema, nunca en el chat.
   - **`code` no funciona en el terminal**: instalar las extensiones desde VS Code (`Ctrl+Shift+X`) o aceptar el aviso de «extensiones recomendadas» al abrir la carpeta.
   - **Stata no está o no tiene licencia**: no se puede arreglar ahora; que siga en la pantalla de Alejandro.
5. **No borres nada**, no desinstales programas y no toques archivos fuera de la carpeta del curso, salvo instalar lo que te haya autorizado.
6. **Si tras tres intentos no se resuelve**, para. Escríbele un resumen de cuatro líneas para que se lo enseñe a Alejandro en la pausa: sistema, qué intentaba hacer, el error exacto y lo que ya habéis probado. Y dile que puede seguir el curso en la pantalla de Alejandro mientras tanto.

Termina con: «Cuando esté resuelto, vuelve al paso en el que estabas».
