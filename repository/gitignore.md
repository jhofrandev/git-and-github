# ¿Para qué sirve el archivo `.gitignore`?

El archivo **`.gitignore`** es un archivo de texto que le indica a Git qué archivos o directorios debe ignorar en tu proyecto. Su objetivo es excluir automáticamente elementos que no deben ser rastreados ni subidos al repositorio (como archivos temporales, contraseñas, o dependencias).

---

## **Propósito principal**

- 🚫 **Evitar rastrear archivos innecesarios**:  
  Ejemplo: archivos generados por el sistema, logs, binarios, o configuraciones sensibles.
- 🧹 **Mantener el repositorio limpio**:  
  Solo se versiona lo esencial, mejorando el rendimiento y la claridad.
- 🔒 **Proteger información confidencial**:  
  Previene que datos sensibles (ej: claves API, `.env`) se expongan accidentalmente.

---

## **Casos de uso comunes**

- Archivos generados por el sistema:  
  `Thumbs.db` (Windows), `.DS_Store` (macOS).
- Dependencias de paquetes:  
  `node_modules/` (Node.js), `__pycache__/` (Python).
- Archivos de entorno:  
  `.env`, `config/secrets.yml`.
- Logs y temporales:  
  `*.log`, `tmp/`, `*.tmp`.
- Artefactos de compilación:  
  `dist/`, `build/`, `*.exe`.

---

## **Sintaxis básica**

- **Ignorar un archivo específico**:  
  `archivo.txt`
- **Ignorar todos los archivos con una extensión**:  
  `*.log`
- **Ignorar una carpeta completa**:  
  `carpeta/`
- **Excluir subcarpetas**:  
  `proyecto/**/temp/` (ignora todas las carpetas `temp` dentro de `proyecto`).
- **Excepción (no ignorar)**:  
  `!archivo_importante.log` (ignora todo excepto este archivo).

---

## **Ejemplo de `.gitignore`**

```gitignore
# Ignorar archivos del sistema
.DS_Store
Thumbs.db

# Ignorar dependencias
node_modules/
__pycache__/

# Ignorar logs y temporales
*.log
tmp/

# Ignorar archivos de entorno
.env
config/credentials.yml

# Excepción: No ignorar .env.example
!.env.example
```
