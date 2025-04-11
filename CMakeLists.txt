cmake_minimum_required(VERSION 3.10) # Versión mínima de CMake requerida

project(Biblioteca) # Nombre del proyecto

set(CMAKE_CXX_STANDARD 20) # Configurar C++20

set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(biblioteca_exe
	main.cpp
	libro.cpp
	biblioteca.cpp
)	# Crear el ejecutable

set_target_properties(biblioteca_exe PROPERTIES LINK_FLAGS "-mconsole")