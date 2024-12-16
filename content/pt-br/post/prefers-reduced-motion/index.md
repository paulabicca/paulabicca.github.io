---
title: Porque você deveria começar a usar prefers-reduced-motion
description: Veja como implementar o prefers-reduced-motion em seu site para promover uma navegação mais acessível e confortável
slug: porque-voce-deveria-comecar-a-usar-prefers-reduced-motion
date: 2024-12-15 00:00:00+0000
tags:
  - acessibilidade
  - frontend
  - web
  - css
categories:
  - front-End
  - Programação
  - Acessibilidade
  - CSS
---

Na web, as animações e efeitos visuais são recursos populares para tornar as páginas mais dinâmicas e envolventes. No entanto, para alguns usuários, especialmente aqueles sensíveis a movimentos rápidos ou excessivos, esses recursos podem causar desconforto, como náusea ou tontura.  
Felizmente, podemos usar o `prefers-reduced-motion`, que permite ajustar ou desativar animações, oferecendo uma alternativa mais suave para quem prefere uma navegação mais estável. Neste texto, vamos explorar o que é o`prefers-reduced-motion`, como implementá-lo em seu site e como os usuários(e você, caso queira) podem modificar suas preferências para uma experiência mais confortável.

## **O que é prefers-reduced-motion?**
`prefers-reduced-motion` é um recurso do CSS que permite aos desenvolvedores ajustar a experiência de navegação para usuários que preferem reduzir ou eliminar animações e movimentos na interface. Isso é especialmente importante para aqueles que se sentem desconfortáveis com movimentos excessivos na tela, como efeitos visuais ou vídeos automáticos.

A configuração "reduzir movimento" pode ser ativada diretamente nas preferências do sistema do usuário. Quando ativada, o navegador envia essa preferência, permitindo que os desenvolvedores adaptem o conteúdo da página, seja desativando animações ou diminuindo sua intensidade. Isso pode incluir desde a desativação da reprodução automática de vídeos até a reestruturação da interação com a interface, tornando-a mais estável e simplificada para quem prefere uma navegação sem movimentos excessivos.

## **Como modificar suas preferências**
A configuração de "reduzir movimento" pode ser ativada diretamente nas configurações do seu dispositivo. Veja como modificar as preferências em diferentes sistemas:

- **Windows 10**: Configurações > Facilidade de Acesso > Vídeo > Mostrar animações no Windows.
- **Windows 11**: Configurações > Acessibilidade > Efeitos visuais > Efeitos de animação.
- **macOS**: Preferências do Sistema > Acessibilidade > Tela > Reduzir movimento.
- **iOS**: Ajustes > Acessibilidade > Movimento.
- **Android 9+**: Configurações > Acessibilidade > Remover animações.

## **Por que usar prefers-reduced-motion é importante para a acessibilidade?**
Implementar essa funcionalidade é um aspecto crucial da acessibilidade web, particularmente no critério AAA da WCAG (Web Content Accessibility Guidelines), especificamente no item 2.3.3: Animação a partir de Interações. Veja mais sobre isso [aqui](https://www.w3.org/WAI/WCAG21/Techniques/css/C39).

Alguns usuários, especialmente aqueles com condições vestibulares, podem sofrer efeitos colaterais indesejados de animações, como tontura ou náusea. Por exemplo, em páginas com rolagem parallax (onde o fundo se move em um ritmo diferente do conteúdo principal), o movimento extra pode ser um gatilho para esses distúrbios, mesmo que o movimento de rolagem por si só seja controlado pelo usuário.

Portanto, ao integrar `prefers-reduced-motion`, você oferece uma alternativa mais confortável para esses usuários, garantindo uma experiência mais inclusiva.

## **Como Implementar prefers-reduced-motion em CSS**
A implementação de `prefers-reduced-motion` em CSS é simples. Basta adicionar uma consulta de mídia que detecta a preferência do usuário e aplicar estilos alternativos quando a configuração estiver ativada. Veja o exemplo:

```css
@media (prefers-reduced-motion: reduce) {
  .notification {
    animation: none;
    transition: none;
  }
}
```
[Experimente na prática no CodePen!](https://codepen.io/paulabicca/pen/wBwgwYo)  
(_Não se esqueça de desativar os "Efeitos de animação" nas configurações do seu sistema operacional._)

## **Como Implementar prefers-reduced-motion em JavaScript**
No JavaScript, você pode usar a propriedade `window.matchMedia` para detectar a preferência do usuário por animações reduzidas e alterar o comportamento da página com base nessa preferência. Veja como isso pode ser feito:

```js
const prefersReducedMotion = window.matchMedia(
  "(prefers-reduced-motion: reduce)"
);
```
[Experimente na prática no CodePen!](https://codepen.io/paulabicca/pen/zxONOym)  
(_Não se esqueça de desativar os "Efeitos de animação" nas configurações do seu sistema operacional._)

## **Por que você deveria começar a usar prefers-reduced-motion?**
Incorporar o `prefers-reduced-motion` em seu site não é apenas uma questão técnica, mas um compromisso com a inclusão. Ao permitir que os usuários escolham como querem interagir com sua página, você proporciona uma experiência mais confortável e acessível para todos. Além disso, essa prática melhora a conformidade com as diretrizes de acessibilidade, garantindo que sua página seja acessível para um público maior, incluindo pessoas com condições que tornam animações excessivas um desafio. Portanto, sempre que possível, implemente soluções que respeitem a preferência por menos movimento, promovendo uma web mais inclusiva e menos cansativa para todos.
