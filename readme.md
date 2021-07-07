# Introdução ao JavaScript com Node

## Variáveis

No JavaScript não é uma linguagem fortemente tipada, ou seja, não precisamos especificar o tipo do dado ao declarar uma variável. Nela existe 3 tipos de variáveis, `let`, `var` e `const`.

- let: Cria variável que pode ser alterada e possui limitação de escopo `{}`
- var: Cria variável que pode ser alterada e não possui limitação de escopo
- const: Cria variável que não pode ser alterado após atribuido um valor e possui limitação de escopo `{}`

```js
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

```js
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

```js
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

```js
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

## Tipo de dados

No JS existem duas categorias de dados, os primitivos e os não primitivos. Os primitivos são `number`, `string`, `null`, `undefined` e `boolean` e os não primitivos são `object` e `array`. Existem outros tipos de dados, esses são os mais basicos e utilizados.

Para descobrir o tipo de dado que a variável pertence é necessario usar o `typeof`

### Null e Undefined

```js
var variavel = null;
var variavel2 = undefined;

console.log(variavel);
console.log(typeof variavel); // object?
console.log(typeof {}); // null equivale a {} no JS
console.log(variavel2);
console.log(typeof variavel2);
```

### Number

```js
var num1 = 1; // Inteiro
var num2 = 2.5; // Float
var num3 = 060; // Octal - 48
var num4 = 0o33; // Octal na versão ES6 - 27
var num5 = 0xff; // Hexadecimal - 255
var num6 = 1.17e2; // 1,17 x 100 notação para numeros grandes
var num7 = Infinity; // Infinito

console.log(num1);
console.log(typeof num1);
console.log(num2);
console.log(typeof num2);
console.log(num3);
console.log(typeof num3);
console.log(num4);
console.log(typeof num4);
console.log(num5);
console.log(typeof num5);
console.log(num6);
console.log(typeof num6);
console.log(num7);
console.log(typeof num7);

console.log(Number.MAX_VALUE); // 1.7976931348623157e+308
console.log(typeof Number.MAX_VALUE);
console.log(Number.MIN_VALUE); // 5e-324
console.log(typeof Number.MIN_VALUE);
console.log("a" / 2); // NaN - Not a Number
console.log(typeof ("a" / 2));
console.log(NaN / 2); // NaN - Not a Number
console.log(typeof NaN);
```

### String

```js
// Declaração
var hello = "Hello";
var ola = "Ola";
var hola = `Hola`;

var helloWorld = "Hello 'World'";
var helloWorld2 = 'Hello "World"';
var helloWorld3 = `'Hello' "World"`;

console.log(hello);
console.log(ola);
console.log(hola);
console.log(helloWorld);
console.log(helloWorld2);
console.log(helloWorld3);
```

```js
// Concatenação 1
var hello = "Hello";
var world = 'World';
var helloWorld = hello + world;

console.log(hello);
console.log(world);
console.log(helloWorld);
```

```js
// Concatenação 2
var hello = "Hello";
var world = 'World';
var helloWorld = `${hello} ${world}`;

console.log(hello);
console.log(world);
console.log(helloWorld);
```

```js
// Plus
var nome = "Ricardinho";
console.log("Nome:", nome);
console.log("Tamanho:", nome.length);
console.log("Primeira letra:", nome[0]);
console.log("UpperCase:", nome.toUpperCase());
console.log("LowerCase:", nome.toLowerCase());
console.log("Corta o ricardinho:", nome.slice(0, 3));
console.log("Mostra dinho:", nome.slice(5));
console.log("Remove divide onde tem i:", nome.split("i"));
console.log("Troca i por a:", nome.replace(/i/g, "a"));

var num = 123;
console.log(num);
console.log(num.toString());

var espacos = "   Pra que tanto espaço antes e depois?    ";
console.log(espacos);
console.log(espacos.trim());
```

### Boolean

```js
var ehVerdade = true;
var ehFalso = false;

console.log(ehVerdade);
console.log(typeof ehVerdade);
console.log(ehFalso);
console.log(typeof ehFalso);
```

### Array

No JS é possivel criar uma lista com diversos dados.

```js
var numeros = [1, 2, 3, 4, 5, 6, 7];
var alunos = ["Ricardo", "Luiz", "Ana", "Marcelo"];
var notas = [8, 7.4, 5.3, 6.7];
// JS não tem lista com tipo de dado prédefinido
var lista_aleatoria = ["Banana", 23.43, numeros, "Cuscuz", null, undefined];

console.log(numeros);
console.log(alunos);
console.log(notas);
console.log(lista_aleatoria);
```

```js
var alunos = ["Ricardo", "Luiz", "Ana", "Marcelo", "Maria"];

console.log(alunos);
console.log(alunos.length);
console.log(alunos[0]);
console.log(alunos[6]);
// Pega parte do array
// Retorna um novo array
console.log(alunos.slice(0, 2));
console.log(alunos.slice(2));

// Adiciona no final do array um ou varios valores
// Retorna o novo comprimento do array
let novoComprimento = alunos.push("Roberto", "Luana");

console.log(alunos);
console.log(novoComprimento);

// Remove o ultimo elemento do array
// Retorna o elemento eliminado
let elementoEliminado = alunos.pop();

console.log(alunos);
console.log(elementoEliminado);

// Remove o primeiro elemento do array
// Retorna o elemento eliminado
let elementoEliminado2 = alunos.shift();

console.log(alunos);
console.log(elementoEliminado2);

// Adiciona um ou mais elementos do inicio do array
// Retorna o novo comprimento do array
let novoComprimento2 = alunos.unshift("Ricardo");

console.log(alunos);
console.log(novoComprimento2);


// Adiciona um separador entre os valores do array
// Retorna o novo comprimento do array
let novoArray = alunos.join(" - ");

console.log(alunos);
console.log(novoArray);

// Busca por um valor no array
// Retorna a posição do elemento ou -1
let posicao = alunos.indexOf("Roberto");

console.log(alunos);
console.log(posicao);

posicao = alunos.indexOf("Luan");
console.log(posicao);

// Busca por um valor no array mas começa do final pro inicio
// Retorna a posição do elemento ou -1
let posicao2 = alunos.lastIndexOf("Roberto");

console.log(alunos);
console.log(posicao2);

// Verifica se o valor está presente no array ou não
// Retorna true se presente e false se não
let ehIncluso = alunos.includes("Maria");

console.log(alunos);
console.log(ehIncluso);

// ============================
// PLUS
alunos.map((value, index, array) => {
  console.log(`Posição ${index}: aluno ${value}`);
  // console.log(array);
});


// Retorna o valor que satisfaz a condição
// Recebe o valor, posição e o array em cada interação
var buscaAluno = alunos.find((value) => value === "Ana");
console.log("Aluno:", buscaAluno);
var buscaAluno2 = alunos.find((value) => value === "Felipe");
console.log("Aluno:", buscaAluno2);

// Retorna a posição do valor que satisfaz a condição
// Recebe o valor, posição e o array em cada interação
var buscaPosicao = alunos.findIndex((value) => value === "Ana");
console.log("Posição:", buscaPosicao);
var buscaPosicao2 = alunos.findIndex((value) => value === "Felipe");
console.log("Posição:", buscaPosicao2);

// Retorna a posição do valor que satisfaz a condição
// Recebe o valor, posição e o array em cada interação
var filtrarPorM = alunos.filter((value) => {
  if (value[0] === "M") return true;
  return false;
});
console.log(filtrarPorM);
```

### Object (Objetos literais)

```js
var aluno = {
  nome: "Luiz",
  turma: "tn10",
  idade: 21,
  media: 7.4,
};

console.log(aluno);
console.log(aluno.nome);
console.log(aluno.turma);
console.log(aluno.idade);
console.log(aluno.media);

aluno.nome = "Carlos";
console.log(aluno);
console.log(aluno.nome);

delete aluno.media;
console.log(aluno);
```

```js
var aluno = {
  nome: "Roger",
  sobrenome: "Souza",
  idade: 29,
  apresentacao: function () {
    return `Oi, sou o ${this.nome} ${this.sobrenome}, tenho ${this.idade} anos`;
  },
};

console.log(aluno);
console.log(aluno.apresentacao());
```

```js
// Plus
var alunos = [
  {
    nome: "Luiz",
    turma: "tn10",
    idade: 21,
    media: 7.4,
  },
  {
    nome: "Ricardo",
    turma: "tn11",
    idade: 26,
    media: 9.4,
  },
  {
    nome: "Luana",
    turma: "tn13",
    idade: 19,
    media: 8.2,
  },
];

console.log(alunos);
console.log(alunos[1]);
console.log(alunos[1].nome);

const buscarAluno = alunos.find(value=>value.nome==="Luana")
const buscarAlunoPosicao = alunos.findIndex(value=>value.nome==="Luana")
console.log(buscarAluno);
console.log(buscarAlunoPosicao);
```

Além dos objetos literais existe os objetos JSON que servem para comunicação web

```js
var objetoLiteral = {
  id: 1,
  nome: "Joaquin",
  idade: 18,
};

var objetoJson = `{"id":1,"nome":"Joaquin","idade":18}`;

var converteJsonParaObjetoLiteral = JSON.parse(objetoJson);
var converteObjetoLiteralParaJson = JSON.stringify(objetoLiteral);
console.log(objetoLiteral);
console.log(objetoJson);
console.log(converteJsonParaObjetoLiteral);
console.log(converteObjetoLiteralParaJson);


// ! Fazer foreach e reducer
```

### Desafios

- Crie um array com um valor:
  - inteiro (number)
  - float (number)
  - boolean
  - string
  - array
  - objeto
- Crie um objeto para um produto. Nele deve possuir:
  - id (inteiro)
  - nome (inteiro)
  - preço (float)
  - descrição (string)
  - quantidade (inteiro)
- Crie um array com os produtos de uma loja. Esse array deve possui 5 produtos com a estrutura acima
- Insira um valor no final do array acima
- Insira um valor no inicio do array acima
- Remova o primeiro valor e o último
<!-- - (PLUS) Busque no array acima o produto com id 3 e imprima no terminal o nome e o preço dele
- Encontre a posição do array acima
- Mapeie todos os produtos da loja e imprima a seguinte frase para cada um deles: `O "nome do produto" custa "preço do produto" e temos nos estoque o total de "quantidade em estoque". Descrição: "Descrição do produto"` -->

## Condicionais

```js
let nome = "Ana";

if (nome === "Ana") {
  console.log("Nome coincide");
}
if (nome === "Luiz") {
  console.log("Nome não coincide");
}

if (nome === "Ana") {
  console.log("Nome coincide");
} else {
  console.log("Nome não coincide");
}

if (nome === "Ana") {
  console.log("Nome igual a Ana");
} else if (nome === "Luiz") {
  console.log("Nome igual a Luiz");
} else {
  console.log("Nome não bateu com nenhum");
}
```

```js
let idade = 21;

// Idade menor que 30
if (idade < 30) {
  console.log("A idade é menor que 30");
}
// Idade menor ou igual a 30
if (idade <= 30) {
  console.log("A idade é menor ou igual a 30");
}
// Idade maior que 30
if (idade > 30) {
  console.log("A idade é maior que 30");
}
// Idade maior ou igual a 30
if (idade >= 30) {
  console.log("A idade é maior igual a 30");
}
// Diferente de idade maior que 30
if (!(idade > 30)) {
  console.log("A idade é maior que 30");
}
// Igual dade com 3 =
if (idade === 21) {
  console.log("A idade é igual a 21");
}
// Igual dade com 2 =
if (idade == 21) {
  console.log("A idade é igual a 21");
}
// Igual dade com 2 =
if (idade == "21") {
  console.log("A idade é igual a '21'");
}
if (idade === "21") {
  console.log("A idade é igual a '21'");
} else {
  console.log("A idade não é igual a '21' por conta do seu tipo de dado");
}
if (idade !== 22) {
  console.log("A idade é diferente a 22");
}
if (idade != 22) {
  console.log("A idade é diferente a 22");
}
if (idade != 21) {
  console.log("A idade é diferente a 21");
} else {
  console.log("A idade é igual a 21");
}
if (idade != "21") {
  console.log("A idade é diferente a '21'");
} else {
  console.log("A idade é igual a '21'");
}
if (idade !== "21") {
  console.log("A idade é diferente a '21'");
} else {
  console.log("A idade é igual a '21'");
}
if (idade !== 21) {
  console.log("A idade é diferente a 21");
} else {
  console.log("A idade é igual a 21");
}

if (idade > 18 && idade < 60) {
  console.log("Essa pessoa é adulta");
} else if (idade > 0 && idade < 18) {
  console.log("Essa pessoa é menor de idade");
} else if (idade > 60) {
  console.log("Essa pessoa é idosa");
} else {
  console.log("Idade inválida");
}

idade === 21 ? console.log("Igual a  21") : console.log("Diferente de 21");

let aluno = "Phineas";

switch (aluno) {
  case "Ferb":
    console.log("É o Ferb");
    break;
  case "Phineas":
    console.log("É o Phineas");
    break;
  default:
    console.log("Ops, não é nenhum desses");
    break;
}
```

### Desafio

- Crie uma variável chamada hora onde ela receberá o valor da hora atual (inteiro) e diga se ela está no período da manha (0h a 11h), tarde (12h a 17h) ou noite (18h a 23h)
- Crie uma variável chamada professor e atribua o nome "Josué" a ele. Verifique se essa string possui tamanho maior ou igual a 4.
- Altere o exercicio a cima para o nome de "Ricardinho" e verifique se ele possui valor menos ou igual a 10

## Funções

Função é um trecho de código que pode ser chamado diversas vezes e retorna valores ou não. Esse trecho de código pode receber parametros que alteram seu valor retornado.

```js
// função que retorna parametro somado com 2 
function soma2(num) {
  return num + 2;
}

// Imprime valor retornado
console.log(soma2(2));
console.log(soma2(5));
console.log(soma2(10));

// Atribui valor retornado a variável
const somado = soma2(20);
console.log(somado);
```
```js
// Uma função pode receber quantos parametros voce imaginar
// função que retorna parametros multiplicados
function multiplicar(a, b /*, params...*/) {
  return a * b;
}

// Imprime valor retornado
console.log(multiplicar(2, 10));

// Atribui valor retornado a variável
const multiplicado = multiplicar(10, 10);
console.log(multiplicado);
```

```js
// Escopo de uma função
var mensagem = "Hello!"
// função que retorna parametros multiplicados
function multiplicar(a, b /*, params...*/) {
  let resultado = a * b;
  console.log(mensagem);
  console.log(resultado);
  return resultado;
}

console.log(mensagem);
console.log(resultado); // Erro: resultado is not defined

// Imprime valor retornado
console.log(multiplicar(2, 10));
```

```js
// Outras formas de escrever função
// Padrão
function somar1(a, b) {
  return a + b;
}

// Função anônima
const somar2 = function (a, b) {
  return a + b;
};

// Arrow function
const somar3 = (a, b) => {
  return a + b;
};

// Outra forma de escrever Arrow function
const somar4 = (a, b) => a + b;

// Outra forma de escrever Arrow function
// Caso a arrow function possua apenas 1 parametro é possivel omitir os parentes
const multiplica2 = num => num * 2;

console.log(somar1(1,2));
console.log(somar2(1,2));
console.log(somar3(1,2));
console.log(somar4(1,2));
console.log(multiplica2(2));
```

```js
// Diferença entre function e arrow function
// No arrow function não é possivel acessar os argumentos da função
const calculadora1 = {
  somar(a, b) {
    console.log(arguments);
  },
};

calculadora1.somar(1, 2, 3);

const calculadora2 = {
  somar: (a, b) => {
    console.log(arguments);
  },
};

calculadora2.somar(1, 2, 3);

// No arrow function não é possivel acessar o this
let aluno1 = {
  nome: "Raul Seixas",
  seuNomeEh() {
    console.log(this.nome);
  },
};
aluno1.seuNomeEh();

let aluno2 = {
  nome: "Roberto Carlos",
  seuNomeEh: () => {
    console.log(this.nome);
  },
};
aluno2.seuNomeEh();

// No arrow function não é possivel usar o operador new
function Professor() {
  this.nome = "Marcelo";
  this.nivel = "Expert";

  this.dizOi = function () {
    console.log("Oi galera!");
  };
}
const prof = new Professor();
console.log(Professor.nome);
console.log(prof.nome);
```

### Desafio 

- Crie uma função que subtraia 2 de um número
- Crie um objeto chamado "calculadora" e crie funções nele para soma, subtração, multiplicação e divisão de dois numeros (a e b, por exemplo)
- Crie uma função que multiplica dois números (a e b) e retorne o resultado. Crie outra função que retorne o quadrado (x²) de um número. OBS: Use a função que multiplica dois números na função que gera o quadrado de um número
- Crie uma função que receba o nome e sobrenome de uma pessoa e retorne a seguinte frase: `Ola "nome da pessoa" "sobrenome da pessoa", seja bem-vindo!`

## Laço de repetição

```js
// Laço básico
for(let i=0; i<5; i++){
  console.log("Contando:", i)
}
```

```js
var nome = "Roberto Carlos"
for(let i=0; i<nome.length; i++){
  console.log(nome[i])
}
```

```js
var nome = "Roberto Carlos"
for(let i=0; i<nome.length; i++){
  if(nome[i]==="o"){
    console.log("Yup")
  }else{
    console.log(nome[i])
  }
}
```

```js
const produto = {
  id: 1,
  nome: "Blusica estilosa",
  preço: 2.99,
  quantidade: 523,
};

for (let chave in produto) {
  console.log(`Chave: ${chave} => valor: ${produto[chave]}`);
}

const pizzas = ["Mussarela", "Portuguesa", "Calabresa", "4 queijos"];

for (let valor of pizzas) {
  console.log(`Pizza sabor: ${valor}`);
}
```


### Desafio

- Crie um loop que conte de 0 a 100 e mostre apenas os números pares
- Faça o mesmo a cima da número ímpares
- Crie um array com valores inteiros aleatórios (exemplo [1,2,3,4]). Crie uma variável chamada "soma" e faça um loop que some o todos os valores dentro do array e atribua a variavel "soma".

## Destructuring (desestruturando)

```js
const frutas = ["Banana", "Pera", "Abacaxi", "Uva", "Melão"]

const [banana, pera, ,uva] = frutas
console.log(frutas)
console.log(banana)
console.log(pera)
console.log(uva)

const pessoa = {
  nome: "Maria Júlia",
  idade: 98,
  altura: 1.57,
  profissao: "Engenheira de bolos"
}

const {nome, profissao} = pessoa

console.log(pessoa)
console.log(nome)
console.log(profissao)
```

## Spread operator (Operador de espalhamento)

```js
// Array
const frutas = ["Banana", "Pera", "Abacaxi", "Uva", "Melão"]
const doces = ["Bolo de chocolate", "Pudim", "Brigadeiro", "Mel"]

const comidas = [...frutas, ...doces]

console.log(frutas)
console.log(doces)
console.log(comidas)
```


```js
// Objeto
const pessoa = {
  nome: "Maria Júlia",
  idade: 98,
  altura: 1.57,
  profissao: "Engenheira de bolos"
}
const endereco = {
  rua: "Floriano Peixoto",
  numero: "201A",
  bairro: "São Domingos",
  cidade: "Mucuripe",
  estado: "Acre"
}
const usuario = { ...pessoa, ...endereco}
console.log(pessoa)
console.log(endereco)
console.log(usuario)

// Mostrar exemplo para caso ocorra de existir duas chaves do mesmo nome
```

```js
// Funções - rest parameter
function exemplo(param1,param2, ...outrosParam){
  console.log(param1)
  console.log(param2)
  console.log(outrosParam)
}
exemplo(1,2,3,4,5,6)

const exemplo2 = (param1, param2, ...outrosParam) => {
  console.log(param1);
  console.log(param2);
  console.log(outrosParam);
};
exemplo2(1, 2, 3, 4, 5, 6);

function concatenaLetras(...letras){
  return  letras.join('')
}
console.log(concatenaLetras('a','b','c','d','e'))

function multiplicar(...numeros) {
  return numeros.reduce((acumulador, valorAtual) => acumulador * valorAtual);
}
console.log(multiplicar(1,2,3,4,5));

```

## Date

```js
const data = new Date()
console.log(data)
// Retorna valor de 1 a 31
console.log(data.getDate())
// Retorna valor de 0 a 11
// 0 = jan e 11 = dez
console.log(data.getMonth())
// Retorna valor de 0 a 6
// 0 = dom e 6 = sábado
console.log(data.getDay())
// Retorna ano (entre 1000 e 9999)
console.log(data.getFullYear())
// Retorna hora
console.log(data.getHours())
// Retorna minutos
console.log(data.getMinutes())
// Retorna segundos
console.log(data.getSeconds())
// É possivel dizer o valor da data que vc irá criar no formato aaaa/mm/dd
console.log(new Date(2020,10,30))
```