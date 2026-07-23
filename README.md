======================================================================
  SciTE Custom Tabs (Win32) - Parche y Extensión de Pestañas
======================================================================

Parche para SciTE (Windows / Win32) que permite personalizar el diseño de las pestañas (tabs) con fuentes grandes, colores dinámicos para estados activos e inactivos, fondos

Puedes modificar la apariencia de tus pestañas al vuelo agregando las
siguientes líneas en tu archivo de configuración (SciTEGlobal.properties
o tu archivo de usuario de propiedades). El editor las lee automáticamente:

# 1. Pestaña Activa (Pestaña seleccionada actualmente)
buffers.activo=font:Calibri,size:24,fore:#FFFFFF,back:#00519d

# 2. Pestañas Inactivas (El resto de pestañas abiertas)
buffers.noactivo=font:Calibri,size:22,fore:#888888,back:#0A141D

# 3. Fondo detrás de la barra de pestañas
buffers.detras=back:#151515

# 4. Color del borde de las pestañas
buffers.borde=#000000


¿Qué hace cada parámetro?
- font : Define la familia tipográfica (ej. Calibri, Segoe UI, Consolas).
- size : El tamaño del texto en puntos. Calcula dinámicamente el alto
		 y ancho de la pestaña para que letras grandes no se corten.
- fore : Color del texto de la pestaña (en formato hexadecimal RGB).
- back : Color de fondo del botón de la pestaña.

----------------------------------------------------------------------
 ⚡  (Compilación Rápida)
----------------------------------------------------------------------
No necesitas compilar todo el motor de Scintilla ni Lexilla desde cero.
- Tiempo estimado: Menos de 10 minutos.
- Solo compilas Win32: Solo modificas y compilas la interfaz de Windows (SciTEWin.cxx).
- Compilador utilizado: x86_64-w64-mingw32-g++ (MinGW-w64).


----------------------------------------------------------------------
 📁 Estructura de Archivos del Proyecto
----------------------------------------------------------------------
compilar/
│
├── scite/                    <-- Carpeta principal del código fuente de SciTE
│   ├── src/                  <-- Código base independiente de la plataforma
│   └── win32/                <-- Código específico de Windows
│       ├── SciTEWin.cxx      * [MODIFICADO] Lógica de dibujo y tabs
│       ├── SciTEWin.h        <-- Cabecera de la ventana principal
│       └── makefile          <-- Archivo make para compilar con MinGW
│
└── scintilla/                <-- Motor Scintilla (no requiere recompilar)
	└── include/

----------------------------------------------------------------------
 🛠️ ¿Cómo compilarlo en menos de 10 minutos?
----------------------------------------------------------------------
1. Coloca el archivo SciTEWin.cxx actualizado dentro de scite/win32/.
2. Abre tu terminal de comandos compatible con MinGW (MSYS2 / MinGW).
3. Navega hasta la carpeta win32:
   cd scite/win32
4. Ejecuta la compilación con el compilador x86_64-w64-mingw32-g++:
   make clean
   make
5. Copia el ejecutable resultante (scite.exe) junto a las DLLs de
   Scintilla y Lexilla a tu directorio final de distribución. ¡Listo!
======================================================================


