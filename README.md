# Zoolander - Inventory Management (Java)

## Integrantes
- Dayron Arley Moreno Cifuentes - Dayron-moreno@upc.edu.co
- Jorge Andrés Malaver Pineda - Jorge-malaver@upc.edu.co
- Diego David Montoya Niño  - Diego-montoya1@upc.edu.co

## Resumen
Aplicación Java para gestión de inventarios que implementa patrones creacionales: Abstract Factory, Builder, Factory Method, Prototype y Singleton.

## Cómo ejecutar
1. Importar el proyecto en Visual studio code.
2. Ejecutar `app.Main`.
3. Ejecutar tests con `mvn test` o desde el IDE.

## Enlace del repositorio
(https-github.com-ZoolanderRopa-inventario-app)

## Evidencia
Ejemplo resumido de patrón Prototype
public abstract class Producto implements Cloneable {
    private String nombre;
    private double precio;
    private int stock;

    public Producto(String nombre, double precio, int stock) {
        this.nombre = nombre;
        this.precio = precio;
        this.stock = stock;
    }

    public Producto clonar() {
        try {
            return (Producto) super.clone();
        } catch (CloneNotSupportedException e) {
            throw new RuntimeException("Error al clonar producto", e);
        }
    }
}

// Uso del Singleton para gestión de inventario
public class Inventario {
    private static Inventario instancia;
    private List<Producto> productos = new ArrayList<>();

    private Inventario() {}

    public static Inventario getInstancia() {
        if (instancia == null) {
            instancia = new Inventario();
        }
        return instancia;
    }

    public void agregarProducto(Producto p) {
        productos.add(p);
    }
}
// Ejemplo resumido de patrón Prototype
public abstract class Producto implements Cloneable {
    private String nombre;
    private double precio;
    private int stock;








