import random

def tirarDado():
    return random.randint(1, 6)

def juego():
    alvaro = tirarDado()
    barbara = tirarDado()

    print(f'Álvaro lanzó un dado y sacó: {alvaro}')
    print(f'Bárbara lanzó un dado y sacó: {barbara}')

    if alvaro > barbara:
        print('¡Álvaro Felicitaciones, ganaste!')
    elif alvaro < barbara:
        print('¡Bárbara Felicitaciones, ganaste!')
    else:
        print('¡Es un empate!')

def clasificarGrupo(nombre, sexo):
    if (sexo.lower() == 'f' and nombre.lower() < 'm') or (sexo.lower() == 'm' and nombre.lower() >= 'n'):
        return 'A'
    else:
        return 'B'

def main():
    nombre = input('Ingrese su nombre: ')
    sexo = input('Ingrese su sexo (F/M): ')

    grupo = clasificarGrupo(nombre, sexo)

    print(f'Usted pertenece al Grupo {grupo}.')

def precioEntrada(edad):
    if edad < 4:
        return 0 
    elif 4 <= edad <= 18:
        return 30000 
    else:
        return 50000  

def main():
    try:
        edad = int(input('Ingrese la edad del cliente: '))
        if edad < 0:
            raise ValueError("La edad no puede ser negativa.")
        
        precioEntrada = precioEntrada(edad)

        if precioEntrada == 0:
            print('El cliente puede entrar gratis.')
        else:
            print(f'El precio de la entrada es: {precioEntrada} pesos.')
    
    except ValueError as e:
        print(f'Error: {e}. Ingrese una edad válida.')

def contraseña():
    contrasenaCorrecta = "contraseña123"
    while True:
        contraseñaIngresada = input("Ingrese la contraseña: ")

        if contraseñaIngresada == contrasenaCorrecta:
            print("¡Contraseña correcta! Acceso permitido.")
            break  
        else:
            print("Contraseña incorrecta. Inténtelo nuevamente.")


def valorIva():
    try:
    
        valorFactura = float(input("Ingrese el valor de la factura: "))

      
        iva = 0.21
        valorIva = valorFactura * (1 + iva)

       
        print(f"El valor con IVA (21%) es: {valorIva:.2f}")

    except ValueError:
        print("Error: Por favor, ingrese un valor numérico válido.")


def añadirNumero():
    lista = [1, 2, 3, 4, 5]

    numero = int(input("Ingresa un número: "))

    lista.append(numero)

    print("Lista actualizada:", lista)

def añadirPosicion():
    listado = [1, 2, 3, 4, 5]

    numero = int(input("Ingresa un número: "))
    posicion = int(input("Ingresa la posición donde deseas insertar el número (a partir de 1): "))

    if 1 <= posicion <= len(listado) + 1:
            listado.insert(posicion - 1, numero)
            print("Número agregado correctamente en la posición", posicion)
            print("Lista actualizada:", listado)
    else:
            print("La posición ingresada no es válida para la lista actual.")

def longitudLista():
    numeros = [10, 20, 30, 40, 50]
    longitud = len(numeros)
    print("el total de numeros de la lista es:", longitud)

def eliminarUltimoNumero():
    lista = [1, 2, 3, 4, 5]

    ultimo_numero = lista[-1]
    print("Último número de la lista:", ultimo_numero)

    eliminado = lista.pop()
    print("Número eliminado:", eliminado)
    print("Lista actualizada:", lista)

def eliminarNumero():

    lista = [10, 20, 30, 40, 50]

    print("Lista actual:", lista)
    posicion = int(input("Por favor ingrese la posición del número que deseas eliminar (a partir de 1): "))

    if 1 <= posicion <= len(lista):
        numeroEliminado = lista.pop(posicion - 1)
        print("Número", numeroEliminado, "eliminado de la lista.")
        print("Lista actualizada:", lista)
    else:
        print("La posición ingresada no es válida para la lista actual.")

def contarNumeros():

    lista = [1, 2, 3, 4, 2, 5, 2]

    numeroCont = int(input("Por favor ingrese un número: "))
    apariciones = lista.count(numeroCont)

    print("El número", numeroCont, "aparece", apariciones, "veces en la lista.")

def posicionesNumero():

    lista = [1, 2, 3, 4, 2, 5, 2]

    numeroBusc = int(input("Por favor ingrese un número: "))
    posiciones = []

    for i in range(len(lista)):
        if lista[i] == numeroBusc:
            posiciones.append(i + 1)

    if posiciones:
        print("El número", numeroBusc, "esta en la posición:", posiciones)
    else:
        print("El número", numeroBusc, "no se encuentra en la lista.")

def mostrarNumeros():
    lista = [1, 2, 3, 4, 5]

    print("Números de la lista:", lista)



while True:
    print("\nMenú:")
    print("1. Añadir número a la lista")
    print("2. Añadir número de la lista en una posición")
    print("3. Longitud de la lista")
    print("4. Eliminar el último número")
    print("5. Eliminar un número")
    print("6. Contar números")
    print("7. Posiciones de un número")
    print("8. Mostrar números")
    print("9. Salir")

    opcion = input("Selecciona una opción del menú: ")

    if opcion == "1":
        añadirNumero()
    elif opcion == "2":
        añadirPosicion()
    elif opcion == "3":
        longitudLista()
    elif opcion == "4":
        eliminarUltimoNumero()
    elif opcion == "5":
        eliminarNumero()
    elif opcion == "6":
        contarNumeros()
    elif opcion == "7":
        posicionesNumero()
    elif opcion == "8":
        mostrarNumeros()
    elif opcion == "9":
        print("Saliendo del programa...")
        break
    else:
        print("Opción no válida. Por favor, selecciona una opción del menú.")

def frutas():
    preciosFrutas = {
        "manzana": 2.500,
        "banana": 1.500,
        "naranja": 300,
        "pera": 2.000,
        "uva": 1.500
    }

    def calcularPrecio(fruta, cantidad):
        if fruta in preciosFrutas:
            precioUnit = preciosFrutas[fruta]
            precioFinal = precioUnit * cantidad
            return precioFinal
        else:
            return None

    while True:
   
        fruta = input("Ingrese el nombre de la fruta: ").lower()
        cantidad = int(input("Ingrese la cantidad vendida: "))

   
        precio = calcularPrecio(fruta, cantidad)
        if precio is not None:
            print(f"El precio final de {cantidad} {fruta}(s) es: ${precio:.2f}")
        else:
            print("Lo siento, esa fruta no está en el registro.")

        continuar = input("¿Desea hacer otra consulta? (s/n): ").lower()
        if continuar != 's':
            break

    print("Gracias por usar el programa. ¡Hasta luego!")

def carrito():
    carritoCompra = {}

    while True:
        articulo = input("Por favor ingrese el nombre del artículo o 'fin' para terminar: ")
        if articulo.lower() == 'fin':
            break
        precio = float(input("Ingrese el precio del artículo: "))
        carritoCompra[articulo] = precio

    print("\nLista de la compra:")
    total = 0
    for articulo, precio in carritoCompra.items():
        print(f"{articulo}: ${precio:.2f}")
        total += precio

    print(f"\nCoste total: ${total:.2f}")


def calcularMed(notas):
    return sum(notas) / len(notas)

alumnos = {}
numAlumnos = int(input("Ingrese el número de alumnos: "))

for i in range(numAlumnos):
    nombre = input(f"Ingrese el nombre del alumno {i+1}: ")
    if nombre in alumnos:
        print("Error: ¡El nombre del alumno ya existe!")
        continue
    notas = []
    while True:
        nota = float(input("Ingrese una nota (ingrese un número negativo para finalizar): "))
        if nota < 0:
            break
        notas.append(nota)
    alumnos[nombre] = notas

print("\nLista de alumnos y sus notas medias:")
for nombre, notas in alumnos.items():
    media = calcularMed(notas)
    print(f"{nombre}: Notas = {notas}, Media = {media:.2f}")

def main():
    while True:
        print("\nMenú:")
        print("1. Juego de dados")
        print("2. Clasificar Grupo")
        print("3. Precio de entrada")
        print("4. Contraseña")
        print("5. Valor con IVA")
        print("6. Añadir número a la lista")
        print("7. Añadir número de la lista en una posición")
        print("8. Longitud de la lista")
        print("9. Eliminar el último número")
        print("10. Eliminar un número")
        print("11. Contar números")
        print("12. Posiciones de un número")
        print("13. Mostrar números")
        print("14. Salir")

        opcion = input("Selecciona una opción del menú: ")

        if opcion == "1":
            juego()
        elif opcion == "2":
           clasificarGrupo()
        elif opcion == "3":
            precioEntrada()
        elif opcion == "4":
            contraseña()
        elif opcion == "5":
            valorIva()
        elif opcion == "6":
            añadirNumero()
        elif opcion == "7":
            añadirPosicion()
        elif opcion == "8":
            longitudLista()
        elif opcion == "9":
            eliminarUltimoNumero()
        elif opcion == "10":
            eliminarNumero()
        elif opcion == "11":
            contarNumeros()
        elif opcion == "12":
            posicionesNumero()
        elif opcion == "13":
            mostrarNumeros()
        elif opcion == "14":
            print("Saliendo del programa...")
            break
        else:
            print("Opción no válida. Por favor, selecciona una opción del menú.")

 
