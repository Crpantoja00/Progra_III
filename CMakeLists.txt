cmake_minimum_required(VERSION 3.10) # Versión mínima de CMake requerida

project(Biblioteca) # Nombre del proyecto

set(CMAKE_CXX_STANDARD 20) # Configurar C++20

set(CMAKE_CXX_STANDARD_REQUIRED True)

#Agregar los archivos fuente
add_executable(biblioteca
	src/main.cpp
	src/libro.cpp
	src/biblioteca.cpp
)	# Crear el ejecutable

# Indica donde estan los headers
target_include_directories(biblioteca PRIVATE include)

set_target_properties(biblioteca PROPERTIES LINK_FLAGS "-mconsole")