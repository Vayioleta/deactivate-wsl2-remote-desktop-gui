# Deshabilitar `msrdc.exe` en WSL

Este documento explica cómo deshabilitar `msrdc.exe` en Windows Subsystem for Linux (WSL) editando el archivo de configuración `.wslconfig`.

## Pasos para deshabilitar `msrdc.exe`

### 1. Abrir la configuración de WSL

Primero, abre una terminal de WSL (por ejemplo, Ubuntu en Windows).

### 2. Editar el archivo `.wslconfig`

Debes editar (o crear si no existe) el archivo `.wslconfig` en tu directorio de usuario de Windows.

#### 2.1. Navegar al directorio del usuario

En la terminal de WSL, navega al directorio de usuario de Windows. El directorio de usuario se encuentra en `/mnt/c/Users/<tu_usuario>`. Asegúrate de reemplazar `<tu_usuario>` con tu nombre de usuario de Windows. Puedes usar el siguiente comando para abrir el archivo con `nano`:

```bash
nano /mnt/c/Users/<tu_usuario>/.wslconfig
```

Si prefieres otro editor de texto, puedes usarlo en lugar de `nano`.

#### 2.2. Añadir configuración para deshabilitar `msrdc.exe`

Dentro del archivo `.wslconfig`, añade las siguientes líneas:

```ini
[wsl2]
guiApplications=false
```

Esto deshabilita el soporte de aplicaciones gráficas en WSL, evitando que `msrdc.exe` se ejecute.

### 3. Guardar y salir del editor

Si usaste `nano`, presiona `Ctrl+X` para salir, luego `Y` para confirmar los cambios, y `Enter` para guardar el archivo.

### 4. Reiniciar WSL

Para que los cambios surtan efecto, debes reiniciar WSL. Puedes hacerlo cerrando todas las instancias de WSL y luego reiniciándolas. Alternativamente, puedes usar una terminal de PowerShell con permisos de administrador y ejecutar:

```powershell
wsl --shutdown
```

Después de esto, abre nuevamente tu terminal de WSL.

## Confirmación

Una vez que hayas seguido estos pasos, `msrdc.exe` debería estar deshabilitado en WSL.

---
