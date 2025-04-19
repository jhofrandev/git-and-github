# Configuración Local vs. Global en Git

Git permite personalizar su comportamiento en tres niveles: **sistema**, **global** y **local**. Aquí te explico las diferencias clave entre la configuración **local** y **global**:

---

## **Configuración Global (`--global`)**

- **Ámbito**: Afecta a **todos los repositorios** de tu usuario en el sistema.
- **Ubicación del archivo**:
  - Linux/macOS: `~/.gitconfig`
  - Windows: `C:\Users\<tu-usuario>\.gitconfig`
- **Cuándo usarla**:
  - Para preferencias personales que aplican a todos tus proyectos.
  - Ejemplo: nombre, email, editor de texto predeterminado, o aliases que usas frecuentemente.

### Comandos típicos:

```bash
git config --global user.name "Tu Nombre"
git config --global core.editor "code --wait"
git config --global alias.st "status"
```

## **Configuración Local (`--local`)**

- **Ámbito**: Afecta **únicamente al repositorio actual** donde ejecutas el comando. Es el nivel predeterminado si no especificas `--global` o `--system`.
- **Ubicación del archivo**: Dentro del repositorio, en `.git/config`.
- **Cuándo usarla**:
  - Para configuraciones específicas de un proyecto en particular.
  - Para anular temporalmente una configuración global para un solo repositorio.
  - Ejemplo: Usar un email de trabajo diferente para un proyecto específico, configurar herramientas específicas del proyecto.

### Comandos típicos (ejecutados dentro del repositorio):

```bash
git config user.email "tu-email-de-trabajo@ejemplo.com"
git config core.fileMode false # Ignorar cambios en permisos de archivo (útil en Windows)