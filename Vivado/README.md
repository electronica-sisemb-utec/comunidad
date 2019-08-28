# Vivado Design Suite

Guía básica para desarrollar un proyecto en Vivado. Para ver la instalación, haz click [aquí](http://www.google.com/).

## Flujo de Trabajo

Para este ejercicio, se utilizará una compuerta lógica AND con la herramienta de Vivado y un FPGA Basys3.

### Inicialización
Primero, se debe crear un proyecto RTL en una ubicación específica. Luego, se configura el setup del FPGA objetivo con los siguientes datos:

```
Family: Artix7
Package: CPG236
Speed: -1 
```

### Diseño
Se empieza a crear un módulo de diseño.

```
1. Create New Source
2. VHDL Module
```
Una vez creado el módulo de diseño, la herramienta debería generar un código inicial como se muestra en la Figura 1.

A continuación se declaran las variables de entrada y salida y se realiza la operación lógica AND como se muestra a continuación:

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity AND_gate is
    Port(
        A, B: in std_logic;
        C: out 
    );
end AND_gate;

architecture Behavioral of AND_Gate is

begin

C <= A and B;

end Behavioral;
```

Finalmente se selecciona `Synthesize - XST`. En la consola no debería aparecer ningún error. El esquemático RTL se encuentra en `RTL ANALYSIS` y el esquemático tecnológico se encuentra en `SYNTHESIS`.

### Simulación

Es necesario crear un Módulo de Test Bench.

```
1. Create New Source
2. VHDL Test Bench
```

El Test Bench no necesita declaración de variables y la entidad tiene que estar vacía. Para realizar la simulación, se abarcan tres etapas:

* Declaración de componente:

En esta sección se declara el componente con sus respectivas entradas y salidas.

* Declaración de señales:

El diseño solo es un "cascarón" para realizar el test, por lo que se deben crear señales para las entradas y salidas.

* Instanciación:

En este apartado se instancia el componente y se asignan las señales correspondientes. El orden de asignación es importante. `A_tb => A` no sería correcto.

* Proceso de Simulación:

Se crea un proceso en el que se le asignan valores a las variables de entrada por un determinado tiempo (usualmente de 10 a 100 ns).


```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity AND_gate_tb is
    Port(
        A, B: in std_logic;
        C: out 
    );
end AND_gate_tb;

architecture Behavioral of AND_gate_tb is

-- Instanciación del componente (Parte 1)
component AND_gate
    Port (
        A,B: in std_logic;
        C: out std_logic
    );
end component;

-- Declaración de señales
signal A_tb : std_logic := '0';
signal B_tb : std_logic := '0';
signal C_tb : std_logic := '0';

begin

-- Instanciación del componente (Parte 2)
uut: AND_gate port map (
    A => A_tb,
    B => B_tb,
    C => C_tb
);

-- Proceso de Simulación
Simulacion : process
begin

    wait for 10 ns;
    A_tb <= '0';
    B_tb <= '0';
    
    wait for 10 ns;
    A_tb <= '1';
    B_tb <= '0';
    
    wait for 10 ns;
    A_tb <= '0';
    B_tb <= '1';
    
    wait for 10 ns;
    A_tb <= '1';
    B_tb <= '1';

    wait;
end process;
end Behavioral;
```
Finalmente, para realizar la simulación se selecciona `Simulate Behavioral`.


## Autores

* **Jhonatan Macazana** - *Vivado* - [jhonatanmacazana](https://github.com/jhonatanmacazana)



## Reconocimientos

* [Nelson Soberón](https://www.google.com/) por la estructura de la documentación.
