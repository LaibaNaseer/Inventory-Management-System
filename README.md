# Inventory-Management-System
It's a simple program of python on concept of classes and objects  
class Product:
    def __init__(self, name, description, price, quantity):
        self.name = name
        self.description = description
        self.price = price
        self.quantity = quantity

    def ProductDetails(self):
        return (f"Name: {self.name}\nDescription: {self.description}\nPrice: {self.price}\nQuantity: {self.quantity}\n")


products_list = [("Book", "Fiction novel by a bestselling author", 14.99, 2),
                ("Pen", "Premium ballpoint pen", 2.99, 50),
                ("Notebook", "Spiral-bound notebook with lined pages", 5.99, 30)]


products = []

for product_details in products_list:
    name, description, price, quantity = product_details
    product = Product(name, description, price, quantity)
    products.append(product)


for product in products:
    (product.ProductDetails())



class PerishableProducts(Product):
    def __init__(self, name, description, price, quantity, expiry_date):
        super().__init__(name, description, price, quantity)
        self.expiry_date = expiry_date

    def PerishableProductDetails(self):
        return f"Name: {self.name}\nDescription: {self.description}\nPrice: {self.price}\nQuantity: {self.quantity}\nExpiry Date: {self.expiry_date}\n"


perishable_products_list = [("Milk", "Fresh milk", 2.99, 10, "2023-06-15"),
                            ("Bread", "Whole wheat bread", 1.99, 5, "2023-06-10"),
                            ("Bread", "Whole wheat bread", 1.99, 5, "2023-06-10")]

perishable_products = []

for perishable_product_details in perishable_products_list:
    name, description, price, quantity, expiry_date = perishable_product_details
    perishable_product = PerishableProducts(name, description, price, quantity, expiry_date)
    perishable_products.append(perishable_product)

for perishable_product in perishable_products:
    (perishable_product.PerishableProductDetails())



class NonPerishableProducts(Product):
    def __init__(self, name, description, price, quantity):
        super().__init__(name, description, price, quantity)

    def NonPerishableProductDetails(self):
        return f"Name: {self.name}\nDescription: {self.description}\nPrice: {self.price}\nQuantity: {self.quantity}\n"


non_perishable_products_list = [("Canned Soup", "Assorted canned soups", 2.99, 10),
                                ("Granola Bars", "Healthy snack bars", 1.99, 15),
                                ("Granola Bars", "Healthy snack bars", 1.99, 15)]

non_perishable_products = []

for non_perishable_product_details in non_perishable_products_list:
    name, description, price, quantity = non_perishable_product_details
    non_perishable_product = NonPerishableProducts(name, description, price, quantity)
    non_perishable_products.append(non_perishable_product)

for non_perishable_product in non_perishable_products:
    (non_perishable_product.NonPerishableProductDetails())



class SeasonalEdibleProducts(Product):
    def __init__(self, name, description, price, quantity, season):
        super().__init__(name, description, price, quantity)
        self.season = season

    def SeasonalEdibleProductDetails(self):
        return f"Name: {self.name}\nDescription: {self.description}\nPrice: {self.price}\nQuantity: {self.quantity}\nSeason: {self.season}\n"


seasonal_edible_products_list = [("Pumpkin Pie", "Delicious pumpkin pie", 9.99, 5, "Autumn"),
                                 ("Candy Canes", "Peppermint-flavored candy canes", 0.99, 20, "Winter"),
                                 ("Watermelon", "Sweet and juicy watermelon", 4.99, 8, "Summer")]

seasonal_edible_products = []

for seasonal_edible_product_details in seasonal_edible_products_list:
    name, description, price, quantity, season = seasonal_edible_product_details
    seasonal_edible_product = SeasonalEdibleProducts(name, description, price, quantity, season)
    seasonal_edible_products.append(seasonal_edible_product)

for seasonal_edible_product in seasonal_edible_products:
    (seasonal_edible_product.SeasonalEdibleProductDetails())




class Supplier:
    def __init__(self, name,description, address, contact_info):
        self.name = name
        self.description = description
        self.address = address
        self.contact_info = contact_info

    def Supplier_info(self):
        return (f"Name: {self.name}\nDEscription: {self.description}\nAddress: {self.address}\nContact info: {self.contact_info}\n")


suppliers_list = [("Qasim","Supplier for Perishable Products", "Green Town Phase 1", "0000-00000000000"),
                  ("Aleena","Supplier for Non Perishable Products", "Johar Town Phase 2", "1111-111111111111"),
                  ("Kawish","Supplier for seasonal Products" ,"Glass Valley Phase 3", "2222-2222222222")]

suppliers = []

for supplier_details in suppliers_list:
    name,description, address, contact_info = supplier_details
    supplier = Supplier(name,description, address, contact_info)
    suppliers.append(supplier)

for supplier in suppliers:
    (supplier.Supplier_info())




print("Inventory Management System")
print("      1.Products Details")
print("      2.Perishable Products")
print("      3.Non Perishable Products")
print("      4.Seasonal Products")
print("      5.Suppliers Details")

option = int(input("Enter your Choice:"))

while option != 0:
    if option == 1:
        for product in products:
            print(product.ProductDetails())
        break
    elif option == 2:
        for perishable_product in perishable_products:
            print(perishable_product.PerishableProductDetails())
        break
    elif option == 3:
        for non_perishable_product in non_perishable_products:
            print(non_perishable_product.NonPerishableProductDetails())
        break
    elif option == 4:
        for seasonal_edible_product in seasonal_edible_products:
            print(seasonal_edible_product.SeasonalEdibleProductDetails())
        break
    elif option == 5:
        for supplier in suppliers:
            print(supplier.Supplier_info())
        break
    else:
        print("Invalid Option")
        break
