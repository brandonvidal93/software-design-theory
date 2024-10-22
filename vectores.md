## Vectores (Arrays)

### ¿Qué es un vector (o arreglo)?
Imagina que tienes una caja grande dividida en varios compartimentos. Cada compartimento puede guardar un juguete o un color. El vector es esa caja. En los compartimentos puedes guardar varios datos, como números, palabras, o lo que quieras, y puedes acceder a cada uno sabiendo su posición.

Por ejemplo:
- Compartimento 0: "Carro"
- Compartimento 1: "Muñeca"
- Compartimento 2: "Pelota"

En programación, un vector es una forma de guardar muchos datos en una sola estructura.

### ¿Cómo se crea o inicializa?
Para crear un vector en JavaScript, usamos corchetes `[]`. Es como crear la caja vacía.

```javascript
let juguetes = []; // Caja vacía

// Caja con información
let juguetes = ["Carro", "Muñeca", "Pelota"];
```

### ¿Cómo se recorre un vector?
Imagina que quieres ver todos los juguetes en la caja, uno por uno. Para hacer eso, usamos un ciclo que nos permite ir a cada compartimento de la caja. Usamos algo llamado `for`.

Ejemplo:

```javascript
let juguetes = ["Carro", "Muñeca", "Pelota"];

for (let i = 0; i < juguetes.length; i++) {
  console.log(juguetes[i]); // Esto imprime cada juguete
}
```

### ¿Cómo se agrega información?

**Usando `push`**

Si tienes un nuevo juguete y lo quieres poner en la caja, puedes usar `push`. Es como abrir la caja y meter un nuevo juguete en el último compartimento.

```javascript
let juguetes = ["Carro", "Muñeca"];
juguetes.push("Pelota"); // Ahora la caja tiene un nuevo juguete
console.log(juguetes); // ["Carro", "Muñeca", "Pelota"]
```

### ¿Cómo se elimina información?

**Usando `pop`**

Si quieres sacar un juguete del final de la caja, puedes usar `pop`. Así sacas el último juguete que metiste.

```javascript
let juguetes = ["Carro", "Muñeca", "Pelota"];
juguetes.pop(); // Saca "Pelota"
console.log(juguetes); // ["Carro", "Muñeca"]
```

**Usando `splice`**

También puedes sacar un juguete de un lugar específico, usando `splice`. Esto es como quitar el juguete de cualquier compartimento que quieras.

```javascript
let juguetes = ["Carro", "Muñeca", "Pelota"];
juguetes.splice(1, 1); // Saca el juguete en la posición 1 ("Muñeca")
console.log(juguetes); // ["Carro", "Pelota"]
```

## ¿Cómo se muestra o imprime la información?

**Usando `console.log`**

Para mostrar lo que hay dentro de la caja, podemos usar `console.log`. Así imprimimos todos los juguetes.

```javascript
let juguetes = ["Carro", "Muñeca", "Pelota"];
console.log(juguetes); // Imprime todo el vector: ["Carro", "Muñeca", "Pelota"]
```

**Usando un ciclo `for`**

Si queremos mostrar los juguetes uno por uno, en lugar de usar solo `console.log(juguetes)`, usamos un ciclo `for` para imprimir cada juguete:

```javascript
let juguetes = ["Carro", "Muñeca", "Pelota"];

// Usamos un ciclo para mostrar cada juguete
for (let i = 0; i < juguetes.length; i++) {
  console.log("Juguete en posición " + i + ": " + juguetes[i]);
}
```