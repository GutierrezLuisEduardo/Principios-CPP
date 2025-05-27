La capacidad de un método de comportarse de manera diferente variando entre clases relacionadas por la herencia (polimorfismo de inclusión), que le contienen o variando entre los distintos argumentos que recibe (polimorfismo Ad-hoc). Esto puede llevarse a cabo a través de la **sobrecarga** y la **sobreescritura**

Ejemplo:
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
