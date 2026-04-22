
# Guía de instalación y configuración de FNM (Fast Node Manager) en Windows

Esta guía te ayudará a instalar y configurar correctamente Fast Node Manager (`fnm`) en Windows, incluyendo la activación automática mediante el archivo de perfil de PowerShell (`$PROFILE`).

---

## Paso 1: Instalar FNM con Winget

Abre **PowerShell** o **Windows Terminal** y ejecuta:

```powershell
winget install Schniz.fnm
```

Esto instalará `fnm` en tu sistema.

---

## Paso 2: Instalar una versión de Node.js

Después de instalar `fnm`, puedes instalar Node.js ejecutando:

```powershell
fnm install 18
```

También puedes usar:

```powershell
fnm install --lts     # Última versión LTS
fnm install latest    # Versión más reciente disponible
```

---

## Paso 3: Activar FNM automáticamente en PowerShell

Para que `fnm` funcione cada vez que abras PowerShell, necesitas configurar tu archivo de perfil (`$PROFILE`).

### 1. Verifica la ruta de tu perfil:

```powershell
echo $PROFILE
```

### 2. Si el archivo no existe, créalo:

```powershell
New-Item -Path $PROFILE -ItemType File -Force
```

### 3. Agrega el entorno de `fnm` al perfil:

```powershell
fnm env --use-on-cd | Out-File -Append -Encoding utf8 $PROFILE
```

### 4. Cierra y vuelve a abrir PowerShell

Luego ejecuta:

```powershell
node -v
npm -v
```

---

## Paso 4: Uso de FNM

### Ver versiones instaladas

```powershell
fnm list
```

### Usar una versión específica

```powershell
fnm use 18
```

### Establecer una versión por defecto

```powershell
fnm default 18
```

### Ver versión activa

```powershell
fnm current
```

---

## ⚠️ Si ves el error: *“la ejecución de scripts está deshabilitada…”*

Ejecuta PowerShell como administrador y permite la ejecución de scripts para tu usuario:

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Presiona `S` (Sí) cuando se te solicite.

---

## Recomendación final

`fnm` es ideal para quienes trabajan con múltiples versiones de Node.js, especialmente en Windows. Una vez configurado correctamente, te ahorrará muchos problemas de compatibilidad y configuración en tus proyectos o en entornos educativos.

---

## Comandos útiles de FNM

| Comando                            | Descripción                                         |
|------------------------------------|-----------------------------------------------------|
| `fnm list` / `fnm ls`              | Lista las versiones de Node.js instaladas          |
| `fnm ls-remote`                    | Lista todas las versiones disponibles para instalar|
| `fnm current`                      | Muestra la versión de Node.js actualmente activa   |
| `fnm use <versión>`               | Cambia la versión activa de Node.js                |
| `fnm default <versión>`           | Establece una versión predeterminada               |
| `fnm install <versión>`           | Instala una versión específica de Node.js          |
| `fnm install --lts`               | Instala la última versión LTS                      |
| `fnm install latest`              | Instala la última versión estable disponible       |
| `fnm uninstall <versión>`         | Elimina una versión específica de Node.js          |
| `fnm env`                          | Muestra variables de entorno y configuración       |

---
