# python
todo de python
def obtener_temperaturas_diarias():
    """
    Solicita al usuario las temperaturas diarias de la semana.
    Retorna una lista de temperaturas.
    """
    temperaturas = []
    for i in range(7):
        while True:
            try:
                temp = float(input(f"Ingrese la temperatura del día {i+1}: "))
                temperaturas.append(temp)
                break
            except ValueError:
                print("Por favor, ingrese un valor numérico válido.")
    return temperaturas

def calcular_promedio_semanal(temperaturas):
    """
    Calcula el promedio de las temperaturas proporcionadas.
    """
    if not temperaturas:
        return 0  # Evitar división por cero si la lista está vacía
    return sum(temperaturas) / len(temperaturas)

def main_tradicional():
    """
    Función principal para la solución tradicional.
    """
    temperaturas = obtener_temperaturas_diarias()
    promedio = calcular_promedio_semanal(temperaturas)
    print(f"El promedio semanal de temperaturas es: {promedio:.2f}")

if __name__ == "__main__":
    main_tradicional()
Programación Orientada a Objetos (POO)
Python

class ClimaSemanal:
    def __init__(self):
        """
        Inicializa la clase con una lista vacía para almacenar las temperaturas.
        """
        self.temperaturas = []

    def ingresar_temperatura_diaria(self, temperatura):
        """
        Agrega una temperatura a la lista de temperaturas.
        """
        self.temperaturas.append(temperatura)

    def calcular_promedio_semanal(self):
        """
        Calcula el promedio de las temperaturas almacenadas.
        Retorna el promedio o 0 si no hay temperaturas.
        """
        if not self.temperaturas:
            return 0
        return sum(self.temperaturas) / len(self.temperaturas)

    def obtener_y_ingresar_temperaturas(self):
        """
        Solicita al usuario las temperaturas diarias y las almacena en la lista.
        """
        for i in range(7):
            while True:
                try:
                    temp = float(input(f"Ingrese la temperatura del día {i+1}: "))
                    self.ingresar_temperatura_diaria(temp)
                    break
                except ValueError:
                    print("Por favor, ingrese un valor numérico válido.")

def main_poo():
    """
    Función principal para la solución orientada a objetos.
    """
    clima = ClimaSemanal()
    clima.obtener_y_ingresar_temperaturas()
    promedio = clima.calcular_promedio_semanal()
    print(f"El promedio semanal de temperaturas es: {promedio:.2f}")

if __name__ == "__main__":
    main_poo()
