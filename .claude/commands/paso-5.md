---
description: Paso 5 · Lee un paper
---

Paso 5 del curso: **lee un paper**. Dalo con los cuatro momentos de «Cómo das cada paso» del `CLAUDE.md`.

**1. Antes de empezar**
- Qué vamos a hacer: vas a leer uno de sus PDFs y a preparar una ficha con los datos clave y la página de donde sale cada uno.
- Para qué le sirve: es la base de una revisión de literatura, y aprende por qué todo lo que extrae la IA hay que comprobarlo.

**2. Mientras lo haces**
- Di: «Voy a mirar qué PDFs hay en `papers/`».
  - **Si no hay ninguno**, dile que copie uno o dos PDFs de su tema a la carpeta `papers/` desde el explorador de archivos (si no tiene ninguno, un working paper de acceso abierto de NBER, SSRN o RePEc) y que vuelva a escribir `/paso-5`. No sigas.
  - **Si hay varios**, coge el primero por orden alfabético y dile cuál.
- Di: «Voy a leer el PDF entero. Puede tardar un poco si es largo». Léelo.
- **Antes de crear la ficha**, enséñale la tabla (Campo | Contenido), una o dos frases por campo:
  1. Referencia (autores, año, título, revista)
  2. Pregunta de investigación
  3. Datos (fuente, unidad de observación, muestra, periodo)
  4. Estrategia de identificación (qué variación usa: diferencias en diferencias, variables instrumentales, regresión discontinua, efectos fijos, modelo estructural…)
  5. Resultado principal: el coeficiente o la elasticidad clave como lo da el paper, con su error estándar si aparece, **y la tabla y la página**
  6. Limitación principal
  7. ¿Encaja con mi investigación? (según la sección «Sobre mí y mi investigación» de `CLAUDE.md`; si está vacía, «pendiente: rellena el /paso-4»)
  Regla estricta: si un dato no aparece en el paper, «no indicado». Nunca lo completes con lo que «suele» poner ese tipo de paper.
- Di: «Ahora la guardo en `notas/ficha-<apellido>-<año>.md`. Como estamos en omitir permisos, no te saldrá aviso». Créala.

**3. Lo que acaba de pasar**
- Has leído el PDF y has creado la ficha (enlace al archivo, escrito como `[notas/ficha-….md](notas/ficha-….md)`).
- El PDF no se ha tocado.
- Señala si algún campo ha quedado como «no indicado» y por qué.

**4. Lo que te llevas y compruébalo tú**
- Lo que te llevas: la IA extrae, tú verificas. Por eso cada dato lleva su página.
- Compruébalo tú: que abra el PDF por la tabla y la página del resultado principal y compruebe que la cifra está ahí y dice lo que dice la ficha.

Termina con: «Espera a que Alejandro dé el siguiente paso (`/paso-6`).»
