# proyectodef login():
    usuarios = {
        "frank": "202212419",
        "cherman": "202211951",
        "juan": "123",
        "mariano": "1234",
        "royer": "12345",
        "migel": "123456"
    }

    while True:
        username = input("Ingrese su nombre de usuario: ")
        password = input("Ingrese su contraseña: ")

        # Verificación de las credenciales
        if username in usuarios and usuarios[username] == password:
            print("Inicio de sesión exitoso.")
            return True
        else:
            print("Nombre de usuario o contraseña incorrectos. Inténtelo nuevamente.")

# Ejecutar el programa
if login():
    """SISTEMA DE VENTAS DE PRODUCTOS"""
    #SISTEMA DE VENTASfrank

    productos = {
        "001": {"nombre": "Arroz", "precio":  2.5},
        "002": {"nombre": "Leche", "precio":  3.0},
        "003": {"nombre": "Azúcar", "precio": 2.0},
        "004": {"nombre": "Aceite", "precio": 5.0},
        "005": {"nombre": "Sal", "precio": 1.0}
    }

    tasa_igv = 0.18

    def mostrar_productos():
        print("Productos disponibles:")
        for codigo, producto in productos.items():
            print(f"Código: {codigo}, Nombre: {producto['nombre']}, Precio: ${producto['precio']}")

    def calcular_igv(subtotal):
        return subtotal * tasa_igv / 100

    def realizar_venta():
        codigo = input("Ingrese el código del producto: ")
        if codigo in productos:
            producto = productos[codigo]
            print(f"Producto: {producto['nombre']}, Precio: ${producto['precio']}")
            cantidad = int(input("Ingrese la cantidad a comprar: "))
            subtotal = cantidad * producto['precio']
            igv = calcular_igv(subtotal)
            total = subtotal + igv
            print(f"Subtotal: ${subtotal}")
            print(f"IGV ({tasa_igv}%): ${igv}")
            print(f"Total a pagar: ${total}")
            confirmacion = input("¿Desea realizar la compra? (s/n): ")
            if confirmacion.lower() == "s":
                print("Venta realizada exitosamente.")
            else:
                print("Venta cancelada.")
        else:
            print("Producto no encontrado.")

    def main():
        print("Bienvenido al sistema de ventas")
        while True:
            print("\n1. Mostrar productos disponibles")
            print("2. Realizar una venta")
            print("3. Salir")
            opcion = int(input("Seleccione una opción: "))
            if opcion == 1:
                mostrar_productos()
            elif opcion == 2:
                realizar_venta()
            elif opcion == 3:
                print("Gracias por utilizar el sistema de ventas.")
                break
            else:
                print("Opción inválida. Por favor, seleccione nuevamente.")

    if __name__ == '__main__':
        main()
