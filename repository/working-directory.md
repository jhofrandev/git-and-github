# El Directorio de Trabajo (Working Directory) en Git

El Directorio de Trabajo es uno de los conceptos fundamentales en Git:

- **Definición**: Es la carpeta de tu proyecto en tu sistema de archivos donde trabajas y editas tus archivos directamente. Es la versión actual de los archivos que ves y modificas.
- **Características**:
  - Contiene todos los archivos y subdirectorios de tu proyecto.
  - Incluye tanto los archivos que Git está rastreando (`tracked`) como los que no (`untracked`).
  - Es donde realizas cambios antes de prepararlos (`stage`) y confirmarlos (`commit`) en el repositorio.
  - Representa el estado actual de tus archivos en el sistema de archivos local.

## Relación con otras áreas de Git

Git maneja tus archivos a través de tres áreas principales:

1.  **Directorio de Trabajo (Working Directory)**: Donde modificas tus archivos. Es tu "espacio de trabajo" actual.
2.  **Área de Preparación (Staging Area / Index)**: Una instantánea intermedia donde colocas los cambios específicos que quieres incluir en tu próximo `commit` usando `git add`.
3.  **Repositorio Git (.git directory)**: Donde Git almacena permanentemente el historial de tu proyecto (los `commits`). Cada `commit` es una instantánea completa del proyecto en un punto específico del tiempo.

## Flujo de trabajo típico

El flujo básico de trabajo en Git implica mover cambios entre estas tres áreas:

1. **Working Directory**
   - Modify files directly
   - `git add` ↓

2. **Staging Area**
   - Stage changes for commit
   - `git commit -m "Message"` ↓

3. **Git Repository (.git)**
   - Store permanent snapshot
