# Function-Types

En TypeScript, los Function Types se utilizan para describir la forma y la estructura de una función, incluyendo los tipos de sus parámetros y el tipo de retorno. Esto proporciona un mecanismo para verificar estáticamente que las funciones se utilizan de acuerdo con su firma definida.

Existen diferentes formas de definir Function Types en TypeScript:

1. Sintaxis básica:
   ```typescript
   let myFunction: (param1: type1, param2: type2, ...) => returnType;
   ```

   Donde `myFunction` es el nombre del tipo de función que estás definiendo. `param1`, `param2`, etc., son los nombres de los parámetros de la función, y `type1`, `type2`, etc., son los tipos correspondientes de esos parámetros. `returnType` es el tipo de retorno de la función.

   Ejemplo:
   ```typescript
   let sum: (a: number, b: number) => number;
   sum = (x, y) => x + y;

   let result: number = sum(2, 3);  // Output: 5
   ```

   En este ejemplo, se define `sum` como un Function Type que toma dos parámetros de tipo `number` y devuelve un valor de tipo `number`. Luego, se asigna una función de suma a `sum` y se llama a esa función para obtener el resultado.

2. Uso de interfaces:
   También puedes utilizar interfaces para definir Function Types en TypeScript. Esto proporciona una forma más modular y reutilizable de definir tipos de funciones.

   ```typescript
   interface MyFunction {
     (param1: type1, param2: type2, ...): returnType;
   }
   ```

   Ejemplo:
   ```typescript
   interface MathOperation {
     (a: number, b: number): number;
   }

   let sum: MathOperation = (x, y) => x + y;
   let multiply: MathOperation = (x, y) => x * y;

   let result1: number = sum(2, 3);       // Output: 5
   let result2: number = multiply(2, 3);  // Output: 6
   ```

   Aquí, se define la interfaz `MathOperation` que describe la estructura de una función que toma dos parámetros de tipo `number` y devuelve un valor de tipo `number`. Luego, se declaran las variables `sum` y `multiply` como tipos `MathOperation` y se les asignan las funciones correspondientes.

Los Function Types en TypeScript son muy útiles en escenarios donde se necesita proporcionar o recibir funciones como argumentos en otras funciones, como en los casos de callbacks, promesas, manipulación de arrays, entre otros.
