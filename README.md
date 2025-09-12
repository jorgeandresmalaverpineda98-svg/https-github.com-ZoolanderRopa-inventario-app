# 🧵 Zoolander Ropa – Sistema de Inventario con Patrones Creacionales

## Integrantes
- Dayron Arley Moreno Cifuentes - Dayron-moreno@upc.edu.co
- Jorge Andrés Malaver Pineda - Jorge-malaver@upc.edu.co
- Diego David Montoya Niño  - Diego-montoya1@upc.edu.co

Este proyecto corresponde a la actividad **(Proyecto Transversal / Fase I)** de la asignatura *Fundamentos de Ingeniería y Sistemas Informáticos*.  
Se desarrolla una aplicación en **Java** para la gestión de inventarios de la empresa **Zoolander Ropa**, aplicando patrones creacionales de diseño.

---

## 🚀 Funcionalidades
- Crear **categorías de ropa** (Camisas, Pantalones, Zapatos, Accesorios).
- Definir **atributos específicos** de cada categoría (ej: talla, material, color).
- Crear **productos de ropa** dentro de categorías.
- **Clonar productos** para agilizar la creación de nuevas prendas.
- Consultar y actualizar el **inventario** (entradas y salidas de stock).
- Gestión centralizada con un **Singleton** para el inventario.

---

## 📌 Patrones Creacionales Implementados
- **Abstract Factory** → creación de categorías y productos de ropa.  
- **Builder** → construcción paso a paso de productos con atributos de moda.  
- **Factory Method** → creación de productos por tipo (camisa, pantalón, zapato).  
- **Prototype** → clonación de productos ya existentes.  
- **Singleton** → una única instancia del inventario de Zoolander Ropa.  

---

## 🛠️ Tecnologías
- Lenguaje: **Java**
- Dependencias: **Visual Studio Code** 
- Control de versiones:  **Git & GitHub**  

---

## 📂 Estructura del Proyecto


## Evidencia
1. Creación del Repositorio
Se creó un repositorio en GitHub con el nombre asignado al proyecto. En este paso se inicializó con un archivo README.md para establecer la base del repositorio.
<img width="900" height="273" alt="image" src="https://github.com/user-attachments/assets/2091e66b-d3e1-42fa-901f-a9030120cfbe" />
2. Configuración Local
Cada integrante clonó el repositorio y configuró su nombre y correo electrónico para que los commits queden asociados a cada colaborador.
<img width="985" height="213" alt="image" src="https://github.com/user-attachments/assets/a1edabe6-d740-4066-833f-7d0f779fe12f" />
3. Commits Individuales
Cada integrante realizó un commit con la implementación de un patrón creacional específico en un archivo distinto. De esta manera, se evidencia la contribución individual de cada miembro.
<img width="534" height="320" alt="image" src="https://github.com/user-attachments/assets/e742c5fa-10aa-4db0-8112-b7882c58e68e" />
4. Commits Colaborativos
Se creó una rama secundaria para realizar modificaciones conjuntas en el archivo README.md. Posteriormente, se abrió un Pull Request que fue revisado y aprobado por otro integrante del equipo, para luego ser integrado a la rama principal. 
<img width="770" height="337" alt="image" src="https://github.com/user-attachments/assets/2734ba56-c377-4ab7-b09d-858bb63f60d3" />
Ejemplo de Clase ProductoRopa.java
package productos;

import patrones.prototype.PrototipoProducto;


public class ProductoRopa implements PrototipoProducto {
    private String nombre;
    private double precio;
    private int cantidad;
    private String talla;
    private String material;
    private String color;

    public ProductoRopa(String nombre, double precio, int cantidad, String talla, String material, String color) {
        this.nombre = nombre;
        this.precio = precio;
        this.cantidad = cantidad;
        this.talla = talla;
        this.material = material;
        this.color = color;
    }

    @Override
    public ProductoRopa clonar() {
        return new ProductoRopa(nombre, precio, cantidad, talla, material, color);
    }

    @Override
    public String toString() {
        return "Producto Ropa: " + nombre + " | Talla: " + talla + " | Color: " + color +
               " | Material: " + material + " | Precio: $" + precio + " | Cantidad: " + cantidad;
    }

    
 
    Ejemplo de Singleton Inventario.java
}

package inventario;

import java.util.HashMap;
import java.util.Map;
import productos.ProductoRopa;

public class Inventario {
    private static Inventario instancia;
    private Map<String, ProductoRopa> productos;

    private Inventario() {
        productos = new HashMap<>();
    }

    public static Inventario getInstancia() {
        if (instancia == null) {
            instancia = new Inventario();
        }
        return instancia;
    }

    public void agregarProducto(ProductoRopa producto) {
        productos.put(producto.toString(), producto);
    }

    public void mostrarInventario() {
        productos.values().forEach(System.out::println);
    }
}







