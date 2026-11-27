# Notas de versión

Cada versión empieza con un título `## X.Y.Z`; la más reciente va primero.

## 0.2.9

### Errores a la vista

- Las líneas con un error o un aviso se tiñen de su color y llevan al final el mensaje del más grave (con `(+N)` si hay más en esa línea); si no cabe, termina en «…» antes del minimapa.
- Minimapa: cada error marca su línea con una banda y, en el borde derecho, una regla a escala enseña todos los del archivo aunque el minimapa no llegue a su línea.

### Rutas

- Separadas por puntos: tras `using`, `import`, `from`, `namespace` o `package` (`using Core.Adapters.`), la lista de sugerencias enseña las carpetas (con punto, para seguir dentro) y los archivos sin extensión. No distingue mayúsculas y busca desde la raíz, junto al archivo y desde `src/`. Si no hay nada en el disco (`using System.`), sugiere el servidor de lenguaje.
- `src=`, `href=`, `url(`, `@import`, `import "…"`, `from "…"` y `require(…)`: su valor cuenta como ruta aunque no lleve barra. `<link href="estilos.css">` o `<script src="app.js">` se ven con el vistazo bajo la línea, y al escribir `href="` ya se sugieren los archivos junto al que se edita.

## 0.2.8

### Rutas en la lista de sugerencias

- Al escribir una ruta (`./`, `../`, `~/`, `C:\` o entre comillas con alguna barra, como `"src/core/`), la lista de sugerencias enseña los archivos y carpetas de esa carpeta, igual que los snippets.
- Se busca junto al archivo que se edita y desde la raíz del proyecto; `~/` es la carpeta personal.
- Carpetas primero, con su barra; los archivos llevan la extensión a la derecha y los ocultos van al final. Lo escrito tras la última barra filtra (nombres con `.` y `-` incluidos).
- Al aceptar una carpeta (Enter o Tab) la lista pasa a lo que tiene dentro; al salir de la ruta se cierra.

## 0.2.7

### Vistazo bajo la línea

- Con el ratón (o el cursor de texto, quieto) sobre una ruta, una URL o un símbolo, aparece un panel justo debajo de esa línea con lo que hay detrás, unido al texto por una raya.
- **Rutas** (`./app/sum.js`, `src/lib.rs:12:5`, `docs/guia.md#L3`, `C:\…`): las primeras líneas del archivo, numeradas, desde la línea indicada y con ella resaltada. Se buscan junto al archivo, desde la raíz del proyecto o tal cual si son absolutas; sin extensión (`import './window'`) se prueban las habituales. Una carpeta enseña lo que tiene.
- **URLs**: el título, la descripción y los primeros párrafos de la página. Se descarga una vez en segundo plano y se guarda mientras la app está abierta.
- **Símbolos**: el extracto de su definición (del servidor de lenguaje), con la documentación y los diagnósticos de ese punto debajo.
- Mientras se escribe no sale; vuelve en cuanto se mueve el cursor.

### Editor flotante

- **Ctrl+F y luego Ctrl+L**: se esconde el resto de la interfaz y queda solo el editor con foco, en una ventana que se arrastra por su cabecera y se redimensiona por la esquina. Ctrl+F, Ctrl+L otra vez vuelve al mosaico.
- Ctrl+B enseña y esconde el árbol de archivos acoplado a su izquierda, que se mueve con la ventana.
- En este modo el borde izquierdo del minimapa se arrastra para cambiar su ancho.

## 0.2.6

### Cambios sin guardar

- Cerrar un archivo (Ctrl+W o la × de su pestaña), la ventana o la carpeta con cambios sin guardar abre un cuadro de diálogo: **Guardar**, **No guardar** o **Cancelar**. Antes solo avisaba y había que cerrar otra vez para descartarlos.
- Enter elige el botón marcado (Guardar, de entrada), ←→ o Tab cambian de botón y Esc cancela. Al cerrar la ventana enseña la lista de archivos con cambios.
- Abrir otra carpeta con archivos sin guardar ya no se niega: pregunta si guardarlos y la abre.

## 0.2.5

### Correcciones

- Con la vista previa de HTML, JSX o TSX al lado del código, el teclado podía quedarse en la página (al hacer clic en ella, o al recargarse tras guardar): Tab con varias líneas seleccionadas saltaba entre los enlaces de la página en vez de sangrarlas. Ahora un clic en Void Code y el final de cada recarga devuelven el teclado al editor; los clics dentro de la página siguen siendo de la página.

## 0.2.4

### Iconos de archivo

- **Paquetes de iconos** (Ctrl+K I, o Ajustes → Apariencia): Material (color), Material (monocromo), Catppuccin (color), Catppuccin (full color, más saturado) y Catppuccin (monocromo). ↑↓ los enseña al momento en el árbol, Enter deja el elegido y Esc vuelve al que había.
- Se ven en los paneles del árbol y en el sidebar fijado, con iconos propios para cada tipo de archivo y para carpetas como `src`, `docs` o `assets` (abiertas o cerradas).
- Se descargan al elegirlos, en una versión fija, y cada icono solo cuando aparece un archivo que lo usa; quedan en la caché. Sin conexión se ven los de siempre.
- Los iconos son de [Material Icon Theme](https://github.com/material-extensions/vscode-material-icon-theme) y [Catppuccin Icons](https://github.com/catppuccin/vscode-icons), ambos con licencia MIT.

## 0.2.3

### Correcciones

- Con la lista de sugerencias abierta (la que sale al escribir), Shift+flechas no seleccionaba y Tab aceptaba la sugerencia en vez de sangrar. Ahora la lista solo responde a sus teclas sin modificadores y se cierra al seleccionar texto, así que Tab y Shift+Tab sangran y quitan sangría a todas las líneas seleccionadas.

## 0.2.2

### Actualizaciones

- Void Code mira solo si hay una versión nueva publicada en GitHub: 5 segundos después de arrancar y luego cada 6 horas. Se desactiva en Ajustes → Actualizaciones.
- Si la hay, aparece un botón en la barra de título. En la copia instalada en Windows descarga el instalador, comprueba su SHA-256 con el de la release y, con otro clic, lo instala y vuelve a abrir la app. En la copia suelta y en Linux abre la página de la release.
- A partir de esta versión las siguientes se ofrecen solas; para llegar a esta hay que instalarla a mano.

### Arranque

- Sin argumentos no se abre ninguna carpeta ni se lee ningún directorio. Antes se abría la carpeta actual, que desde el menú Inicio es la de instalación (y el árbol fijado la enseñaba). Se elige la carpeta desde la portada: Ctrl+O o la última abierta.
- Sin carpeta, lo que la necesita (Ctrl+P, el árbol, Git, GitHub y Proyecto) avisa de que hay que abrir una, y las terminales empiezan en la carpeta personal.

## 0.2.1

### Correcciones

- En Windows, Ejecutar, Compilar y Probar fallaban con «no se encuentra la ruta»: la carpeta del proyecto llevaba delante el prefijo `\\?\`, que PowerShell no acepta. Ahora se usa la ruta normal, también al cambiar de carpeta y en la vista de GitHub.

## 0.2.0

### Temas

- **Selector de tema** (Ctrl+K T): se filtra escribiendo, ↑↓ lo enseña al momento, Enter lo deja puesto y Esc vuelve al de antes.
- 19 temas: Void, Acrylic Void, Dracula, Nord, Gruvbox, Monokai, Tokyo Night, Catppuccin Mocha y Latte, One Dark, Rosé Pine, Everforest, Kanagawa, Ayu Mirage, GitHub Dark y Light, Solarized Dark y Light y Neón.
- **Acrylic Void**: ventana translúcida con el escritorio desenfocado detrás (en Windows lo pinta el sistema).

### Vista previa web

- HTML, JSX y TSX se ven renderizados en una tile del mosaico junto al código (Ctrl+Shift+V), con barra para recargar, abrir en el navegador o volver al código. Usa WebView2 en Windows y WKWebView en macOS; en Linux se abre en el navegador.
- Ctrl+Alt+Shift+V (o F5 sin tareas, o la barra de ejecutar) los abre en el navegador del sistema. Los componentes de React se transpilan y montan en una página propia.

### Árbol de archivos como sidebar

- Ctrl+K B fija el árbol a la izquierda; en Ajustes se elige **pegado** (el mosaico se estrecha) o **flotante** (tarjeta encima del editor).
- Sigue al archivo abierto y se maneja con el teclado: Ctrl+B le pasa el foco, ↑↓ ← → Enter y Esc, y crear, renombrar, cortar, copiar, pegar y enviar a la papelera como en los paneles.

### Editor

- Al escribir se despliega una lista con los snippets que encajan.
- **Guardado automático** (Ajustes → Archivos), con el retraso a elegir entre 250 ms y 10 s.

### Correcciones

- En Windows, la sesión de cada proyecto (archivos abiertos, mosaico y cursores) se guardaba en la carpeta actual en vez de en la carpeta de estado de Void Code, y no se recuperaba al volver a abrirlo.

### Otros

- La página de inicio queda centrada, sin las notas de la versión al lado.
- Código reorganizado por dentro (núcleo hexagonal; interfaz en base, hooks, rutas y componentes comunes y compuestos), sin cambios de uso.

## 0.1.0

### Rendimiento

- El editor solo maqueta las líneas que se ven: un archivo de 4,4 MB ocupa unos 130 MB de memoria (antes, 1,7 GB).
- Se abren archivos de cualquier tamaño; antes el límite era de 5 MB.
- **Modo archivo grande** (desde 2 MB, se cambia en Ajustes): sin minimapa, servidor de lenguaje, marcas de git ni atenuado por bloque.
- El resaltado se rehace solo alrededor de lo que cambia, y en archivos largos el principio se colorea primero.
- Deshacer guarda 100 pasos por editor, o 50 con cinco editores o más en pantalla.
- Dibujado con OpenGL: unos 220 MB menos de memoria al arrancar.

### GitHub

- Sesión propia de Void Code: se inicia en el navegador con un código que se copia solo, sin terminal ni `gh`.
- El token se guarda en el llavero del sistema; desconectar no afecta a `gh` ni a git.
- La vista de GitHub lee el repositorio, issues, pull requests, Actions y releases con la API de GitHub.

### Proyecto y ajustes

- **Proyecto** (Ctrl+Shift+P): prepara la carpeta para desarrollar con git, las ramas main, release y test, licencia MIT y .gitignore, en este equipo o en GitHub con las tres ramas subidas. Antes de crear se ve lo que se va a hacer.
- **Abrir carpeta** (Ctrl+O): explorador en el centro de la app con un mosaico de carpetas, buscador, ruta en migas, recientes, lugares y unidades, marca en los repositorios git y botón para crear carpetas.
- Ajustes por secciones y con una explicación en cada uno; nuevos: escala de la interfaz, pasos de deshacer y la cuenta de GitHub.

### Editor

- Seleccionar por palabras con Ctrl+Shift+flechas; borrar palabras con Ctrl+Retroceso y Ctrl+Supr.
- Doble clic selecciona la palabra y triple clic la línea.
- Al pegar, los saltos de línea de Windows se convierten en saltos normales.
- En archivos con saltos de Windows, el cursor ya no se queda detrás del final de la línea.

### Incluye

- Resaltado de sintaxis, minimapa, varios cursores, snippets y búsqueda en el archivo.
- Mosaico de editores y de terminales, árbol de archivos y búsqueda difusa (Ctrl+P).
- Diagnósticos, autocompletado e ir a la definición con servidores de lenguaje.
- Panel de git y vista de GitHub.
- Markdown con vista de lectura, visor de imágenes y botones para ejecutar y compilar.
