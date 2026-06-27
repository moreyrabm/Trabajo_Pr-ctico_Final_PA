**SISTEMA DE BIBLIOTECA DIGITAL** 

**Integrantes:**  
		**Moreyra Matias**   
		**Pastori P. Santiago**   
 

A lo largo del proyecto de un sistema básico de gestión de biblioteca desarrollado en lenguaje Python utilizando Programación Orientada a Objetos (POO).  Se preserva los datos mediante archivos JSON, herencia, polimorfismo, metaclase, decoradores, composición y agregación.. 

A la vez, el diseño se compone, y actúa, de la siguiente forma: 

* **METACLASE (**MetaRegistro)**:** Hereda de type e intercepta la creación de cada instancia mediante \_\_call\_\_, incrementando el contador global cantidad\_instancias. Esto permite saber cuántos objetos del sistema fueron creados durante la ejecución.  
* **HERENCIA Y POLIMORFISMO:** Entidad es la clase base con el método mostrar(). Libro y Usuario heredan de ella y lo sobreescriben con su propia representación textual, permitiendo iterar sobre una colección mixta y llamar a mostrar() polimórficamente.  
* **RELACIONES:**   
* **Composición**: Prestamo contiene un Libro — no tiene sentido sin él.  
* **Agregación**: Prestamo referencia a un Usuario — el usuario puede existir de forma independiente.  
* Biblioteca gestiona listas de Libro, Usuario y Prestamo.  
* **DECORADOR PROPIO:** registrar(funcion) imprime \[INFO\] Ejecutando: \<nombre\> antes de cada operación. Se aplica a agregar\_libro, agregar\_usuario, eliminar\_libro, eliminar\_usuario, prestar\_libro y devolver\_libro.  
* **TEST:** 


| Test | Qué verifica |
| :---- | :---- |
| test\_crear\_libro | Creación correcta de un libro y sus atributos |
| test\_crear\_usuario | Creación correcta de un usuario y sus atributos |
| test\_agregar\_libro | Alta de libro en la biblioteca |
| test\_agregar\_usuario | Alta de usuario en la biblioteca |
| test\_buscar\_libro | Búsqueda por ISBN |
| test\_buscar\_usuario | Búsqueda por DNI |
| test\_prestar\_libro | Registro de préstamo |
| test\_devolver\_libro | Registro de devolución |
| test\_no\_prestar\_dos\_veces | Validación de préstamo duplicado |
| test\_metaclase | Verificación del contador de instancias |
| test\_polimorfismo | Verificación de que Libro y Usuario tienen mostrar() |
| test\_guardado\_json | Persistencia: datos cargados en nueva instancia de Biblioteca |

Para el desarrollo óptimo del código se recomienda seguir algunos pasos y cumplir los requisitos básicos: 

### **Requisitos**

- Python 3.10 o superior  
- Jupyter Notebook o Google Colab  
- pytest (solo para los tests)

```shell
pip install pytest
```

### **Ejecución del sistema**

Abrir el notebook en Jupyter o Google Colab y ejecutar todas las celdas. El programa inicia con el menú principal:

```
===== BIBLIOTECA DIGITAL =====
1. Agregar libro
2. Listar libros
3. Eliminar libro
4. Agregar usuario
5. Listar usuarios
6. Eliminar usuario
7. Prestar libro
8. Devolver libro
9. Prestamos activos
0. Salir
```

Al iniciarse, el sistema carga automáticamente los datos guardados de sesiones anteriores desde `biblioteca.json`.

### Ejecución de los tests

Exportar el notebook a `.py` y luego:

```shell
python -m pytest biblioteca.py -v
```

O desde el notebook, ejecutar la celda de tests directamente con `ipytest`.

