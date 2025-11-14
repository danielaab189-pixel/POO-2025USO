class Motor:
    def __init__(self, tipo, potencia):
        self._tipo = tipo
        self._potencia = potencia

    @property
    def tipo(self):
        return self._tipo

    @tipo.setter
    def tipo(self, value):
        self._tipo = value

    @property
    def potencia(self):
        return self._potencia

    @potencia.setter
    def potencia(self, value):
        self._potencia = value

    def encender_motor(self):
        print(f"El motor {self._tipo} de {self._potencia} HP se ha encendido.")

    def detener_motor(self):
        print(f"El motor {self._tipo} de {self._potencia} HP se ha detenido.")

    def __str__(self):
        return f"Motor: Tipo={self._tipo}, Potencia={self._potencia} HP"


class Vehiculo:
    def __init__(self, marca, modelo, anio):
        self._marca = marca
        self._modelo = modelo
        self._anio = anio

    @property
    def marca(self):
        return self._marca

    @marca.setter
    def marca(self, value):
        self._marca = value

    @property
    def modelo(self):
        return self._modelo

    @modelo.setter
    def modelo(self, value):
        self._modelo = value

    @property
    def anio(self):
        return self._anio

    @anio.setter
    def anio(self, value):
        self._anio = value

    def encender(self):
        print(f"El vehiculo {self._marca} {self._modelo} se ha encendido.")

    def apagar(self):
        print(f"El vehiculo {self._marca} {self._modelo} se ha apagado.")

    def __str__(self):
        return f"Vehiculo: Marca={self._marca}, Modelo={self._modelo}, Anio={self._anio}"


class Automovil(Vehiculo):
    def __init__(self, marca, modelo, anio, numero_puertas, motor):
        super().__init__(marca, modelo, anio)
        self._numero_puertas = numero_puertas
        self.motor = motor

    @property
    def numero_puertas(self):
        return self._numero_puertas

    @numero_puertas.setter
    def numero_puertas(self, value):
        self._numero_puertas = value

    def abrir_maletero(self):
        print(f"El maletero del automovil {self._marca} {self._modelo} se ha abierto.")

    def tocar_claxon(self):
        print(f"El claxon del automovil {self._marca} {self._modelo} ha sonado.")

    def __str__(self):
        return f"{super().__str__()}, Numero de Puertas={self._numero_puertas}\n{self.motor}"


class Motocicleta(Vehiculo):
    def __init__(self, marca, modelo, anio, cilindraje, motor):
        super().__init__(marca, modelo, anio)
        self._cilindraje = cilindraje
        self.motor = motor

    @property
    def cilindraje(self):
        return self._cilindraje

    @cilindraje.setter
    def cilindraje(self, value):
        self._cilindraje = value

    def hacer_caballito(self):
        print(f"La motocicleta {self._marca} {self._modelo} esta haciendo un caballito.")

    def usar_patada_arranque(self):
        print(f"La motocicleta {self._marca} {self._modelo} ha usado el patada de arranque.")

    def __str__(self):
        return f"{super().__str__()}, Cilindraje={self._cilindraje} cc\n{self.motor}"


if __name__ == "__main__":
    motor1 = Motor("Gasolina", 150)
    motor2 = Motor("Electrico", 100)
    motor3 = Motor("Gasolina", 200)
    motor4 = Motor("Diesel", 120)

    auto1 = Automovil("Toyota", "Corolla", 2020, 4, motor1)
    auto2 = Automovil("Honda", "Civic", 2019, 4, motor2)

    moto1 = Motocicleta("Yamaha", "MT-07", 2021, 689, motor3)
    moto2 = Motocicleta("Kawasaki", "Ninja", 2022, 650, motor4)

    print("=== Demostracion de Automoviles ===")
    auto1.encender()
    auto1.motor.encender_motor()
    auto1.abrir_maletero()
    auto1.tocar_claxon()
    auto1.motor.detener_motor()
    auto1.apagar()

    print("\n=== Demostracion de Motocicletas ===")
    moto1.encender()
    moto1.motor.encender_motor()
    moto1.hacer_caballito()
    moto1.usar_patada_arranque()
    moto1.motor.detener_motor()
    moto1.apagar()

    print("\n=== Informacion de Vehiculos ===")
    print(auto1)
    print()
    print(auto2)
    print()
    print(moto1)
    print()
    print(moto2)
