# Introdução ao JavaScript com Node

## Variáveis

No JavaScript não é uma linguagem fortemente tipada, ou seja, não precisamos especificar o tipo do dado ao declarar uma variável. Nela existe 3 tipos de variáveis, `let`, `var` e `const`.

- let: Cria variável que pode ser alterada e possui limitação de escopo `{}`
- var: Cria variável que pode ser alterada e não possui limitação de escopo
- const: Cria variável que não pode ser alterado após atribuido um valor e possui limitação de escopo `{}`

```javascript
// Diferenciando let, var e const em relação a escopo
if (true) {
  var hello = "hello";
  const hola = "hola";
  let ola = "ola";

  console.log(hello); // saida: hello
  console.log(hola); // saida: hola
  console.log(ola); // saida: ola
}

console.log(hello); // saida: hello
console.log(hola); // erro, variável não declarada
console.log(ola); // erro, variável não declarada
```

```javascript
// Diferenciando let e var de const em relação a atribuição
var num1 = 1;
let num2 = 2;
const num3 = 3;

console.log(num1); // saida: 1
console.log(num2); // saida: 2
console.log(num3); // saida: 3

num1 = 4;
console.log(num1); // saida: 4
num2 = 5;
console.log(num2); // saida: 5
num3 = 6; // Erro: Assignment to constant variable.
console.log(num3); // Erro: Assignment to constant variable
```

```javascript
// Diferenciando let, var e const em relação a funções
// Exemplo 1
var hello = "hello";
const hola = "hola";
let ola = "ola";

console.log(hello); // saida: hello
console.log(hola); // saida: hola
console.log(ola); // saida: ola

function imprimeAi() {
  console.log(hello); // saida: hello
  console.log(hola); // saida: hola
  console.log(ola); // saida: ola
}
imprimeAi();
```

```javascript
// Diferenciando let, var e const em relação a funções
// Exemplo 2
function testandoEscopo() {
  let num1 = 1;
  var num2 = 2;
  const num3 = 3;
  console.log(num1); // saida: 1
  console.log(num2); // saida: 2
  console.log(num3); // saida: 3
}
testandoEscopo();
console.log(num1); // Erro: num1 is not defined
console.log(num2); // Erro: num2 is not defined
console.log(num3); // Erro: num3 is not defined
```
