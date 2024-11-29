---
title: "HTML semântico e WAI-ARIA : mais que amigos, friends"
description: Descubra como o HTML semântico e WAI-ARIA podem melhorar a acessibilidade do seu site.
slug: wai-aria-html-semantico-mais-que-amigos-friends
date: 2024-11-29 00:00:00+0000
tags: 
    - wai-aria
    - acessibilidade
    - WCAG
    - frontend
    - web
categories:
    - front-End
    - Programação
    - Acessibilidade

---

Quando falamos sobre desenvolvimento web, o **HTML semântico** e o **WAI-ARIA** são como dois parceiros inseparáveis, trabalhando juntos para tornar seu site mais acessível e fácil de entender. Você provavelmente já conhece o **HTML semântico**, mas o que é o **WAI-ARIA**? Vamos desvendar os dois de maneira simples e sem complicação!

---

## HTML Semântico: O Básico da Estrutura

Primeiro, vamos falar sobre **HTML semântico**. O que isso significa? Basicamente, é o uso de tags HTML que têm um significado claro e bem definido, tanto para o navegador quanto para os usuários. Ao usar elementos semânticos, você está criando um código que não só faz mais sentido para os desenvolvedores, mas também melhora a experiência dos usuários, especialmente aqueles com deficiência.

Por exemplo, em vez de usar  `<div> ` e adicionar atributos de estilo para que ela se comporte como um botão, você deve usar a tag  `<button> `, que já é semanticamente definida para essa função. Isso ajuda na acessibilidade e torna o código mais fácil de entender.

Exemplo de HTML Semântico:

**Evite:**
```html
<div role="button" aria-label="Enviar"></div>
```
**Prefira:**
```html
<button aria-label="Enviar"></button>
```
Optar por **HTML semântico**, como `<button>`, não só melhora a acessibilidade, mas também oferece outros benefícios:

- **Melhor desempenho em dispositivos móveis:** O HTML semântico é mais leve e facilita a criação de layouts responsivos.
- **Melhor SEO:** Os mecanismos de busca dão mais relevância a elementos semânticos, como títulos e links, facilitando a indexação do seu conteúdo.
- **Facilidade no desenvolvimento:** O código é mais limpo, intuitivo e fácil de entender.

Agora vamos com alguns exemplos?

| **Exemplo Genérico**       | **Exemplo Semântico**      | **Descrição**                                            |
|----------------------------|----------------------------|----------------------------------------------------------|
| `<div id="header">`         | `<header>`                 | Define o cabeçalho de uma página ou seção.               |
| `<div id="nav">`            | `<nav>`                    | Define um bloco de navegação.                            |
| `<div class="article">`     | `<article>`                | Representa um conteúdo independente, como uma postagem.  |
| `<div class="section">`     | `<section>`                | Define uma seção ou parte do conteúdo com um título.     |
| `<div id="footer">`         | `<footer>`                 | Representa o rodapé de uma página ou seção.              |
| `<div class="main">`        | `<main>`                   | Define o conteúdo principal da página.                   |
| `<div id="aside">`          | `<aside>`                  | Representa conteúdo relacionado, mas não essencial.       |
| `<div class="heading">`     | `<h1>`, `<h2>`, `<h3>`, etc.| Define títulos e subtítulos, estruturando o conteúdo.    |
| `<div class="button">`      | `<button>`                 | Representa um botão de ação.                             |


---

## WAI-ARIA: Dando uma Mãozinha na Acessibilidade
Agora, o **WAI-ARIA** (Accessible Rich Internet Applications) entra em cena. Ele é como um assistente extra, ajudando a tornar o seu site acessível quando o **HTML semântico** não é o suficiente para descrever a funcionalidade de um elemento, como em aplicativos dinâmicos ou interfaces mais complexas. O **WAI-ARIA** oferece "informações extras" para tecnologias assistivas, como leitores de tela, para garantir que todos os usuários, independentemente de suas limitações, possam interagir com o conteúdo de forma eficiente.

Agora que você sabe o que é **WAI-ARIA** vamos falar de dois atributos deles:  **aria** e **role**.

---

### Atributos ARIA 
Os **atributos ARIA** são usados para fornecer informações adicionais a tecnologias assistivas, como leitores de tela, quando o HTML padrão não é suficiente para descrever a funcionalidade ou o estado de um elemento de forma clara.

A seguir, apresento alguns **atributos ARIA** comuns que podem ser muito úteis no seu dia a dia de desenvolvimento. Para uma lista completa, consulte a documentação [aqui](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes).


---


 **Exemplos de Atributos ARIA:**

| Atributo ARIA     | Descrição                                                                | Exemplo                                  |
|-------------------|--------------------------------------------------------------------------|------------------------------------------|
| **aria-label**    | Fornece um texto descritivo para elementos de interface sem texto visível.| `<button aria-label="Fechar">X</button>` |
| **aria-hidden**   | Esconde um elemento para leitores de tela, sem afetar sua visibilidade.                              | `<div aria-hidden="true">Este conteúdo não será lido pelo leitor de tela</div>`    |
| **aria-description**    | Fornece uma descrição mais detalhada sobre um elemento.                              | `<div aria-description="Este botão envia o formulário">Enviar</div>`    |
| **contenteditable**   |Indica que um campo é editável, útil quando usamos uma  `<div>`  em vez de um  `<input>`.                               | `<div contenteditable="true">Edite este texto</div>`    |
| **aria-required**   | Marca um campo de formulário como obrigatório.                             | `<input type="text" aria-required="true" />`    |
| **aria-invalid**    | 	Indica que um campo contém um valor inválido.                      | `<input type="text" aria-invalid="true" />`    |
| **aria-expanded**    | Informa se um menu ou acordeão está expandido ou contraído.                               | `<button aria-expanded="false">Menu</button>`    |
| **aria-labelledby**    | Referencia outro elemento para fornecer um nome acessível.                             | `<h1 id="header">Título</h1><div aria-labelledby="header">Conteúdo associado ao título</div>`    |
| **aria-details**     |Fornece informações adicionais ou descrições mais detalhadas sobre um elemento.                            | `<button aria-details="info">Mais informações</button>`    |

---


### Funções ARIA: Roles 
Por padrão, muitos elementos **HTML semânticos** já têm funções definidas. Por exemplo, um  `<input type="radio"> ` tem a função de "radio". Elementos não semânticos, como  `<div> ` e  `<span> `, precisam do atributo role para definir sua função.

A seguir, apresento alguns roles comuns que podem ser muito úteis no seu dia a dia de desenvolvimento. Para uma lista completa, consulte a documentação [aqui](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles).


---


 **Exemplos de Roles:**

| Função ARIA (Role)     | Descrição                                                                | Exemplo                                  |
|-------------------|--------------------------------------------------------------------------|------------------------------------------|
| **role="alert"**    | Comunica uma mensagem importante e geralmente sensível ao tempo ao usuário.| `<div role="alert">Erro: campo obrigatório não preenchido.</div>` |
| **role="definition"**   |Indica que o elemento contém a definição de um termo ou conceito.                             | `<div role="definition">Acessibilidade: prática de tornar a web acessível para todos.</div>`    |
| **role="search"**    | Define a área de pesquisa da página.                              | `<div role="search">Caixa de pesquisa</div>`    |
| **role="modal"**   |Indica que o elemento é um modal.                            | `<div role="modal">Este é um modal</div>`    |
| **role="dialog"**   |Indica que o elemento é uma janela de diálogo.                            | `<div role="dialog">Esta é uma janela de diálogo</div>`    |

---

## Vamos Colocar em Prática?

E aí está! Agora você já sabe como o **HTML semântico** e o **WAI-ARIA** podem trabalhar juntos para melhorar a acessibilidade do seu site. Usar **HTML semântico** é como construir uma casa com uma estrutura sólida e bem planejada, enquanto o **WAI-ARIA** é aquele toque final que garante que todo mundo consiga acessar e interagir com ela, independentemente de limitações. Ao aplicar essas práticas, você não só torna seu site mais inclusivo, mas também otimiza a experiência do usuário e ajuda a melhorar o SEO.

A acessibilidade na web é mais do que uma boa prática — é um compromisso com um mundo digital mais justo e acessível para todos.

Agora que você já sabe o básico, que tal começar a aplicar esses conceitos no seu próximo projeto? Lembre-se: cada pequeno passo conta!