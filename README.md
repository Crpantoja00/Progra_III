# Proyecto Biblioteca

Este proyecto en C++ implementa una biblioteca básica con clases para manejar libros y su colección. Se ha configurado utilizando CMake y se gestiona con Git. Este documento sirve como guía para compilar el proyecto correctamente y trabajar con control de versiones.

---

## 🛠️ Compilación con CMake

### Estructura del proyecto
```
Biblioteca/
├── CMakeLists.txt
├── src/
│   ├── main.cpp
│   ├── Libro.cpp
│   └── Biblioteca.cpp
├── include/
│   ├── Libro.h
│   └── Biblioteca.h
```

### Contenido del `CMakeLists.txt`
```cmake
cmake_minimum_required(VERSION 3.10) # Versión mínima de CMake requerida

project(Biblioteca) # Nombre del proyecto

set(CMAKE_CXX_STANDARD 20) # Usar C++20
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(biblioteca
    src/main.cpp
    src/libro.cpp
    src/biblioteca.cpp
)

target_include_directories(biblioteca PRIVATE include) # Incluir headers
set_target_properties(biblioteca PROPERTIES LINK_FLAGS "-mconsole") # Opcional, para evitar WinMain error
```

### Pasos para compilar
```bash
mkdir build        # Crear carpeta de compilación
cd build           # Entrar a la carpeta
cmake ..           # Generar archivos de compilación
cmake --build .    # Compilar el proyecto
./biblioteca       # Ejecutar el ejecutable (en Windows: biblioteca.exe)
```

### 🔄 Limpieza del proyecto
Si hay errores o deseas reiniciar la configuración:
```bash
# Desde dentro de la carpeta raíz del proyecto
rmdir /s /q build             # Eliminar carpeta build (en Windows)
rm -rf build/                 # En sistemas Unix/Linux
```
Alternativamente, solo elimina el caché si ya estás dentro de la carpeta build:
```bash
del /f /q CMakeCache.txt      # Eliminar caché en Windows
rmdir /s /q CMakeFiles
```

---

## 🔧 Control de versiones con Git

### Configuración inicial (solo una vez)
```bash
git config --global user.name "TuNombreDeUsuario"
git config --global user.email "tu@email.com"
```

### Subir el proyecto a GitHub
```bash
cd Biblioteca              # Entrar a la carpeta del proyecto
git init                   # Iniciar repositorio
```

Agregar archivos y hacer commit:
```bash
git add .                  # Agregar todos los archivos
git commit -m "Primer commit"
```

Conectar con repositorio remoto:
```bash
git remote add origin https://github.com/Usuario/NombreRepo.git
```

Subir al repositorio remoto:
```bash
git branch -M main         # Renombrar rama a main (opcional)
git push -u origin main
```

### Crear una nueva rama y subir cambios
```bash
git checkout -b nueva-rama     # Crear y cambiar a nueva rama
# ...hacer modificaciones...
git add .                      # Agregar cambios
git commit -m "Cambios hechos"
git push -u origin nueva-rama  # Subir la rama remota
```

### Fusionar ramas (merge)
```bash
git checkout main              # Cambiar a rama principal
git pull origin main           # Asegurarse de estar actualizado
git merge nueva-rama           # Fusionar los cambios
```

---

## 📦 Comandos útiles adicionales

### Git
```bash
git status           # Ver estado del repositorio
git log              # Ver historial de commits
git diff             # Ver diferencias sin commitear
git branch           # Ver ramas actuales
git remote -v        # Ver URL del repositorio remoto
git pull             # Descargar cambios del remoto
git clone <url>      # Clonar repositorio existente
```

### CMake
```bash
cmake -G "MinGW Makefiles" ..    # Especificar generador
cmake --build . --target clean   # Limpiar build
cmake -DCMAKE_BUILD_TYPE=Debug ..# Compilar en modo depuración
```

---


