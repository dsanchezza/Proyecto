
# Proyecto final POO
Construir una aplicación que emule una un sistema de gestión de inventario para una bodega.

Integrantes:
- Danna Gabriela Sánchez Zambrano
- Samuel Nicolás Garzón Gomez
- David Steven Torres Garzón

Este proyecto consiste en desarrollar una aplicación quue permita gestionar el inventario en bodega de una empresa de partes de autos, este mismo contiene diferentes archivos .py en los cuales se definen diferentes funcionalidades, integrando una interfaz gráfica, una base de datos SQLite y exportación de reportes en PDF con gráficas incluidas.

Este sistema de inventario permite:
- Registrar productos con diferentes atributos
- Consultar, editar y almacenar el inventario en una base de datos SQLite
- Filtrar las ventas en rangos de fecha
- Generar comprobantes en PDF incluyendo sus respectivos gráficos de ventas
- Hacer un ranking de los productos con mayor y menor stock
- Interactuar por medio de una interfaz gráfica hecha con tkinter


Antes de iniciar con la visualización del proyecto y la explicación de este mismo, es importante tener los requerimientos instalados, por lo cual, en la terminal de Windows se utilizará este comando para verificar que todo esté correctamente instalado:

```python
python --version
pip --version
```


<img width="1191" height="134" alt="Captura de pantalla 2025-07-20 230414" src="https://github.com/user-attachments/assets/ae645f88-1b62-48db-a213-7fdf9cb9059d" />


Si está correctamente instalado, ambos comandos devolverán la versión, así podemos continuar al siguiente paso

En este proyecto se hace uso de un entorno virtual, al crear la carpeta es importante que esto sea lo primero que se haga puesto que las dependencias del proyecto se instalarán en el entorno virtual, el cual se puede crear con el siguiente comando en la terminal:

```python
python -m venv venv
#Aún falta activar el entorno virtual para que empiece a funcionar, este se activará usando el siguiente comando
venv\Scripts\activate
```

Puesto que en este proyecto se hace uso de diferentes librerías externas, también se instalarán en la terminal usando el siguiente comando

```python
pip install pandas openpyxl matplotlib
```

Sin embargo, aún falta una librería, la cual para instalarse es necesario crear una cuenta en la página web de esta misma
- Link para registrarse (es importante consultar su nombre de usuario antes de continuar ya que este se pide durante la instalación) https://www.reportlab.com/accounts/register/

Finalmente, para la instalación de este programa se utilizará el siguiente comando en la terminal

```python
pip install rlextra -i https://www.reportlab.com/pypi/
```

Se solicitará el nombre de usuario y la contraseña que se introdujo cuando se creó la cuenta, posteriormente iniciará la descarga

# Diagrama de clases
<img width="1329" height="3840" alt="Mermaid_Chart_-_Create_complex_visual_diagrams_with_text _A_smarter_way_of_creating_diagrams -2025-07-20-171544" src="https://github.com/user-attachments/assets/7d83d3de-85d4-4e4d-9a86-eaba15801c0a" />


# Definición y explicación de código

En nuestro archivo `clases.py` se encuentra toda la información de las clases del sistema de inventario

**Clase proveedor**

```python
class Proveedor:
    def __init__(self, id: int, nombre, telefono: int, direccion, email):
        self.id = id
        self.nombre = nombre
        self.telefono = telefono
        self.direccion = direccion
        self.email = email

    def informacion_proveedor(self):
        return f"{self.nombre} ({self.telefono})"
```
La clase proveedor guarda información tal como ID, nombre del proveedor, teléfono, dirección y correo electronico, adicionalmente, tiene un metodo `informacion_proveedor` el cual retirna el nombre y teléfono del proveedor.

**Clase producto**
```python
class Producto:
    def __init__(self, id: int, nombre, descripcion, marca, modelo, proveedor: Proveedor, fecha_compra: datetime, cantidad, precio_unitario):
        self.id = id
        self.nombre = nombre
        self.descripcion = descripcion
        self.marca = marca
        self.modelo = modelo
        self.proveedor = proveedor
        self.fecha_compra = fecha_compra
        self.cantidad = cantidad
        self.precio_unitario = precio_unitario

    def sumar_stock(self, cantidad):
        self.cantidad += cantidad

    def reducir_stock(self, cantidad):
        if self.cantidad < cantidad:
            return
        self.cantidad -= cantidad

    def informacion_producto(self):
        return f"{self.nombre} - {self.marca} {self.modelo} ({self.cantidad} unidades)"
```
