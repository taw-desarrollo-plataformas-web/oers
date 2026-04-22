
# Guía de instalación y uso de NVM (Node Version Manager) en Linux (Ubuntu/Debian)

La presente guía está diseñada para ayudarle a instalar y configurar NVM (Node Version Manager) en distribuciones Linux basadas en Debian como Ubuntu. NVM te permite instalar y cambiar fácilmente entre diferentes versiones de Node.js.

---

## Paso 1: Instalar NVM

Abre una terminal y ejecuta:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.2/install.sh | bash
```

Luego, **cierra y vuelve a abrir la terminal**, o ejecuta:

```bash
source ~/.bashrc
```

> Si usas Zsh, puede usar `source ~/.zshrc` en su lugar.

---

## Paso 2: Verificar instalación

Para verificar que NVM está instalado correctamente, ejecuta:

```bash
nvm --version
```

Debería ver un número de versión como salida, por ejemplo: `0.40.2`

---

## Paso 3: Instalar Node.js

```bash
nvm install 18      # Instala Node.js v18
nvm install --lts   # Instala la última versión LTS
nvm install node    # Instala la versión más reciente (no LTS)
```

---

## Paso 4: Usar una versión específica

```bash
nvm use 18
```

Para cambiar entre versiones que ya instalaste.

Puedes ver qué versión está activa con:

```bash
nvm current
```

---

## Paso 5: Establecer una versión por defecto

```bash
nvm alias default 18
```

Esto asegura que cada nueva terminal use esa versión por defecto.

---

## Paso 6: Ver y gestionar versiones

```bash
nvm list           # Ver versiones instaladas
nvm ls-remote      # Ver versiones disponibles para instalar
nvm uninstall 16   # Eliminar Node.js v16
```

---

## Recomendaciones finales

- NVM es una herramienta esencial para ambientes de desarrollo modernos.
- Úsala especialmente si trabaja con varios proyectos que requieren versiones distintas de Node.js.
- Si usas un archivo `.nvmrc` dentro de un proyecto con el contenido `18`, puede activar esa versión con:

```bash
nvm use
```

---
