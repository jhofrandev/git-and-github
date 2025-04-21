# Visualización del Historial de Confirmaciones en Git

La visualización del historial de confirmaciones (commits) en Git es una de las tareas fundamentales al trabajar con este sistema de control de versiones. Permite entender cómo ha evolucionado un proyecto, quién ha contribuido, qué cambios se han realizado y cuándo. Git ofrece diversas herramientas y opciones para explorar este historial.

## El Comando Principal: `git log`

El comando más básico y esencial para ver el historial de confirmaciones es `git log`. Por defecto, muestra una lista de las confirmaciones realizadas en el repositorio, desde la más reciente hasta la más antigua.

Cada entrada en el log típicamente incluye:

- **Hash de la confirmación:** Un identificador único (SHA-1) para la confirmación.
- **Autor:** Quién realizó la confirmación (nombre y correo electrónico).
- **Fecha:** Cuándo se realizó la confirmación.
- **Mensaje de la confirmación:** La descripción que se proporcionó al hacer el commit.

**Ejemplo de salida básica:**

commit a1b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f8a9b0 (HEAD -> main, origin/main)
Author: Nombre Apellido <tu@email.com>
Date: Mon Apr 21 10:30:00 2025 -0500

commit f0e9d8c7b6a5f4e3d2c1b0a9f8e7d6c5b4a3b2a1
Author: Otro Nombre <otro@email.com>
Date: Sun Apr 20 15:00:00 2025 -0500

## Opciones Comunes para Personalizar `git log`

`git log` es muy potente y se puede personalizar con numerosas opciones para adaptar la salida a tus necesidades:

- **`--oneline`**: Muestra cada commit en una sola línea, mostrando solo el hash abreviado y el título del mensaje del commit. Es útil para obtener una vista rápida del historial.

  ```bash
  git log --oneline
  ```

  Salida de ejemplo:

  ```
  a1b2c3d (HEAD -> main, origin/main) Agrega nueva funcionalidad X
  f0e9d8c Corrige error en el cálculo de Y
  ...
  ```

- **`--graph`**: Dibuja un gráfico ASCII que representa la estructura de ramas y fusiones (merges) junto al historial de commits. Es muy útil para entender cómo se han integrado las ramas. Se suele combinar con `--oneline` y `--decorate`.

  ```bash
  git log --graph --oneline --decorate
  ```

  Salida de ejemplo:

  ```
  * a1b2c3d (HEAD -> main, origin/main) Agrega nueva funcionalidad X
  |\
  | * 1a2b3c4 (feature/nueva) Implementa parte de la funcionalidad X
  |/
  * f0e9d8c Corrige error en el cálculo de Y
  ...
  ```

- **`--decorate`**: Muestra dónde apuntan las referencias (como ramas locales, remotas y etiquetas) en el historial. `HEAD` indica la confirmación actual.

- **`--stat`**: Muestra estadísticas sobre los archivos modificados en cada commit (qué archivos cambiaron y cuántas líneas se agregaron/eliminaron).

  ```bash
  git log --stat
  ```

- **`-p` o `--patch`**: Muestra el "parche" (diff) introducido por cada confirmación. Es decir, muestra los cambios exactos realizados en el código.

  ```bash
  git log -p -2 # Muestra el parche de los últimos 2 commits
  ```

- **Filtrado de Commits**:

  - `-<n>` o `--max-count=<n>`: Limita el número de commits mostrados a los `n` más recientes. Ejemplo: `git log -5` (muestra los últimos 5).
  - `--since`, `--until`, `--after`, `--before`: Filtran commits por fecha. Ejemplo: `git log --since="2 weeks ago"`.
  - `--author="<patrón>"`: Muestra solo commits cuyo autor coincide con el patrón. Ejemplo: `git log --author="Nombre Apellido"`.
  - `--grep="<patrón>"`: Muestra solo commits cuyo mensaje coincide con el patrón.
  - `-- <ruta/al/archivo>`: Muestra solo los commits que afectaron a un archivo o directorio específico. Ejemplo: `git log -- src/main.js`.

- **Formatos Personalizados**: La opción `--pretty=format:"<string>"` permite definir un formato de salida completamente personalizado usando placeholders como `%h` (hash corto), `%an` (nombre autor), `%ad` (fecha autor), `%s` (asunto/título), etc.
  ```bash
  git log --pretty=format:"%h - %an, %ar : %s"
  ```
  Salida de ejemplo:
  ```
  a1b2c3d - Nombre Apellido, 5 hours ago : Agrega nueva funcionalidad X
  f0e9d8c - Otro Nombre, 1 day ago : Corrige error en el cálculo de Y
  ...
  ```

## Herramientas Gráficas (GUI)

Además de la línea de comandos, existen muchas herramientas gráficas que ofrecen una visualización más interactiva y visual del historial de Git:

- **`gitk`**: Una herramienta gráfica simple que viene incluida con Git. Ejecútala desde la terminal en tu repositorio con `gitk --all`.

- **Clientes Git de Escritorio**: Aplicaciones como Sourcetree, GitKraken, Tower, GitHub Desktop, etc., proporcionan interfaces visuales muy completas para explorar el historial, ver ramas, diffs y realizar operaciones Git.

- **Integraciones en IDEs**: Editores de código como Visual Studio Code (con extensiones como GitLens o Git Graph), IntelliJ IDEA, Eclipse, etc., suelen tener integraciones que permiten visualizar el historial de Git directamente dentro del editor.
