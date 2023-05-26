## ¿Qué son las estructuras de datos?

Son colecciones de valores, las relaciones entre ellos y las funciones u operaciones que se pueden aplicar a los datos. Nos permite ordenar de cierta forma la información mediante un lenguaje de programación.
Nos ayudan a

- Solucionar problemas
- Guardar datos
- Estructurar datos

Las estructuras de datos son aquellas que nos permiten optimizar el espacio y el orden en que almacenamos la información, nos ayudan en problemas específicos y algunos lenguajes tienen estructuras de datos ya definidas por el lenguaje en si mientras en otros lenguajes como JavaScript es necesario definirlas

## Memoria y cómo se guardan los datos

La memoria puede identificarse como un gran arreglo de bits. Recordemos que 1 bit es la unidad básica de información que se puede representar en una computadora, y puede tener los valores 0 o 1.
Todos esos bytes en la memoria tienen asignada una dirección, también conocido como índice correlativo. Es decir, las direcciones de memoria suelen escribirse en notación hexadecimal, que finalmente es un número entero.

## Arrays

Array es una colección de información
Arrays estáticos son aquellos que se quedaran fijos debido a que definimos cuantos espacios tendremos, es decir que le diremos a la maquina cuantos slots deberá usar
Arrays dinámicos son aquellos que podemos mutar

- Los arrays son como una lista con indices numerales consecutivas
- Tambien son conocidas como listas
- Tenemos diferentes métodos construidos por el lenguaje
  - Push ⇒ Agregar un elemento al final del array
  - Pop ⇒ Borra el último elemento
  - Unshift ⇒ Agrega un elemento al inicio del array
  - Shift ⇒ Borra el primer elemento
  - Splice ⇒ Agrega un elemento en una parte del array
- Si nosotros agregamos un elemento al inicio debe haber ciertas operaciones que deben suceder
- Existen dos formas de arrays

  - Estáticos ⇒ Definimos cuantos slots exactamente vamos a usar
  - Dinámicos ⇒ JS Maneja de forma por defecto

    <code>
  class MyArray {
      constructor() {
        this.length = 0;
        this.data = {};
      }
      get(index) {
        return this.data[index];
      }
      push(item) {
        this.data[this.length] = item;
        this.length++;
        return this.data;
      }
      pop() {
        const lastItem = this.data[this.length - 1];
        delete this.data[this.length - 1];
        this.length--;
        return lastItem;
      }
      delete(index) {
        const item = this.data[index];
        this.shiftIndex(index);
        return item;
      }
      shiftIndex(index) {
        for (let i = index; i < this.length - 1; i++) {
          this.data[i] = this.data[i + 1];
        }
        delete this.data[this.length - 1];
        this.length--;
      }
    }
    </code>

## Strings

## Hash Table

## Construyendo una Hash Table

## Implementando el método get

## Linked List

## Construyendo una Singly Linked List

## Agregar nodos a la lista

## Agregar nodos intermedios

## Doubly Linked List

## Stacks

## Construyendo un Stack

## Queues

## Construyendo un Queue

## Trees

## Construyendo un Binary Search Tree

## Graphs

## Representando grafos en código

## Construyendo un grafo
