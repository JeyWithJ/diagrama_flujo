# diagrama_flujo

# Desafío: javaScript

## Nombre de Desafío: diagrama_flujo

## Instrucciones

Determiná que será impreso en la consola, sin ejecutar el código.

> Investiga cuál es la diferencia entre declarar una variable con `var` y directamente asignarle un valor.

```javascript
x = 1;
var a = 5;
var b = 10;
var c = function (a, b, c) {
  var x = 10;
  console.log(x); //10
  console.log(a); //5
  var f = function (a, b, c) { 
    b = a;
    console.log(b); //10
    b = c;
    var x = 5; 
  };
  f(a, b, c);
  console.log(b); //10
};
c(8, 9, 10);
console.log(b); //10
console.log(x); //10
```

```javascript
console.log(bar); //bar
console.log(baz); //baz
foo();
function foo() {
  console.log("Hola!"); //hola
}
var bar = 1;
baz = 2;
```

```javascript
var instructor = "Jhoswe";
if (true) {
  var instructor = "Jose";
}
console.log(instructor); //Jose
```

```javascript
var instructor = "Jhoswe";
console.log(instructor); //Jhoswe
(function () {
  if (true) {
    var instructor = "Jose";
    console.log(instructor); //Jose
  }
})();
console.log(instructor); //Jose
```

```javascript
var instructor = "Jhoswe";
let pm = "Jose";
if (true) {
  var instructor = "The Flash";
  let pm = "Reverse Flash";
  console.log(instructor); //The flash
  console.log(pm); //Reverse flash
}
console.log(instructor); //Jhoswe
console.log(pm); // Jose
```

### Coerción de Datos

¿Cuál crees que será el resultado de la ejecución de estas operaciones?:

```javascript
6 / "3" // error
"2" * "3" //23
4 + 5 + "px" //9px
"$" + 4 + 5 //$9
"4" - 2 //4-2
"4px" - 2 //4px-2
7 / 0 // matherror
{}[0]
parseInt("09") //num 9
5 && 2 //5 2
2 && 5 // 2 5
5 || 0 // 5
0 || 5 // 0
[3]+[3]-[10] //-4
3>2>1
[] == ![]
```

> Si te quedó alguna duda repasá con [este artículo](http://javascript.info/tutorial/object-conversion).

### Hoisting

¿Cuál es el output o salida en consola luego de ejecutar este código? Explicar por qué:

```javascript
function test() {
  console.log(a);
  console.log(foo());

  var a = 1;
  function foo() {
    return 2;
  }
}

test();
```

Y el de este código? :

```javascript
var snack = "Meow Mix";

function getFood(food) {
  if (food) {
    var snack = "Friskies";
    return snack;
  }
  return snack;
}

getFood(false);
```

### This

¿Cuál es el output o salida en consola luego de ejecutar esté código? Explicar por qué:

```javascript
var fullname = "Jhoswe Castro";
var obj = {
  fullname: "Jose Zuñiga",
  fullname: "Jorge Alonso",
  getFullname: function () {
    return this.fullname;
  },
};

console.log(obj.getFullname());

var test = obj.getFullname;

console.log(test());
```

### Event loop

Considerando el siguiente código, ¿Cuál sería el orden en el que se muestra por consola? ¿Por qué?

```javascript
function printing() {
  console.log(1);
  setTimeout(function () {
    console.log(2);
  }, 1000);
  setTimeout(function () {
    console.log(3);
  }, 0);
  console.log(4);
}

printing(); //
```