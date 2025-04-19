# Confirmar Cambios (Committing Changes)

Confirmar cambios (`git commit`) es el acto de guardar permanentemente la instantánea de tu Área de Preparación en el historial del repositorio Git.

- **Propósito**: Crear un punto de guardado seguro en el historial de tu proyecto. Cada commit representa una versión estable y significativa del proyecto a la que puedes volver más tarde.
- **Funcionamiento**:
    - El comando `git commit` toma los archivos y cambios que están actualmente en el Área de Preparación (lo que añadiste con `git add`) y los empaqueta en un nuevo objeto de commit.
    - Cada commit incluye:
        - Un **identificador único (hash SHA-1)** que lo distingue.
        - Una **referencia al commit padre** (o padres, en caso de fusiones), creando así la cadena del historial.
        - Una **instantánea del contenido** del proyecto (tal como estaba en el Área de Preparación).
        - **Metadatos**: Autor, fecha y, crucialmente, un **mensaje de commit**.
- **El Mensaje de Commit**: Es una descripción que explica *qué* cambios se hicieron y *por qué*. Escribir buenos mensajes de commit es fundamental para entender el historial del proyecto.
- **Relación con el Staging Area**: `git commit` *solo* registra lo que está en el Área de Preparación. Los cambios en el Directorio de Trabajo que no se hayan añadido con `git add` no se incluirán en el commit.
- **Historial**: Los commits forman una línea de tiempo del desarrollo del proyecto. Puedes navegar por este historial, comparar versiones y restaurar estados anteriores.

### Comandos Típicos:

```bash
# Abre el editor configurado para escribir un mensaje de commit
git commit

# Confirma con un mensaje directamente en la línea de comandos
git commit -m "Mensaje descriptivo del cambio"

# Añade todos los archivos rastreados modificados al Staging Area y confirma en un solo paso
# ¡Cuidado! Esto omite la revisión cuidadosa del Staging Area.
git commit -a -m "Mensaje descriptivo"

# Modifica el último commit (cambia el mensaje o añade/quita cambios)
# ¡No uses esto en commits que ya has compartido con otros!
git commit --amend