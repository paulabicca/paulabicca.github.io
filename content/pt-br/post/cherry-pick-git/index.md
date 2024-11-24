---
title: Como o Cherry-pick pode salvar você
description: Descubra como esse comando pode salvar seu dia ao evitar retrabalho, resolver bugs na branch errada ou reaproveitar soluções de forma eficiente.
slug: como-cherry-pick-pode-salvar-voce
date: 2024-11-23 00:00:00+0000
tags: 
    - Git
    - Cherry-pick
    - GitHub
    - GitKraken
    -  VS Code
categories:
    - Git
    - Dicas de Programação
    - Programação
---

Já aconteceu de você resolver um bug na branch errada ou precisar reutilizar uma solução sem levar tudo junto? É aqui que o cherry-pick entra em cena! Esse comando do Git é o equivalente a escolher a fruta perfeita numa árvore: você pega exatamente o que precisa, sem o “pacote completo”.

Imagine recuperar aquele código perdido ou levar uma solução para outra branch sem refazer tudo. Curioso? Então vamos explorar como o cherry-pick pode te salvar desse problema ✨️

---

## **O que é Cherry-Pick?**

O comando git cherry-pick permite aplicar um commit específico de uma branch em outra. Em vez de trazer todo o histórico, como no merge ou rebase, ele foca apenas no que você apontar.

Funciona assim: você localiza o hash do commit desejado, e o Git transporta as mudanças para a branch atual. Ideal para situações pontuais em que você precisa de ajustes sem bagunçar o fluxo de trabalho.

Por que usar? Para evitar retrabalho, recuperar mudanças perdidas ou garantir que correções estejam nas branches certas.


---

## **Quando o Cherry-Pick é a Melhor Opção?**

**1. Recuperar um commit específico para outra branch:**
Você corrigiu um bug, mas percebeu que estava na branch errada. Sem desespero! Basta aplicar o commit na branch correta.


**2. Incorporar soluções entre branches sem um merge completo:**
Precisa de uma funcionalidade pronta, mas não quer carregar toda a bagagem de outra branch? Cherry-pick resolve.


**3. Erro ao fazer commit direto na main:**
Um commit acidental na main pode ser levado para a branch correta rapidamente, mantendo o histórico limpo.

---

## **Como Usar Cherry-Pick na Prática**

**Passo 1: Encontre o hash do commit**  
Primeiro, localize o commit que você deseja aplicar. Use o comando `git log` ou uma interface gráfica para encontrar o hash.

Se você não sabe o que é um hash de commit, aqui vai um exemplo para ajudar:  

```bash
commit e0c3d682014f6b2bf8d2814512bc8c00c2968b40 (origin/development)  # Isso é um hash
Author: Jane Doe <jane.doe@gmail.com>  
Date:   Tue Nov 21 14:32:01 2024  

```

**Passo 2: Aplique o commit na branch atual**

Agora, vá para a branch onde você quer aplicar esse commit.
Sempre verifique se você está na branch correta. Por exemplo, se você deseja trazer um commit da da branch `development` para a branch `feature-login`, verifique se está nela com um git log. 


**Passo 3: Resolva conflitos (se houver)**  

Se o commit causar conflitos, o Git mostrará quais arquivos precisam ser ajustados. Resolva os conflitos manualmente editando os arquivos indicados.

Depois de resolver, finalize o processo com:

```bash
git cherry-pick --continue

```
Se precisar cancelar o cherry-pick por algum motivo, use:

```bash
git cherry-pick --abort

```

**Passo 4: Confirme o resultado**

Por fim, confira se o commit foi aplicado corretamente. Use o comando git log para verificar se o commit aparece no histórico da branch atual.

Se tudo deu certo, o cherry-pick trouxe exatamente o que você precisava para a branch feature-login! 

---

## **Cuidados e Boas Práticas**

- **Contexto é tudo:** Entende se você realmente precisa de cherry-pick na branch atual. Para cenários maiores use o merge ou rebase são escolhas mais organizadas.

- **Organização primeiro:** Não use cherry-pick como “jeitinho” para corrigir má gestão de branches.

- **Conflitos frequentes:** Trabalhe em equipe para evitar retrabalho e reduza pontos de conflito.

---

## **Recursos adicionais**

O cherry-pick é uma ferramenta super utíl que torna possível corrigir erros, reutilizar código e otimizar fluxos de trabalho.

Quer se aprofundar no assunto? Dá uma olhada na [documentação oficial do Git](https://git-scm.com/docs/git-cherry-pick). É completíssima e vai te deixar um expert no assunto.

E para facilitar ainda mais a sua vida, que tal usar extensões do VS Code? Aqui estão algumas que podem te ajudar na hora de dar um cherry-pick sem complicação:

- **GitLens**: Traz uma visualização detalhada de commits e histórico, facilitando a identificação do commit certo.

- **Git Graph**: Exibe o histórico do repositório em um gráfico super intuitivo, perfeito para localizar aquele hash específico.

- **GitKraken** (ferramenta externa, mas vale citar): Para quem prefere interfaces gráficas amigáveis ao invés da linha de comando.

---

Agora é sua vez: já teve uma situação em que o cherry-pick teria salvado seu dia? Me conte nos comentários!
