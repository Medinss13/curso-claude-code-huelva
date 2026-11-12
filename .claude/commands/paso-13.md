---
description: Paso 13 · Tu tribunal de agentes
---

**Dalo con los cuatro momentos de «Cómo das cada paso» del `CLAUDE.md`**: empieza con el titular `### Paso 13 · Tu tribunal de agentes`, «Qué vamos a hacer» y «Para qué te sirve en tu investigación»; antes de cada archivo que crees o cambies, enséñale un trozo y avisa del permiso; antes de cada programa que ejecutes, di cuál y para qué; y al final explica «Lo que acaba de pasar» (qué hay ahora en su carpeta que antes no había) antes del formato de respuesta de abajo.

Estamos en el **paso 13 del curso: tu tribunal de agentes**. El objetivo es que la persona vea a tres revisores especializados leer un borrador a la vez y juntar sus críticas en un informe, y que compruebe qué han encontrado.

1. Explícale en tres frases como máximo:
   - En `.claude/agents/` hay tres revisores ya definidos: **metodología**, **citas** y **redacción**. Cada uno es un archivo de texto con su papel y sus reglas (puede abrirlos y cambiarlos).
   - Solo pueden **leer**: ninguno puede modificar el borrador.
   - Vas a lanzar los tres a la vez sobre el mismo texto y después juntarás lo que digan. Puede verlos trabajar en el menú **⋮** de la barra de título → **Background tasks**.
2. Pregúntale qué revisar y espera respuesta:
   1. **El borrador de ejemplo** (`borrador/borrador-genericos.md`) ⭐: tiene errores escondidos a propósito.
   2. **El artículo que acabas de compilar** (`articulo/texto/main.tex`, con `articulo/resultados/` para comprobar las cifras).
   3. **Un borrador tuyo**: que lo copie a la carpeta `borrador/`. Antes, avísale: **nada confidencial ni sin permiso de sus coautores**.
3. Lanza **los tres revisores a la vez** (en un único mensaje, usando tu herramienta de agentes con los agentes `revisor-metodologia`, `revisor-citas` y `revisor-redaccion`), dándoles a cada uno la ruta del texto (y, en la opción 2, también la de `articulo/resultados/` y `articulo/codigo/00_master.log`).
   **No leas tú el texto antes de lanzarlos ni les des pistas sobre posibles errores**: que cada revisor trabaje con su propio criterio.
4. Cuando terminen, crea `notas/informe-tribunal.md`:
   - **Resumen**: los tres problemas más graves, en tres viñetas.
   - Una sección por revisor con sus hallazgos (dónde, qué pasa, gravedad, cómo arreglarlo).
   - Si dos revisores señalan lo mismo, júntalo y dilo («lo señalan metodología y redacción»).
   - **No modifiques el texto revisado.**
5. Responde con este formato:

**Informe del tribunal:** [notas/informe-tribunal.md](notas/informe-tribunal.md).

**Los tres problemas más graves:** las tres viñetas del resumen.

**Ahora te toca a ti:** abre el texto y comprueba cada uno de esos tres problemas. ¿Están de verdad? ¿Hay alguno que el tribunal se haya inventado? Si has usado el borrador de ejemplo, Alejandro os dirá cuántos errores tenía escondidos: compara con todo el informe, no solo con el resumen.

**La idea:** el tribunal te ahorra la primera lectura. La última siempre es tuya.

Termina con: «Hasta aquí los pasos del curso. Gracias por llegar hasta el final.»
