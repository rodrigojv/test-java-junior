# Ejercicio para evaluación de candidatos para Developers Java - Nivel Junior

## Requisitos

* Conocimientos básicos del lenguaje Java
* IDE favorito
* Git
* Muchas ganas y curiosidad 💪

# Descripción de la Evaluación

Se proveen unos ejercicios de distinta dificultad. Leer antentamente lo que se pide en cada ejercicio y empezar por el que sea más sencillo.

# 1. Análisis e Interpretación de Código

Analizar el siguiente bloque de código ¿Es un programa Java válido? ¿Compila? Si es así, indicar el resultado de su ejecución y explicar por qué el resultado es el indicado

```java
    String letra = "6";
    String prefijo = "Iteracion nro ";
    for (int i = 0; i < 10; i++) {
        if (letra == String.valueOf(i)) {
            System.out.println("El bucle continua");
            break;
        } else {
            System.out.println(prefijo + i);
        }
    }
    
  /* 
  
  Es válido ya que la variable prefijo recorrera iniciando en la posicion 0 hasta que sea menor 10 mostrará en consola un mensaje con la posición , una vez dentro del ciclo preguntara si el valor de la variable es igual, devuelve el valor primitivo de un objeto String como un tipo de dato cadena, es decir que imprimirá  un mensaje sino imprimirá las variables con la posición

  */
    
    
    
```

# 2. Modelado OO

Escribir un aplicativo Java que permita administrar un catálogo de automóviles bajo los siguientes requisitos:

Se necesita poder representar automóviles, donde se guardarán las siguientes características por automovil: color, puertas, ruedas, kilometraje, número de chasís, marca.

Los automóviles deben poder simular las operaciones de acelerar, frenar, prenderse y apagarse.

También debe modelarse automóviles especiales tipo deportivos, que compartan todas las características de un automóvil normal, pero además se pueda conocer la cantidad de segundos que le toma llegar de 0 a 100 Km/h.

Se debe poder construir un automóvil pasando de parámetros sus principales características: color, puertas, ruedas, kilometraje, número de chasis, marca.

Una vez modelado el sistema se debe poder interactuar con el aplicativo por línea de comandos y realizar las siguientes operaciones:

* Ofrecer una lista de autos ya precargados, mostrando su marca, color, nro de chasis y si es deportivo
* Permitir de la lista anterior buscar y seleccionar un auto por medio de su nro de chasis
* Permitir conducir el auto seleccionado ofreciendo las operaciones de: acelerar, frenar, prenderse y apagarse.
* Si se acelera un auto deportivo se debe imprimir en consola la cantidad de segundos que le toma llegar de 0 a 100 Km/h

🎁 _Bono:_ se ofrecerá un punto de bono si se lee la lista de autos a partir de un archivo de texto.

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package principal;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.nio.charset.Charset;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.util.Scanner;

/**
 *
 * @author E15Start
 */
public class Principal {

    public static InputStreamReader Leer = new InputStreamReader(System.in);
    public static BufferedReader teclado = new BufferedReader(Leer);

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) throws IOException {
        String entradaTeclado;
        Vehiculo vehiculo = new Vehiculo();
        Vehiculo a = new Vehiculo();

        a.marcas = "Lamborghini";
        a.puerta = "4";
        a.chasis = "231";
        a.color = "verde";
        a.kilometraje = "100";
        a.rueda = "4";

       /* Vehiculo b = new Vehiculo();
        b.marca = "Ferrari";
        b.puerta = "4";
        b.chasis = "321";
        b.color = "azul";
        b.kilometraje = "50";
        b.rueda = "4";*/

        /*Path archivo = Paths.get("C:/PRUEBA/archivo.txt");
         Charset charset = StandardCharsets.UTF_8;

         //Lectura de arhivo
         BufferedReader reader = Files.newBufferedReader(archivo, charset);*/
        Scanner sc = new Scanner(System.in);
        System.out.println("\f");
        System.out.print("Entra matrícula: ");
        entradaTeclado = sc.nextLine();
        vehiculo.setMatricula(entradaTeclado);
        System.out.println("Entra alguna de las siguentes marcas de vechículos: Ford, Toyota, Suzuki, Renault, Seat ");
        entradaTeclado = sc.nextLine();
        int op;
        Vehiculo auto = new Vehiculo();
        System.out.println("VEHICULO");
        System.out.println("1. Arrancar");
        System.out.println("2. Acelerar");
        System.out.println("3. Frenar");
        System.out.println("4. Estacionar");
        System.out.println("5. Salir");

        if (entradaTeclado.equalsIgnoreCase("Ford")) {
            System.out.println("Tenemos un auto de marca " + entradaTeclado + " y nro de cahsis de " + a.chasis);
            System.out.println("Elija una accion");
            
            vehiculo.setMarca(Vehiculo.MarcaDeVehiculo.FORD);
            do {
                op = Integer.parseInt(teclado.readLine());

                switch (op) {
                    case 1:
                        auto.Arranque();
                        break;
                    case 2:
                        auto.Acelerar();
                        break;
                    case 3:
                        auto.Estacionar();
                        break;
                    case 4:
                        auto.Estacionar();
                        break;

                }

            } while (op < 5);

        } else
            if (entradaTeclado.equalsIgnoreCase("Toyota")) {
            vehiculo.setMarca(Vehiculo.MarcaDeVehiculo.TOYOTA);
                        System.out.println("Tenemos un auto de marca " + entradaTeclado + " y nro de cahsis de " + a.chasis);
            System.out.println("Elija una accion");
            
            vehiculo.setMarca(Vehiculo.MarcaDeVehiculo.FORD);
            do {
                op = Integer.parseInt(teclado.readLine());

                switch (op) {
                    case 1:
                        auto.Arranque();
                        break;
                    case 2:
                        auto.Acelerar();
                        break;
                    case 3:
                        auto.Estacionar();
                        break;
                    case 4:
                        auto.Estacionar();
                        break;

                }

            } while (op < 5);
        } else 
                if (entradaTeclado.equalsIgnoreCase("Suzuki")) {
            vehiculo.setMarca(Vehiculo.MarcaDeVehiculo.SUZUKI);
                        System.out.println("Tenemos un auto de marca " + entradaTeclado + " y nro de cahsis de " + a.chasis);
            System.out.println("Elija una accion");
            
            vehiculo.setMarca(Vehiculo.MarcaDeVehiculo.FORD);
            do {
                op = Integer.parseInt(teclado.readLine());

                switch (op) {
                    case 1:
                        auto.Arranque();
                        break;
                    case 2:
                        auto.Acelerar();
                        break;
                    case 3:
                        auto.Estacionar();
                        break;
                    case 4:
                        auto.Estacionar();
                        break;

                }

            } while (op < 5);
        } else if (entradaTeclado.equalsIgnoreCase("Renault")) {
            vehiculo.setMarca(Vehiculo.MarcaDeVehiculo.SUZUKI);
                        System.out.println("Tenemos un auto de marca " + entradaTeclado + " y nro de cahsis de " + a.chasis);
            System.out.println("Elija una accion");
            
            vehiculo.setMarca(Vehiculo.MarcaDeVehiculo.FORD);
            do {
                op = Integer.parseInt(teclado.readLine());

                switch (op) {
                    case 1:
                        auto.Arranque();
                        break;
                    case 2:
                        auto.Acelerar();
                        break;
                    case 3:
                        auto.Estacionar();
                        break;
                    case 4:
                        auto.Estacionar();
                        break;

                }

            } while (op < 5);
        } else if (entradaTeclado.equalsIgnoreCase("Seat")) {
            vehiculo.setMarca(Vehiculo.MarcaDeVehiculo.SEAT);
                        System.out.println("Tenemos un auto de marca " + entradaTeclado + " y nro de cahsis de " + a.chasis);
            System.out.println("Elija una accion");
            
            vehiculo.setMarca(Vehiculo.MarcaDeVehiculo.FORD);
            do {
                op = Integer.parseInt(teclado.readLine());

                switch (op) {
                    case 1:
                        auto.Arranque();
                        break;
                    case 2:
                        auto.Acelerar();
                        break;
                    case 3:
                        auto.Estacionar();
                        break;
                    case 4:
                        auto.Estacionar();
                        break;

                }

            } while (op < 5);
        } else {
            System.out.println("No has elegido ninguna de las marcas enumaradas.");
        }

        // TODO code application logic here
    }

}

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package principal;

/**
 *
 * @author E15Start
 */
public class Vehiculo {
        String marcas; 
    String puerta;//por ejemplo, corolla o vitz
    String rueda;//puede ser auto o camioneta
    String kilometraje;
    String chasis;
    String color;
    /**
     * Clase para crear objetos "Vehiculo" de tipo "enum" con atributos
     * "matricula" y "marca".
     *
     */
    private int velocidad;
    
        public Vehiculo() {
        this.velocidad = 0;
    }

    public int Estacionar() {
        this.velocidad = 0;
        System.out.println("El vehiculo esta estacionado");
        return this.velocidad;
    }
    
    
    public int Arranque() {
        this.velocidad = 10;
        System.out.println("Velocidad:" + this.velocidad);
        return this.velocidad;

    }

    public int Acelerar() {
        this.velocidad = this.velocidad + 10;
        System.out.println("Velocidad:" + this.velocidad);
        return this.velocidad;
    }

    public int Frenar() {
        this.velocidad = 0;
        System.out.println("Velocidad:" + this.velocidad);
        return this.velocidad;
    }


    enum MarcaDeVehiculo {

        FORD, TOYOTA, SUZUKI, RENUALT, SEAT
    };

    private String matricula;
    private MarcaDeVehiculo marca;

    /**
     * Constructor del objeto que define los atributos.
     */
  /*  public Vehiculos () {
        matricula = "";
        marca = null;
    }*/

    /**
     * Mediante un parámetro se establece la matrícula del vehículo
     *
     * @param matricula El valor del parámetro que se introduzca será el valor
     * de la matrícula.
     */
    public void setMatricula(String matricula) {
        this.matricula = matricula;
    }

    /**
     * Mediante un parámetro se establece la matrícula del vehículo
     *
     * @param marca El valor del parámetro que se introduzca será el valor de la
     * marca.
     */
    public void setMarca(MarcaDeVehiculo marca) {
        this.marca = marca;
    }

    /**
     * Método para obtener la matrícula del Objeto
     *
     * @param Devuelve el valor de la matrícula.
     */
    public String getMatricula() {
        return matricula;
    }

    /**
     * Método para obtener la marca del Objeto.
     *
     * @param Devuelve el valor de la marca.
     */
    public MarcaDeVehiculo getMarca() {
        return marca;
    }

}



# 3. Conexión JDBC

Conectarse a una base de datos por JDBC, hacer una consulta mediante un PreparedStatement e imprimir en consola los resultados de la consulta.

El sistema debe modelar y comportarse según las siguientes especificaciones:

1.  Debe permitir ingresar por parámetros de aplicación o por consola el nombre de la columna y el valor a consultar de la columna

2.  Debe ejecutar un query de acuerdo a los datos ingresados en el ítem 1 e impirmir en consola el resultado del query. Los parámetros deben ser usados para armar el query de la siguiente forma:

    `select * from potluck where nombreColumnaParam = valorParam`

    Donde nombreColumnaParam y valorParam son los parámetro del ítem 1.

3.  Se debe utilizar un PreparedStatement para setear el valor usado como filtro del query. No vale concatenar todo en un string.

Se puede utilizar el siguiente script SQL compatible con PostgreSQL para crear la tabla:

```sql
CREATE TABLE potluck
(
    id integer NOT NULL,
    name character varying(20),
    food character varying(30),
    confirmed character(1),
    signup_date date,
    CONSTRAINT potluck_pkey PRIMARY KEY (id )
)
```
package pruebajdbc;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;
import java.util.logging.Level;
import java.util.logging.Logger;

public class Pruebajdbc {

    public static void main(String[] args) {

        String url = "jdbc:postgresql://localhost:5432/prueba";
        String user = "postgres";
        String password = "12345678";

        int id = 3;
        String name = "Yani";
        String food="miel";
        String Cofirmed="1";
        String signup_date="1";
        String sql = "INSERT INTO prueba.potluck("
                + " id,"
                + " name,"
                + " food,"
                + " confirmed,"
                + " signup_date"
                + ") "
                + " VALUES("
                + " ?,"
                + " ?, "
                + " ?,"
                + " ?,"
                + " now()"
                + " )";

        try (Connection con = DriverManager.getConnection(url, user, password);
             PreparedStatement pst = con.prepareStatement(sql)) {
            
            pst.setInt(1, id);
            pst.setString(2, name);
            pst.setString(3, food);
            pst.setString(4, Cofirmed);            
            pst.executeUpdate();
            
            int resultado = pst.executeUpdate();
 

        } catch  (SQLException ex) {
            System.out.println(ex);

            //Logger lgr = Logger.getLogger(JavaPostgreSqlPrepared.class.getName());
           // lgr.log(Level.SEVERE, ex.getMessage(), ex);
        }
    }
}

# Forma de entrega

Se debe hacer un fork de este repositorio, solucionar en ese fork los ejercicios y luego hacer un push a dicho repositorio.

El ejercicio 1 se podría solucionar en un archivo `ejercicio_01.md`.

Finalmente, enviar un email con la URL del repositorio forkeado a la persona que te envió este test.

Muchas gracias y buena suerte! ❤️️
