# Introduccion_EjerciciosPython_SusanaMartin
Ejercicios introducción Python entrega.
#Ejercicio 1: Conversor de Temperatura
#Escribe un programa que convierta una temperatura de grados Celsius a grados Fahrenheit.

# Conversor de Temperatura: Celsius a Fahrenheit
# Solicita al usuario que introduzca la temperatura en Celsius
celsius = float(input("Introduce, por favor,la temperatura en grados Celsius: "))
# Fórmula de conversión
fahrenheit = (celsius * 9/5) + 32
# Muestra el resultado
print(f"{celsius}°C equivalen a {fahrenheit:.2f}°F")

#Ejercicio 2: Calculadora de Propina
#Crea un programa que calcule el monto total a pagar en un restaurante, incluyendo una propina del 15% sobre el total de la cuenta.

# Calculadora de Propina
# Solicita el monto de la cuenta al usuario
cuenta = float(input("Introduce el monto total de la cuenta: €"))
# Calcula la propina del 15%
propina = cuenta * 0.15
# Calcula el monto total con propina
total = cuenta + propina
# Muestra los resultados
print(f"Propina (15%): €{propina:.2f}")
print(f"Total a pagar: €{total:.2f}")

#Ejercicio 3: Verificación de Edad
#Escribe un programa que solicite la edad de un usuario y determine si es mayor de edad (mayor o igual a 18 años) o no

# Verificación de Edad
# Solicita la edad al usuario
edad = int(input("Por favor, introduce tu edad: "))
# Verifica si es mayor o menor de edad
if edad >= 18:
    print("Eres mayor de edad.")
else:
    print("Eres menor de edad.")

#Ejercicio 4: Contador de Vocales
#Crea un programa que cuente el número de vocales en una palabra ingresada por el usuario.

# Contador de vocales en una palabra
# Solicita al usuario que introduzca una palabra
palabra = input("Por favor, introduce una palabra: ").lower()
# Creamos contador de vocales el cual iniciamos en 0
contador_vocales = 0
# Define las vocales (puedes incluir acentos si lo deseas)
vocales = "aeiou"
# Recorre cada letra de la palabra
for letra in palabra:
    if letra in vocales:
        contador_vocales += 1
# Muestra el resultado
print(f"La palabra '{palabra}' contiene {contador_vocales} vocales.")

#Ejercicio 5: Suma de Números Pares
#Escribe un programa que calcule la suma de todos los números pares del 1 al 100.

# Suma de Números Pares del 1 al 100
suma = 0
# Recorre los números del 1 al 100
for numero in range(1, 101):
    if numero % 2 == 0:  # Verifica si es par
        suma += numero
# Muestra el resultado
print(f"La suma de los números pares del 1 al 100 es: {suma}")

# Ejercicio 6: Verificación de Palíndromo
#Crea un programa que verifique si una palabra ingresada por el usuario es un palíndromo (se lee igual de izquierda a derecha que de derecha a izquierda).

# Verificación de Palíndromo

# Solicita la palabra al usuario
palabra = input("Introduce una palabra: ").lower()
# Elimina espacios  
palabra_limpia = palabra.replace(" ", "")
# Compara la palabra con su reverso
if palabra_limpia == palabra_limpia[::-1]:
    print(f"La palabra '{palabra}' es un palíndromo.")
else:
    print(f"La palabra '{palabra}' no es un palíndromo.")

#Ejercicio 7: Calculadora Simple Crea un programa que realice operaciones aritméticas simples (suma, resta,multiplicación, división) según la elección del usuario.

def calculadora():
    print("Calculadora Simple")
    print("Operaciones disponibles:")
    print("1. Suma")
    print("2. Resta")
    print("3. Multiplicación")
    print("4. División")
    opcion = input("Elige una opción (1/2/3/4): ")
    if opcion in ("1", "2", "3", "4"):
        try:
            num1 = float(input("Introduce el primer número: "))
            num2 = float(input("Introduce el segundo número: "))
            if opcion == "1":
                resultado = num1 + num2
                operacion = "+"
            elif opcion == "2":
                resultado = num1 - num2
                operacion = "-"
            elif opcion == "3":
                resultado = num1 * num2
                operacion = "*"
            elif opcion == "4":
                if num2 != 0:
                    resultado = num1 / num2
                    operacion = "/"
                else:
                    print("Error: No se puede dividir entre cero.")
                    return
            print(f"Resultado: {num1} {operacion} {num2} = {resultado}")
        except ValueError:
            print("Por favor, introduce valores numéricos válidos.")
    else:
        print("Opción no válida. Elige entre 1 y 4.")
calculadora()

#Ejercicio 8: Cálculo del Índice de Masa Corporal (IMC)
#Escribe un programa que calcule el Índice de Masa Corporal (IMC) de una persona

def calcular_imc():
    print("Cálculo del Índice de Masa Corporal (IMC)")
    try:
        peso = float(input("Introduce tu peso en kilogramos (kg): "))
        altura = float(input("Introduce tu altura en metros (m): "))
        if peso > 0 and altura > 0:
            imc = peso / (altura ** 2)
            print(f"Tu IMC es: {imc:.2f}")
            # Clasificación según OMS
            if imc < 18.5:
                print("Clasificación: Bajo peso")
            elif imc < 24.9:
                print("Clasificación: Peso normal")
            elif imc < 29.9:
                print("Clasificación: Sobrepeso")
            else:
                print("Clasificación: Obesidad")
        else:
            print("Error: La altura y el peso deben ser mayores que cero.")
    except ValueError:
        print("Por favor, introduce valores numéricos válidos.")
calcular_imc()

#Ejercicio 9: Conversor de Divisas
#Crea un programa que convierta una cantidad de dólares a euros. Suponiendo que 1 dólar es igual a 0.85 euros.

def conversor_divisas():
    print("Conversor de Dólares a Euros")
    try:
        dolares = float(input("Introduce la cantidad en dólares (USD): "))
        tasa_cambio = 0.85
        euros = dolares * tasa_cambio
        print(f"{dolares:.2f} USD equivalen a {euros:.2f} EUR")
    except ValueError:
        print("Por favor, introduce una cantidad válida en números.")
conversor_divisas()

#Ejercicio 10: Determinar el Día de la Semana
#Escribe un programa que determine el día de la semana correspondiente a un número ingresado por el usuario (1 para lunes, 2 para martes, etc.).

def dia_de_la_semana():
    print("Determinar el Día de la Semana")
    try:
        numero = int(input("Introduce un número del 1 al 7: "))
        dias = {
            1: "Lunes",
            2: "Martes",
            3: "Miércoles",
            4: "Jueves",
            5: "Viernes",
            6: "Sábado",
            7: "Domingo"
        }
        if numero in dias:
            print(f"El día correspondiente es: {dias[numero]}")
        else:
            print("Número fuera de rango. Debe ser entre 1 y 7.")
    except ValueError:
        print("Por favor, introduce un número entero válido.")
dia_de_la_semana()

#Ejercicio 11: Calculadora de Edad
#Escribe un programa que solicite al usuario su año de nacimiento y calcule su edad actual.

from datetime import datetime
def calcular_edad():
    print("Calculadora de Edad")
    try:
        año_nacimiento = int(input("Introduce tu año de nacimiento (ej. 2000): "))
        año_actual = datetime.now().year
        edad = año_actual - año_nacimiento
        if edad >= 0:
            print(f"Tienes aproximadamente {edad} años.")
        else:
            print("El año de nacimiento no puede ser mayor al año actual.")
    except ValueError:
        print("Por favor, introduce un año válido en números enteros.")
calcular_edad()

#Ejercicio 12: Calculadora de Área de un Rectángulo
#Crea un programa que calcule el área de un rectángulo. El usuario debe ingresar la longitud y el ancho del rectángulo.

def calcular_area_rectangulo():
    print("Calculadora de Área de un Rectángulo")
    try:
        longitud = float(input("Introduce la longitud del rectángulo (en metros): "))
        ancho = float(input("Introduce el ancho del rectángulo (en metros): "))
        if longitud > 0 and ancho > 0:
            area = longitud * ancho
            print(f"El área del rectángulo es: {area:.2f} metros cuadrados.")
        else:
            print("La longitud y el ancho deben ser valores positivos.")
    except ValueError:
        print("Por favor, introduce valores numéricos válidos.")
calcular_area_rectangulo()

# Ejercicio 13: Verificación de Número Primo
# Escribe un programa que determine si un número ingresado por el usuario es primo o no.

numero = int(input("Introduce un número entero: "))
es_primo = True
if numero <= 1:
    es_primo = False
else:
    for i in range(2, numero):
        if numero % i == 0:
            es_primo = False
            break
if es_primo:
    print(f"{numero} es primo.")
else:
    print(f"{numero} no es primo.")

#Ejercicio 14: Calculadora de Descuento
#Crea un programa que calcule el precio final de un artículo después de aplicar un descuento del 20%

def calcular_descuento():
    print("Calculadora de Descuento (20%)")
    try:
        precio_original = float(input("Introduce el precio original del artículo (en €): "))
        if precio_original > 0:
            descuento = precio_original * 0.20
            precio_final = precio_original - descuento
            print(f"Descuento aplicado: €{descuento:.2f}")
            print(f" Precio final: €{precio_final:.2f}")
        else:
            print("El precio debe ser mayor que cero.")
    except ValueError:
        print("Entrada inválida. Introduce un valor numérico.")
calcular_descuento()


#Ejercicio 15: Conversor de Tiempo
#Escribe un programa que convierta un número de minutos en horas y minutos. Por ejemplo, 145 minutos serían 2 horas y 25 minutos

def convertir_minutos():
    print("Conversor de Tiempo: Minutos a Horas y Minutos")
    try:
        minutos_totales = int(input("Introduce el número de minutos: "))
        if minutos_totales >= 0:
            horas = minutos_totales // 60   # División entera
            minutos = minutos_totales % 60 # Minutos restantes
            print(f"{minutos_totales} minutos son {horas} hora(s) y {minutos} minuto(s).")
        else:
            print("Por favor, introduce un número de minutos positivo.")
    except ValueError:
        print("Entrada inválida. Introduce un número entero.")
convertir_minutos()

#Ejercicio 16: Contador de Números Pares e Impares
#Crea un programa que cuente y muestre la cantidad de números pares e impares en una lista ingresada por el usuario.

def contar_pares_impares():
    print("Contador de Números Pares e Impares")
    try:
        entrada = input("Introduce una lista de números separados por comas (ej. 1,2,3,4): ")
        numeros = [int(x.strip()) for x in entrada.split(",")] #lista separada por comas y sin espacios.
        pares = 0
        impares = 0
        for numero in numeros:
            if numero % 2 == 0:
                pares += 1
            else:
                impares += 1
        print(f"Cantidad de números pares: {pares}")
        print(f"Cantidad de números impares: {impares}")
    except ValueError:
        print("Entrada inválida. Asegúrate de ingresar solo números separados por comas.")
contar_pares_impares()

#Ejercicio 17: Conversor de Millas a Kilómetros
#Escribe un programa que convierta una distancia en millas a kilómetros. Sabiendo que 1 milla equivale a 1.60934 kilómetros

# Conversor de Millas a Kilómetros
# Factor de conversión
FACTOR = 1.60934
# Solicitar al usuario la cantidad en millas
millas = float(input("Introduce la distancia en millas: "))
# Convertir a kilómetros
kilometros = millas * FACTOR
# Mostrar el resultado
print(f"{millas} millas equivalen a {kilometros:.2f} kilómetros.")


#Ejercicio 18: Contador de Palabras
#Crea un programa que cuente la cantidad de palabras en una oración ingresada por el usuario.

# Contador de palabras en una oración
# Solicita al usuario que introduzca una oración
oracion = input("Introduce una oración: ")
# Divide la oración en palabras usando espacios
palabras = oracion.split()
# Cuenta cuántas palabras hay
cantidad = len(palabras)
# Muestra el resultado
print(f"La oración tiene {cantidad} palabras.")

#Ejercicio 19: Verificación de Año Bisiesto
#Escribe un programa que determine si un año ingresado por el usuario es bisiesto o no.

# Verificación de Año Bisiesto
# Solicitar al usuario un año
año = int(input("Introduce un año: "))
# Comprobar si el año es bisiesto
if (año % 4 == 0 and año % 100 != 0) or (año % 400 == 0):
    print(f"{año} es un año bisiesto.")
else:
    print(f"{año} no es un año bisiesto.")

#Ejercicio 20: Suma de Números en una Lista
#Crea un programa que sume todos los números en una lista ingresada por el usuario.    
# Suma de Números en una Lista

# Solicita al usuario los números separados por comas
entrada = input("Ingresa números separados por comas (ej. 1, 2, 3): ")
# Procesa la entrada para convertirla en una lista de enteros
numeros = [int(x.strip()) for x in entrada.split(",")]
# Calcula la suma de los números
suma = sum(numeros)
# Muestra el resultado
print(f"La suma de los números es: {suma}")
