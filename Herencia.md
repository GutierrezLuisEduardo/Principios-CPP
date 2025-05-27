La relación entre clases que supone la herencia de una clase base/madre/superclase a una clase derivada/hija/subclase.

Tipos de herencia:
- Simple: una sola clase base y una sola clase derivada
- Con Constructor: Instanciada la clase base a través de su constructor, desde la subclase.
- Multinivel: Una derivada funge de base para subderivadas
- Múltiple: Una clase hereda de más de una base.
- Con métodos virtuales: para polimorfismo.

Cómo cambia el acceso a miembros heredados según el modificador de acceso usado en la declaración de herencia:
- Con public:

| Modificador | Cambios en sus miembros |
| ----------- | ----------- |
| public | Permanecen public |
| protected | Permancen protected |
| private | No son accesibles desde la clase derivada |
  
