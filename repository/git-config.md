# Comando `git config`

El comando **`git config`** se utiliza para establecer o consultar opciones de configuración de Git. Estas configuraciones definen cómo funciona Git en tu sistema, desde tu identidad hasta preferencias de comportamiento.

---

## **¿Para qué sirve?**

- Definir tu **nombre** y **correo electrónico** asociado a los commits.
- Configurar el **editor de texto predeterminado** (ej: VS Code, Nano).
- Personalizar comportamientos como colores, alias o integraciones con herramientas externas.

---

## **Niveles de configuración**

Git permite configuraciones en tres ámbitos:

1. **Sistema (`--system`)**:  
   Afecta a **todos los usuarios** en el sistema operativo.

   ```bash
   git config --system <opción> <valor>
   ```

2. **Global (`--global`)**:  
   Configuración para **tu usuario actual** (la más usada).
   ```bash
   git config --global user.name "Tu Nombre"
   ```
3. **Local (`--local`)**:
   Aplica solo **al repositorio actual**.
   ```bash
   git config --local <opción> <valor>
   ```
