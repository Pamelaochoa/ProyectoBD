# ProyectoBD
Configuración de la Base de Datos.

Instalar MySQL: Si aún no tienes MySQL instalado, descarga e instala MySQL desde MySQL Downloads.

Crear una base de datos: Inicia sesión en tu servidor de MySQL y crea una nueva base de datos. Por ejemplo:
# CREATE DATABASE biblioteca;
Configurar las tablas: Utiliza el script proporcionado en schema.sql para crear las tablas necesarias en la base de datos.
#Instalación de Dependencias

Instalar Python: Si aún no tienes Python instalado, descarga e instala Python desde Python Downloads.
Instalar bibliotecas Python: Utiliza pip para instalar las bibliotecas Python necesarias:

## pip install mysql-connector-python
## !pip install pandas
## ! pip install PyMySQL
## ! pip install ipython-sql
## ! pip install mysqlclient

# Ejecución del Programa
Uso del Programa
-> Función para agregar un nuevo libro
def agregar_libro(titulo, autor, genero, editorial, anio_publicacion, ISBN, cantidad_disponible):
    cursor = conexion.cursor()
    consulta = "INSERT INTO libros (titulo, autor, genero, editorial, anio_publicacion, ISBN, cantidad_disponible) VALUES (%s, %s, %s, %s, %s, %s, %s)"
    datos = (titulo, autor, genero, editorial, anio_publicacion, ISBN, cantidad_disponible)
    cursor.execute(consulta, datos)
    conexion.commit()
    cursor.close()

-> Función para cerrar la conexión a la base de datos
def cerrar_conexion():
    conexion.close()

-> Ejemplo de uso
if _name_ == "_main_":
    Listar libros disponibles
    print("Libros disponibles:")
    listar_libros()

  -> Agregar un nuevo libro
    nuevo_titulo = "El Gran Gatsby"
    nuevo_autor = "F. Scott Fitzgerald"
    nuevo_genero = "Novela"
    nueva_editorial = "Scribner"
    nuevo_anio_publicacion = 1925
    nuevo_ISBN = "978-3-16-148410-0"
    nueva_cantidad_disponible = 5

    agregar_libro(nuevo_titulo, nuevo_autor, nuevo_genero, nueva_editorial, nuevo_anio_publicacion, nuevo_ISBN, nueva_cantidad_disponible)

  ->  Listar libros después de agregar uno nuevo
    print("\nLibros disponibles después de agregar un nuevo libro:")
    listar_libros()
