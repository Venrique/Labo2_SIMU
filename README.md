# Laboratorio 2
Técnicas de Simulación en Computadoras: Segunda práctica de laboratorio

## Contenido
En esta práctica trabajaremos con los siguientes temas:

- Punteros
- Enumeraciones
- Clases

### El problem.msh

```cpp
0.5 5 5   // representa L K y Q
10 9 1 1  // representa el numero de: nodos, elementos, condiciones de Dir y condiciones de Newm


Coordinates
1	0.1
2	0.6
3	1.1
4	1.6
5	2.1
6	2.6
7	3.1
8	3.6
9	4.1
10	4.6
EndCoordinates

Elements
1 1 2
2 2 3
3 3 4
4 4 5
5 5 6
6 6 7
7 7 8
8 8 9
9 9 10
EndElements

Dirichlet
1	15
EndDirichlet

Neumann
10	8
EndNeumann

```
### El classes.h

### Enum

```cpp

//Se crean cuatro enumeraciones que serviran para dar mayor legibilidad al codigo

enum lines {NOLINE,SINGLELINE,DOUBLELINE};
enum modes {NOMODE,INT_FLOAT,INT_INT_INT};
//Ya no necesitamos tener la longitud
enum parameters {THERMAL_CONDUCTIVITY,HEAT_SOURCE};
enum sizes {NODES,ELEMENTS,DIRICHLET,NEUMANN};

```

### Clase Abstracta: Item

```cpp
//Clase abstracta que representa un objeto en la malla

class item{

    protected:
        int id; //identificador
        float x; //coordenada en X (basta con este dato por estar en 1 dimension)
        int node1; //identificador de nodo
        int node2; //segundo identificador de nodo
        float value; //valor asociado al objeto
        
    public:
        //Getters para los atributos
        int getId() {
            return id;
        }

        float getX() {
            return x;
        }

        int getNode1() {
            return node1;
        }

        int getNode2() {
            return node2;
        }

        float getValue() {
            return value;
        }
        
        //Metodos abstractos para instanciar los atributos de acuerdo a las necesidades

        //Caso en que se utiliza un entero y un real
        virtual void setIntFloat(int n,float r)=0;

        //Caso en que se utilizan tres enteros
        virtual void setIntIntInt(int n1,int n2,int n3)=0;

};

```

<hr>
<p align="center">Para servirles, <strong>Equipo de Instructores</strong> </p>
