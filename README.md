# pit
projeto para estacionamento.
class ParkingLot:  
    def _init_(self, capacity):  
        self.capacity = capacity  
        self.vehicles = {}  

    def park_vehicle(self, plate_number):  
        if len(self.vehicles) < self.capacity:  
            self.vehicles[plate_number] = True  
            print(f"Veículo {plate_number} estacionado.")  
        else:  
            print("Estacionamento cheio! Não é possível estacionar mais veículos.")  

    def remove_vehicle(self, plate_number):  
        if plate_number in self.vehicles:  
            del self.vehicles[plate_number]  
            print(f"Veículo {plate_number} removido.")  
        else:  
            print(f"Veículo {plate_number} não encontrado.")  

    def available_spaces(self):  
        return self.capacity - len(self.vehicles)  

    def display_vehicles(self):  
        if self.vehicles:  
            print("Veículos estacionados:")  
            for plate in self.vehicles.keys():  
                print(plate)  
        else:  
            print("Nenhum veículo estacionado.")  


if _name_ == "_main_":  
    parking_lot = ParkingLot(capacity=5)  

    parking_lot.park_vehicle("ABC1234")  
    parking_lot.park_vehicle("XYZ5678")  
    
    print(f"Espaços disponíveis: {parking_lot.available_spaces()}")  

    parking_lot.display_vehicles()  

    parking_lot.remove_vehicle("ABC1234")  
    print(f"Espaços disponíveis: {parking_lot.available_spaces()}")  

    parking_lot.display_vehicles()
