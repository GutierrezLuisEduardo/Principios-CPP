> La capacidad de un método de comportarse de manera diferente variando entre clases relacionadas por la herencia (polimorfismo de inclusión, a través de la sobreescritura/overriding), o variando dentro de una misma clase entre los distintos argumentos que recibe (polimorfismo Ad-hoc, a través de la sobrecarga/overloading).

Sobrecarga de métodos:
Permite definir múltiples métodos con el mismo nombre pero con diferentes parámetros (diferente número o tipo de argumentos).

Sobreescritura de métodos:
Permite que una clase derivada proporcione una implementación específica de un método que ya está definido en su clase base. Se utiliza la palabra virtual (indica que puede sobreescribirse) en el método de la clase base y se utiliza override (indica que se sobreescribe) en el método correspondiente de la clase derivada. 

Ejemplo de sobreescritura:
```cpp
class Animal{
public:
void Ladrar() {
  std::cout << "Woof!";}
};

class Perro: public Animal{
public:

};
```

Ejemplo de sobrecarga:
```cpp
class Animal{
public:
void Ladrar() {
  std::cout << "Woof!";}
};

class Perro: public Animal{
public:

};
```
