# Void Code

Editor de código nativo para Windows, escrito en Rust. Es oscuro, sin bordes y se maneja sobre todo con el teclado. Incluye terminal, git, GitHub, servidores de lenguaje, snippets y vista previa de HTML, JSX y TSX.

Este repositorio solo publica las versiones. Las notas de cada una están en [CHANGELOG.md](CHANGELOG.md) y en su release.

## Descargar

En la [última release](https://github.com/Spoch-dev/void_code/releases/latest):

- **`void_code-X.Y.Z-setup.exe`**: el instalador para Windows. No pide permisos de administrador, crea los accesos del menú Inicio y se actualiza solo.
- **`void_code-X.Y.Z-windows-x86_64.exe`**: el ejecutable suelto, sin instalar.

Cada archivo va con su `.sha256` para comprobar que la descarga está bien:

```powershell
(Get-FileHash .\void_code-X.Y.Z-setup.exe -Algorithm SHA256).Hash
```

## Actualizaciones

La copia instalada mira aquí si hay una versión nueva: 5 segundos después de arrancar y luego cada 6 horas. Si la hay, sale un botón en la barra de título que descarga el instalador, comprueba su SHA-256 y lo instala. Se desactiva en Ajustes → Actualizaciones.

## Qué hace

- Editor con resaltado de sintaxis, minimapa, varios cursores, snippets, búsqueda y deshacer por grupos.
- Mosaico de editores y de terminales reales, árbol de archivos y búsqueda difusa (Ctrl+P).
- Diagnósticos, autocompletado e ir a la definición con los servidores de lenguaje que tengas instalados.
- Panel de git y vista de GitHub, con su propia sesión guardada en el llavero del sistema.
- Vista previa de HTML, JSX y TSX junto al código, y botones para ejecutar, compilar y probar.
- 19 temas (Ctrl+K T) y paquetes de iconos de archivo Material y Catppuccin (Ctrl+K I).

## Atajos principales

| Atajo | Qué hace |
|---|---|
| Ctrl+P | Buscar un archivo |
| Ctrl+O | Abrir otra carpeta |
| Ctrl+B | Árbol de archivos |
| Ctrl+, | Ajustes |
| Ctrl+T | Terminal |
| Ctrl+G / Ctrl+Shift+G | Panel git / vista de GitHub |
| Ctrl+S | Guardar |
| Ctrl+W | Cerrar el archivo |
| F5 | Ejecutar el archivo o su proyecto |
| Ctrl+Shift+V | Vista previa (Markdown, SVG, HTML, JSX y TSX) |
| Ctrl+K T / Ctrl+K I | Tema / iconos de archivo |

## Seguridad

Si encuentras un fallo de seguridad, no abras un issue público: avísame en privado desde la pestaña **Security** de este repositorio ([Report a vulnerability](https://github.com/Spoch-dev/void_code/security/advisories/new)). Más detalles en [SECURITY.md](SECURITY.md).

## Licencia

[MIT](LICENSE) © 2026 Spoch-dev.

Los iconos de archivo son de [Material Icon Theme](https://github.com/material-extensions/vscode-material-icon-theme) (MIT, © Material Extensions) y de [Catppuccin Icons for VSCode](https://github.com/catppuccin/vscode-icons) (MIT, © Catppuccin y thang-nm). Void Code no los incluye: los descarga al elegirlos. Los snippets por lenguaje son de [friendly-snippets](https://github.com/rafamadriz/friendly-snippets).
