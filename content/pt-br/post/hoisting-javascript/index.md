---
title: "Você já ouviu falar em Hoisting?"
description: Entenda como hoisting funciona, suas implicações nos escopos e casos de uso.
slug: voce-ja-ouviu-sobre-hoisting
date: 2025-01-09 00:00:00+0000
tags:
  - Javascript
  - frontend
categories:
  - Programação
  - front-End
  - Javascript
---


Já se deparou com um código onde uma variável parecia ser usada antes de sua declaração e ficou confuso sobre o que estava acontecendo? Isso é o **hoisting** em JavaScript!
Vamos explorar esse conceito básico, como os escopos importam para esse conceito e suas implicações.

---

## **Escopo: Um contexto para o Hoisting**

Antes de conversamos sobre o que é **hoisting**, primeiro precisamos entender um pouco melhor sobre escopos.  Em JavaScript, o escopo é o contexto onde uma variável pode ser acessada ou utilizada.   
Existem três tipos principais de escopo:

## **Tipos de Escopo**

### **Escopo Global**

Variáveis declaradas fora de qualquer função ou bloco estão no escopo global, acessíveis de qualquer lugar no código.

**Exemplo:**

```javascript
var globalVar = "Estou no escopo global!";
function mostrarGlobal() {
  console.log(globalVar); 
}
mostrarGlobal();

/*
A saída do código acima é: "Estou no escopo global!"
*/
```

### **Escopo Local (ou de Função)**

Variáveis declaradas dentro de uma função só podem ser acessadas dentro dela.

**Exemplo:**

```javascript
function minhaFuncao() {
  let localVar = "Estou no escopo local!";
  console.log(localVar); // "Estou no escopo local!"
}
minhaFuncao();
console.log(localVar); // ReferenceError: localVar is not defined
```

### **Escopo de Bloco**

Introduzido no ES6,  as variáveis declaradas com `let` ou `const` dentro de um bloco {} são limitadas a esse bloco.

**Exemplo:**

```javascript
if (true) {
  let blocoVar = "Estou no escopo de bloco!";
  console.log(blocoVar); // "Estou no escopo de bloco!"
}
console.log(blocoVar); // ReferenceError: blocoVar is not defined
```

---

Agora que entendemos sobre escopo, vamos entender melhor o que é **Hoisting** .

## **O Que é Hoisting?**

 O **hoisting** é um comportamento do JavaScript que permite utilizar uma função ou variável antes de sua declaração. Isso ocorre porque o mecanismo de hoisting eleva as declarações para o topo do escopo, tornando-as acessíveis antes mesmo de serem definidas no código.
 Caso você queira uma explicação mais detalhada você encontra [aqui](https://developer.mozilla.org/pt-BR/docs/Glossary/Hoisting).

Agora que você possui uma explicação. Vamos aos exemplos.

### **Exemplos de Hoisting**

#### **Com variável**

```javascript
minhaVariavel = 3; //Inicializa minhaVariavel
console.log("aqui será 3:", minhaVariavel); // a saída será 3
var minhaVariavel; //Declara minhaVariavel para hoisting
```

Aqui, a variável `minhaVariavel` foi 'içada' para o topo do código e por isso que no meu console log a saída é `3`.

---

#### **Com função**

```javascript
fullName("Jane", "Doe");

function fullName(name, lastName) {
  console.log(`Meu nome é ${name} ${lastName}`);
}
/*
A saída do código acima é: "Meu nome é Jane Doe"
*/
```
Mesmo que chamemos a função em nosso código primeiro, antes que a função seja escrita, o código ainda funciona. 

#### **Com `let` e `const`**

```javascript
console.log(minhaVariavel); // ReferenceError: Cannot access 'minhaVariavel' before initialization
console.log(minhaVariavelConst); // SyntaxError: Missing initializer in const declaration

let minhaVariavel = "Olá, Mundo!";
const minhaVariavelConst = "Olá, Mundo!";
```

Ao contrário de `var`, variáveis declaradas com `let` ou `const` são içadas, mas permanecem em um estado de "**Temporal Dead Zone (TDZ)**" até serem declaradas.

#### **O que é Temporal Dead Zone?**

A TDZ é o período entre a criação de uma variável e a sua declaração no código. Durante a TDZ, a variável existe, mas ainda não foi inicializada, e acessar ela nesse intervalo gera um erro de referência (ReferenceError). A TDZ afeta principalmente variáveis declaradas com `let` e `const`, já que elas seguem seus escopos, ao contrário de variáveis com `var`.

---

## **Casos de (possíveis) usos**

O **hoisting** em si não é uma técnica ou recurso que você escolhe usar diretamente, mas sim um comportamento do JavaScript. Então, a questão não é usar **hoisting** , mas compreender como ele funciona para evitar armadilhas e tirar proveito de situações específicas.

### **Casos Onde Faz Sentido**

1. **Scripts Legados com var**  
   Em projetos mais antigos que ainda utilizam var, o hoisting pode ser útil para entender como variáveis são tratadas. No entanto, não é recomendado adotar var em novos projetos, pois ele é propenso a causar confusão e bugs.

2. **Bibliotecas e Frameworks Antigos**  
   Se você trabalha com bibliotecas ou frameworks que não adotaram padrões modernos (como ES6), entender o hoisting é crucial para depurar e evitar erros.

3. **Protótipos de Código e Aprendizado**  
   Durante o aprendizado de JavaScript, o hoisting pode ajudar a entender como o JavaScript lida com variáveis e funções nos bastidores. No entanto, é importante entender as boas práticas desde o início, como sempre declarar variáveis antes de usá-las.

---

### **Casos Onde Não Faz Sentido**

1. **Novos Projetos Modernos**  
   Com `let` e `const`, o hoisting torna-se menos relevante porque essas variáveis não podem ser usadas antes da declaração. Isso cria uma abordagem mais previsível e menos propensa a erros.

2. **Boas Práticas e Legibilidade**  
   Embora o hoisting permita executar código antes da declaração, não é uma prática recomendada, pois pode tornar o código confuso para outros desenvolvedores (ou até para você mesmo no futuro).

---

## **Ainda faz sentido nos dias de hoje?**

O hoisting ainda faz sentido hoje? Sim, não, depende... hahaha!  
Brincadeiras à parte, o hoisting ainda é útil em situações específicas, como no uso de declarações de funções e na manutenção de projetos legados. Porém, em projetos modernos, o cenário é diferente.

Aqui vão algumas dicas para lidar com variáveis e evitar problemas:

- Prefira let e const.
- Declare variáveis no início do escopo onde serão usadas.
- Evite confiar no comportamento implícito do hoisting para garantir um código mais legível e previsível.

Embora o uso direto do conceito de hoisting seja cada vez menos comum, entender como ele funciona continua sendo uma habilidade essencial para todo desenvolvedor JavaScript.   
Afinal, conhecimento nunca é demais, certo? :)
