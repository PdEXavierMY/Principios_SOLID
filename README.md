# Principios_SOLID

Pincha [aquí](https://github.com/Xavitheforce/Principios_SOLID) para dirigirte a mi repositorio.

El ejercicio es el siguiente:

Ejercicio práctico1 (3Puntos): Creación de una clase en Python que representa una matriz.
Para este ejercicio, deberás crear una clase que representa una matriz. Las operaciones que esta clase debe permitir son la creación de una matriz a partir de una lista de listas, la impresión de la matriz en una forma legible, y el cálculo de la transpuesta de la matriz. Asegúrate de que cada método tenga una única responsabilidad.

El ejercicio consta de distintos ficheros que representan las clases del código y un lanzador que se ejecuta en el main para una buena aplicación de los principios SOLID.

El lanzador es:

```py
from matriz import Matriz
from transpuesta import Transpuesta
from imprimir import Imprimir

class Lanzador:
    def __init__(self):
        self.elementos = []
        self.cantidad_filas = int(input("Ingrese la cantidad de filas: "))
        self.cantidad_columnas = int(input("Ingrese la cantidad de columnas: "))
        self.crear_matriz()
        self.matriz = Matriz(self.elementos)
        self.transpuesta = Transpuesta(self.matriz)
        self.imprimir = Imprimir(self.matriz)

    def crear_matriz(self):
        for i in range(self.cantidad_filas):
            fila = []
            for j in range(self.cantidad_columnas):
                fila.append(int(input(f"Ingrese el elemento {i+1},{j+1}: ")))
            self.elementos.append(fila)

    def lanzar(self):
        print("La matriz es: ")
        self.imprimir.imprimir()
        print("La matriz transpuesta es: ")
        transpuesta_result = self.transpuesta.calcular_transpuesta()
        imprimir_transpuesta = Imprimir(transpuesta_result)
        imprimir_transpuesta.imprimir()
```

Y el UML del ejercicio es:

![image](https://github.com/Xavitheforce/Principios_SOLID/assets/91721699/358f058f-2e70-41af-8c39-8d3ef3741a94)
