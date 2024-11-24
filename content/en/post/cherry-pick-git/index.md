---
title: How Cherry-pick can save you
description: Find out how this command can save your day by avoiding rework, solving bugs on the wrong branch or reusing solutions efficiently.
slug: how-cherry-pick-can-save-you
date: 2024-11-23 00:00:00+0000
tags: 
    - Git
    - Cherry-pick
    - GitHub
    - GitKraken
    -  VS Code
categories:
    - Git
    - Programming Tips
    - Programming
---


Have you ever solved a bug on the wrong branch or needed to reuse a solution without taking everything with you? This is where cherry-pick comes in! This Git command is the equivalent of picking the perfect fruit from a tree: you get exactly what you need, without the "whole package".

Imagine recovering that lost code or taking a solution to another branch without redoing everything. Curious? Then let's explore how cherry-picking can save you from this problem!

---

## **What is Cherry-Pick?**
The git `cherry-pick` command allows you to apply a specific commit from one branch to another. Instead of bringing up the entire history, as in merge or rebase, it focuses only on what you point to.

It works like this: you locate the hash of the commit you want, and Git transports the changes to the current branch. Ideal for one-off situations where you need to make adjustments without messing up the workflow.

Why use it? To avoid rework, recover lost changes or ensure that corrections are in the right branches.

---

## **When is the Cherry-Pick the Best Option?**
**1. Recovering a specific commit to another branch**  
You've fixed a bug, but realized you were on the wrong branch. No need to despair! Just apply the commit to the correct branch.

**2. Incorporate solutions between branches without a full merge**
Need a feature ready, but don't want to carry all the baggage of another branch? Cherry-pick it.

**3. Error committing directly to main**  
An accidental commit to main can be moved to the correct branch quickly, keeping the history clean.

---

## **How to Use Cherry-Pick in Practice**
**Step 1: Find the commit hash**  
First, locate the commit you want to apply. Use the `git log` command or a graphical interface to find the hash.

If you don't know what a commit hash is, here's an example to help:

```bash
commit e0c3d682014f6b2bf8d2814512bc8c00c2968b40 (origin/development)  # Isso é um hash
Author: Jane Doe <jane.doe@gmail.com>  
Date:   Tue Nov 21 14:32:01 2024  

```

**Step 2: Apply the commit to the desired branch**

Now go to the branch where you want to apply this commit. Always check that you are on the correct branch. For example, if you want to bring a commit from the `development`  branch to the `feature-login` branch, make sure you're there with a `git log`.

```bash
git cherry-pick <hash-do-commit> 

```


**Step 3: Resolve conflicts (if any)**

If the commit causes conflicts, Git will show you which files need to be adjusted. Resolve the conflicts manually by editing the files indicated.

After resolving, end the process with:

```bash
git cherry-pick --continue

```
If you need to cancel the cherry-pick for any reason, use it:

```bash
git cherry-pick --abort

```

**Step 4: Confirm the result**

Finally, check that the commit has been applied correctly. Use the git log command to check that the commit appears in the history of the current branch.

If all went well, the cherry-pick brought exactly what you needed to the feature-login branch!

---

## **Best Practices**
- **Context is everything:**  Make sure you really need to use cherry-pick on the current branch. For larger scenarios, use merge or rebase, which are more organized choices.

- **Organization first:** Don't use cherry-pick as a "shortcut" to fix poor branch management.

- **Frequent conflicts:**  Collaborate with your team to avoid rework and reduce conflict points.


---

## **Tools and Documentation**

Cherry-pick is a super useful tool that allows you to fix bugs, reuse code, and optimize workflows.

Want to dive deeper into the topic? Check out the [official Git documentation](https://git-scm.com/docs/git-cherry-pick). It's comprehensive and will make you an expert on the subject..

And to make your life even easier, why not use some VS Code extensions? Here are a few that can help you perform a cherry-pick without complications:

- **GitLens**: Provides a detailed view of commits and history, making it easier to identify the right commit.

- **Git Graph**: Displays the repository history in a highly intuitive graph, perfect for locating that specific hash.

- **GitKraken** (external tool, but worth mentioning): For those who prefer user-friendly graphical interfaces over the command line.

---

Now it's your turn: have you ever faced a situation where cherry-pick could have saved your day? Share your story in the comments!