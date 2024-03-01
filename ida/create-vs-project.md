## 1
- Crear una proyecto escogiendo "Dynamic-Link Library (DLL)"
- `View -> Other Windows -> Project Manager`, o en la ventana Solution Explorer cambiar la pestaña que se encuentra en la parte inferior Project Manager
- En el nombre del proyecto (no en los directorios) click derecho -> Add New Project Property Sheet...
- Dirigirse al directorio Release|x64 o en el que desees, desplegarlo, y hacer click derecho en PropertySheet -> Properties
- En `User Macros` crear lo siguiente:
  - Name: IDASDK, Value: <Ruta del SDK del IDA (sin comillas)>
  - Name: IDADIR, Value: <Ruta de instalación del IDA Pro (sin comillas)>
  - En los dos casos dar click a "Set this macro as an environment variable in the build environment"

## 2

- Dirigirse a Solution Explorer, y en el nombre del proyecto click derecho -> Properties
- `C/C++ -> Additional Includes Directories` agregar, `$(IDASDK)\include;$(IDADIR)\plugins\hexrays_sdk\include`
- `C/C++ -> Preprocessor -> Processor definitions`:
  - x64: `__NT__;__EA64__`
  - x86: `__NT__;` 
- `Linker -> All options -> Additional Library Directories` agregar:
  - x64: `$(IDASDK)\lib\x64_win_vc_64_pro`
- `Linker -> All options -> Additional Dependencies` agregar, `ida.lib`
  - Opcional, al usar ventenas: `user32.lib`
- `Linker -> Command Line -> Additional Options` agregar,
  - para plugin: `/EXPORT:PLUGIN`

## Desactivar para evitar errores

- `C/C++ -> General -> SDL checks`, cambiar a `No (/sdl-)`
