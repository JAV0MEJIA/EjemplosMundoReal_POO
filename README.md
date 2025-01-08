# EjemplosMundoReal_POO
EjemplosMundoReal_POO
# Simulador de Reservas Hotel
class Hotel:
    def __init__(self, nombre, direccion, num_habitaciones):
        self.nombre = nombre
        self.direccion = direccion
        self.num_habitaciones = num_habitaciones
        self.habitaciones = []

    def agregar_habitacion(self, numero, tipo, precio):
        self.habitaciones.append(Habitacion(numero, tipo, precio))

    def mostrar_habitaciones(self):
        for habitacion in self.habitaciones:
            print(f"Número: {habitacion.numero}, Tipo: {habitacion.tipo}, Precio: {habitacion.precio}")

# Definición de la clase Habitacion
class Habitacion:
    def __init__(self, numero, tipo, precio):
        self.numero = numero
        self.tipo = tipo
        self.precio = precio
        self.reservada = False

    def reservar(self):
        if not self.reservada:
            self.reservada = True
            print(f"Habitación {self.numero} reservada con éxito.")
        else:
            print(f"Habitación {self.numero} ya está reservada.")

# Definición de la clase Reserva
class Reserva:
    def __init__(self, hotel, habitacion, fecha_entrada, fecha_salida):
        self.hotel = hotel
        self.habitacion = habitacion
        self.fecha_entrada = fecha_entrada
        self.fecha_salida = fecha_salida

    def mostrar_reserva(self):
        print(f"Hotel: {self.hotel.nombre}")
        print(f"Habitación: {self.habitacion.numero}")
        print(f"Fecha de entrada: {self.fecha_entrada}")
        print(f"Fecha de salida: {self.fecha_salida}")

# Creación de un hotel
hotel = Hotel("QUITO CALLES  GONZALES SUAREZ Y GUAPULO", "", 10)

# Agregar habitaciones al hotel
hotel.agregar_habitacion(1, "Simple", 100)
hotel.agregar_habitacion(2, "Doble", 200)
hotel.agregar_habitacion(3, "Suite", 500)

# Mostrar habitaciones del hotel
print("Habitaciones del hotel:")
hotel.mostrar_habitaciones()

# Reservar una habitación
habitacion = hotel.habitaciones[0]
habitacion.reservar()

# Crear una reserva
reserva = Reserva(hotel, habitacion, "2024-01-01", "2024-01-03")

# Mostrar la reserva
print("\nReserva:")
reserva.mostrar_reserva()

