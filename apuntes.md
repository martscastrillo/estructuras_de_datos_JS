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

## Construyendo nuestro array

```javascript
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
```

## Strings

String inmutables se refiere a que una vez definido no lo podemos cambiar.

- De por si no es una estructura de datos, pero la forma en la que se guarda en memoria es como una estructura de datos
- Tenemos un string en una variable

```javascript
const saludo = "Hola";
```

- Cabe recalcar que en muchos lenguajes incluyendo JavaScript, los strings son inmutables
  - para generar un cambio en el string sera necesario:
  1. Tomar todos los datos de los memory slots
  2. Buscar nuevos memory slots
  3. Pegar en los memory slots necesarios con los nuevos elementos
  - Hacer todos estos pasos puede llegar a ser un problema generando un problema de computo
  - Cuando generamos strings con JavaScript casi nunca tenemos modificarlos
- Los strings se guardan como un arreglo

RESUMEN: Los strings son inmutables es decir que una vez definidos no podemos cambiar “letra por letra” si no que tendremos que tomar todos los items y comenzar a realizar la operación deseada también significa mayor esfuerzo de computo

## Hash Table

Hash function es poder asegurar generar un hash que se convierte en el address para acceder al valor.

- En JavaScript se pueden conocer como objetos o Maps [Aun les falta unos pasos para concretarlo]
- En otros lenguajes como python son conocidos como Diccionarios [Python], Maps [Java, Go], Hashes [Ruby]

Hash Tables vs Objetos

- Las hash tables son similares a los objetos porque tienen el concepto de guardar valores key, value
- La diferencia es que tienen un paso extra que se convierte en caja negra la cual es una hash function
- Funciona de una manera similar a los arreglos debido a que accedemos a través de un numero

Métodos

- Insert ⇒ Insertar un elemento en la tabla
- Search ⇒ Buscar un elemento por key
- Delete ⇒ Borrar un elemento

Colisión de Hash Table

- En ocasiones podemos pasar un key distintito puede generar el mismo hash
- Colisionando con el anterior
- Esto podrá depender de la cantidad de espacio disponible

RESUMEN: Las hash tables se parecen a los objetos porque podemos guardar valores por llave, valor. Pero su principal diferencia es que genera un hash para cada llave valor. El único problema es que se puede generar un mismo hash colisionando con el anterior

## Construyendo una Hash Table

```javascript
class HashTable {
	constructor(size) {
		this.data = new Array(size);
	}
	hashMethod(key) {
		let hash = 0;
		for (let i = 0; i < key.length; i++) {
			hash = (hash + key.charCodeAt(i) * i) % this.data.length;
		}
		return hash;
	}
	set(key, value) {
		const address = this.hashMethod(key);
		if (!this.data[address]) {
			this.data[address] = [];
		}
		this.data[address].push([key, value]);
		return this.data;
	}
}

const myHashTable = new HashTable(50);
```

## Implementando el método Get

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
