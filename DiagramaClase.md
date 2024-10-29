## **SISTEMA DE CARRITO DE COMPRAS** ##
--------------------------------------
#### **Integrante** ####
- Maria Sofia Aljure Herrera
---------------------------------------
### **Descripción General** ###
Para este proyecto, se desarrollara una base de datos para un sistema de carrito de compras que integre funcionalidades tanto para administradores como para compradores. 

---------------------------------------
### **Estructura Base De Datos** ###
#### **Entidades Principales** ####
1. ### **Ususario** ###
#### **Descripción:** #### 
Almacena información básica de los usuarios, como su rol, nombre e información.
- ### **Atributos** ###
   - nombre
   - apellido
   - email
   - contraseña 
2. ### **Producto** ###
#### **Descripción:** ####  
Contiene detalles de cada producto disponible, como nombre, precio y stock.
- ### **Atributos** ###
    - dProducto
    - nombrePoducto
    - precioProducto
    - stock 
3. ### **Inventario** ###
#### **Descripción:** #### 
Relaciona los productos con la cantidad disponible en stock.
- ### **Atributos** ###
   - idIventario
   - cantidadDisponible
   - actualizarStock
   -  Producto[] productos
   4. ### **Detalle Factura** ###
  #### **Descripción:** ####
Asocia cada producto adquirido en una compra específica, permitiendo un desglose detallado.
- ### **Atributos** ###
   - iddetalleFactura
   - cantidad
   - precioUnitario
   - Producto
   5. ### **Factura** ###
   #### **Descripción:** ####
Registra las compras de los usuarios, incluyendo la fecha y el total.
- ### **Atributos** ###
   - idFactura
   - fecha
   - total
   - calcularTotal
   -------------------------------
   ## **DIAGRAMA DE CLASE (FORMATO WSD)** ##
   -------------------------------------
   ```js
   @startuml Diagrama de clase

   class Usuario{
    nombre: String
    apellido: String
    email: String
    contrasenia : String
    }
    class Inventario{
    idIventario: int 
    Producto[] productos
    cantidadDisponible: int
    actualizarStock()
    }

    class Inventario{
    idIventario: int 
    Producto[] productos
    cantidadDisponible: int
    actualizarStock()
    }

    class DetalleFactura{
    iddetalleFactura : int
    cantidad : int 
    precioUnitario: float 
    Producto : producto
    }

    class Factura{
    idFactura : int 
    fecha: date 
    total : float
    calcularTotal()
    }

    Usuario "1" --> "0..*" Factura
    Factura "1" --> "1..*" DetalleFactura
    DetalleFactura "1" --> "1" Producto
    Inventario  "1" --> "1" Producto
    @enduml
   ```
![Diagrama de Clase](image.png)