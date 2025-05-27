La capacidad de un método de comportarse de manera diferente variando entre clases relacionadas por la herencia (polimorfismo de inclusión, a través de la sobreescritura/overriding), o variando dentro de una misma clase entre los distintos argumentos que recibe (polimorfismo Ad-hoc, a través de la sobrecarga/overloading).

Sobrecarga de métodos:

<details markdown='1'><Summary></Summary>
</details>

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
