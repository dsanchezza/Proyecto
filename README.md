
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
