# Comando `git init`

El comando **`git init`** se utiliza para inicializar un nuevo repositorio de Git en un directorio local. Es el primer paso para empezar a usar Git en un proyecto.

---

## **¿Qué hace?**

1. **Crea un repositorio vacío**:

   - Genera una carpeta oculta llamada `.git` en tu proyecto, donde se almacenan todos los metadatos y el historial de cambios.
   - Sin este comando, Git no puede rastrear los archivos del proyecto.

2. **Prepara el entorno**:
   - Define el directorio actual como un "espacio de trabajo" gestionado por Git.
   - Establece la rama inicial (por defecto, `main` o `master`, según tu configuración).

---

## **Casos de uso**

- ✅ **Iniciar un proyecto nuevo**:
  ```bash
  mkdir mi-proyecto
  cd mi-proyecto
  git init
  ```
