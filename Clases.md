---
tags: []
created: '2024-11-11'
title: 'Clases'
---
## Clase
> Una estructura **blueprint/modelo/plantilla** que modela las propiedades y el comportamiento de un objeto.

```cpp
class product{
    private:
    // Attributes
    public:
    // Methods
};
```
Las clases son estructuras contenedoras de atributos **(también llamados propiedades, variables de instancia)** y métodos (**también llamados funciones de instancia, comportamientos**) que poseeran los objetos **(instancias/implementaciones de esa clase)** derivados.

### Uso de la POO de manera estratégica
- <details markdown='1'><summary>Determinar si es necesario el uso de objetos para resolver un problema:</summary>
  
  - ¿Hay **entidades relevantes** participando del problema? (_**Determinando clases**_)
  - Para cada entidad identificada, ¿Qué **propiedades** de esta entidad son **relevantes**? (_**Determinando atributos**_)
  - Para cada entidad identificada, ¿Qué **acciones** debería realizar? (**_Determinando métodos_**)
  
  Finalmente plasmar una solución al problema que comprenda la dinámica entre las distintas clases.
</details>

- <details markdown='1'><summary>Generalización y especialización</summary>

**Generalización**: el uso de clases **(superclases)** que contengan las propiedades y comportamientos que **heredaran** sus **subclases**, evitando así reescribir código (y complicarlo) de manera innecesaria.

  **Especialización**: Uso de subclases para crear **objetos especializados** que además de contener las propiedades y comportamientos provistos por la superclase, incluirán **otras propiedades y comportamientos** que les convierten en un objeto **singular**.
</details>


- <details markdown='1'><summary>Revisar y Refinar</summary>

  Nunca esta demás revisar que el diseño de tus objetos y clases sea el óptimo. **Evita la redundancia entre clases** (Principio de Responsabilidad Única). Queremos el mejor código para mantenerlo de manera fácil en el futuro.
</details>

### Atributos

Representan las propiedades del objeto a modelar y son accesibles por cualquier método de la misma clase. Cualquier subclase los heredará: que el atributo sea **heredable** significa que cualquier subclase contendrá por defecto los mismos atributos que la superclase.
```cpp
int num = 1; // tipo nombre = dato;
```
Se colocan bajo el modificador de acceso deseado (suele ser private) y como cualquier variable pueden ser inicializados ahí mismo, aunque generalmente suele hacerse desde algún constructor.

### Methods
> Funciones de instancia
They can recibe values, use them in operations, and/or return them just like any function, with the difference that methods have access to any attribute contained within the same class.

```cpp
// Dentro de un apartado de métodos en la clase
int getNum() {
    return num
};

void setNum(int x) {
    num = x;
};
```
### Constructor
> Generador de un objeto (aquello que te permite hacer uso de tu clase para crear instancias).

Un tipo especial de método incluido en la clase para inicializar los atributos de futuros objetos y así configurar el estado inicial de futuros objetos. Durante su declaración no se especifica un tipo de dato (ni siquiera void), comparte nombre con la clase de manera que se invoque automáticamente al instanciarla, puede haber más de un constructor (sobrecarga de constructores) con distintas listas de parámetros para manejar la creación del objeto de distintas maneras. El constructor por defecto especifica cómo debe construirse el objeto sin el paso previo de parámetros; El constructor de copia recibe un objeto del mismo tipo y crea uno idéntico.

```cpp
class product{
    private:
    // Attributes
    int num;
    public:
    // Methods
    product():num(0) {}; // Constructor por defecto
    product(int x):num(x) {};
    product(const product& original):num(original.getNum()); // Constructor copia

    int getNum() {
        return num
    };
    
    void setNum(int x) {
        num = x;
    };
};
```

### Objetos
Entidad concreta que se crea a partir de estructura y comportamientos de la clase. Si hay un constructor dentro de su clase, los atributos del objeto podrán ser inicializados con mediante este, proporcionándole argumentos.

<details markdown='1'><summary>Inicializar atributos para un objeto</summary>

En clases como esta:

```
class Perro{
    private:
        string nombre;
        int edad;
        double peso;
    public:
        void alimentar(int cantidad_alimento){};
        Perro(string n, int e, double p) : nombre(n), edad(e), peso(p) {};
        //Un constructor puede tener valores por defecto
        Perro(string n=,"Unknown" int e=0, double p=0.0 : nombre(n), edad(e), peso(p) {};
};
```
Maneras de inicializar atributos de nuestros objetos:
- Usando su constructor:
  
  `Perro miPerro("Terry", 4, 36.9)`
- Directamente desde su declaración en la clase:
  ```
  class Perro{
      nombre="Unknown";
      edad=0;
      peso=0.0;
  }
  ```
- Asignar los valores manualmente:
  ```
    Perro miPerro;
    miPerro.nombre="Terry";
    miPerro.edad=4;
    miPerro.peso=36.9
  ```
</details>

### Dibujando diagramas de clase (UML)
A una clase se le representa con una tabla cuyo header será el nombre de la clase misma.

Orden de agrupamiento: 
- Atributos en la parte superior
- Métodos (incluye constructores) en la parte inferior

Criterios de agrupamiento:
- Previo a cada propiedad/comportamiento, un signo que representa su tipo de acceso [revisar modificadores de acceso](https://github.com/A01707310/PrincipiosDeCpp/blob/main/Pilares%20de%20POO.md#encapsulaci%C3%B3n): 

  - '-' para _private_
  - '+' para _public_
  - '#' para _protected_

- Añadir luego de ':' el tipo de dato contenido/retornado para el atributo/propiedad, respectivamente.

<details markdown='1'><summary>Ejemplo de clase en forma de código y de diagrama</summary>

```
class Perro{
    private:
        string nombre;
        int edad;
        double peso;
    public:
        void alimentar(int cantidad_alimento){};
};
```
|Perro|
|:--
|-----------------Atributos------------------|
|- nombre : string|
|- edad : int|
|- peso : double|
|- cantidad_alimento : int|
|-----------------Métodos------------------|
|+ alimentar(cantidad_alimento : int) : void|

</details>


<details markdown='1'><summary>Representando interrelaciones dentro del diagrama</summary>
  
  - Asociación: línea sólida. Indica que hay relación entre los objetos de dos clases.
  - Agregación: línea sólida con rombo abierto (pegado a la clase receptora). Representa dentro de una clase, el recibir un objeto previamente construido (y por tanto independiente) a esta.
  - Composición: línea sólida con rombo cerrado (pegado a la clase contenedora). Representa objetos contenidos dentro de objetos contenedores (lo contenido no puede existir sin su contenedor).
  - Herencia: línea sólida con triángulo hueco (el triángulo pegado a la superclase). Representa clases que heredan propiedades y métodos de otra (una superclase).
  - Realización: línea discontinua con triángulo hueco.
  - Línea discontinua con flecha: Dependencia (una clase depende de otra clase, indicando que un cambio en una puede afectar a la otra)
</details

LINK A UN VIDEO SOBRE DIAGRAMAS UML: https://www.youtube.com/watch?v=6XrL5jXmTwM
