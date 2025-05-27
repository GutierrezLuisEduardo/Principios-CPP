La relación entre clases que supone la herencia de una clase base/madre/superclase a una clase derivada/hija/subclase.

Tipos de herencia:
- Simple: una sola clase base y una sola clase derivada
- Con Constructor: Instanciada la clase base a través de su constructor, desde la subclase.
- Multinivel: Una derivada funge de base para subderivadas
- Múltiple: Una clase hereda de más de una base.
- Con métodos virtuales: para polimorfismo.

Cómo cambia el acceso a miembros heredados según el modificador de acceso usado en la declaración de herencia:
- Con public (Herencia Pública):

| Modificador | Cambios en los miembros heredados respecto a la clase base |
| ----------- | ----------- |
| public | Permanecen public |
| protected | Permanecen protected |
| private | No son accesibles |
  
- Con protected (Herencia Protegida):

| Modificador | Cambios en los miembros heredados respecto a la clase base |
| ----------- | ----------- |
| public | Serán protected |
| protected | Permanecen protected |
| private | No son accesibles |
  
