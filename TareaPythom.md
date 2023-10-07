# Pythom 
# ejercicio1

#Algoritmo para calcular el subsidio familiar dependiendo la cantidad de hijos
def calcularSubsidio(hijos, edad_escolar, viuda):
    subsidio_base = 0
    
    if hijos <= 2:
        subsidio_base = 70
    elif hijos <= 5:
        subsidio_base = 90
    else:
        subsidio_base = 120
    
    subsidio_edad_escolar = 0
    if 6 <= edad_escolar <= 18:
        subsidio_edad_escolar = 10 * (edad_escolar - 5)
    
    subsidio_viuda = 20 if viuda else 0
    subsidio_total = subsidio_base + subsidio_edad_escolar + subsidio_viuda
    
    return subsidio_total

# ejercicio2

#Calculos de vectores
import random

def llenar_vector_aleatorio(longitud):
    return [random.randint(1, 100) for _ in range(longitud)]

def verificar_escenario(vector_a, vector_b):
    suma_a = sum(vector_a)
    suma_b = sum(vector_b)

    if suma_a == suma_b:
        return "Vectores iguales."
    elif suma_a < suma_b:
        return "El vector A es menor que el vector B."
    else:
        return "El vector B es menor que el vector A."

longitud = int(input("Ingrese la longitud : "))
vector_a = llenar_vector_aleatorio(longitud)
vector_b = llenar_vector_aleatorio(longitud)

print("Vector A:", vector_a)
print("Vector B:", vector_b)

resultado = verificar_escenario(vector_a, vector_b)
print(resultado)

# ejercicio 3

#algoritmo definir rango
def calcularRango(datos):
    if len(datos) == 0:
        return 0  # Si no hay datos, el rango es 0

    maximo = max(datos)
    minimo = min(datos)
    rango = maximo - minimo
    return rango

# Solicitar al usuario la cantidad de datos
n = int(input("Ingrese los datos: "))

# Solicitar al usuario ingresar los datos uno por uno
datos = []
for i in range(n):
    dato = float(input(f"Ingrese el dato {i + 1}: "))
    datos.append(dato)
    
# ejercicio 4

# algoritmo calculo de cuadro
def dibujarCuadrado(lado):
    if lado <= 0:
        print("El lado del cuadrado tiene ser mayor a 0.")
        return

    for i in range(lado):
        if i == 0 or i == lado - 1:
            print("* " * lado)
        else:
            print("* " + "  " * (lado - 2) + "*")