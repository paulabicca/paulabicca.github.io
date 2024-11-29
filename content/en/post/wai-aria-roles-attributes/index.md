---
title: "WAI-ARIA & semantic HTML: Partners in Accessibility"
description: Find out how semantic HTML and WAI-ARIA can improve the accessibility of your site.
slug: wai-aria-semantic-html-partners-in-accessibility
date: 2024-11-29 00:00:00+0000
tags: 
    - wai-aria
    - accessibility
    - WCAG
    - frontend
    - web
categories:
    - front-End
    - programming
    - accessibility

---

When it comes to web development, **semantic HTML** and **WAI-ARIA** are like two inseparable partners, working together to make your site more accessible and easier to understand. You probably already know about **semantic HTML**, but what is **WAI-ARIA**? Let's unravel both in a simple and uncomplicated way

---

## Semantic HTML: The Basics of Structure

First, let's talk about **semantic HTML**. What does this mean? Basically, it's the use of HTML tags that have a clear and well-defined meaning, both for the browser and for users. By using semantic elements, you are creating code that not only makes more sense to developers, but also improves the experience of users, especially those with disabilities.

For example, instead of using `<div>` and adding style attributes to make it behave like a button, you should use the `<button>` tag, which is already semantically defined for this function. This helps with accessibility and makes the code easier to understand.

Example of Semantic HTML:

**Avoid:**
```html
<div role="button" aria-label="Send"></div>
```
**Prefer:**
```html
<button aria-label="Send"></button>
```

Opting for **semantic HTML**, such as `<button>`, not only improves accessibility, but also offers other benefits:

- **Better performance on mobile devices:** Semantic HTML is lighter and makes it easier to create responsive layouts.
- **Better SEO:** Search engines give more relevance to semantic elements such as titles and links, making it easier to index your content.
- **Ease of development:** The code is cleaner, more intuitive and easier to understand.

Now let's look at some examples.

| **Generic Example**       | **Semantic Example**      | **Description**                                            |
|----------------------------|----------------------------|----------------------------------------------------------|
| `<div id="header">`         | `<header>`                 | Defines the header of a page or section.               |
| `<div id="nav">`            | `<nav>`                    | Defines a navigation block.                            |
| `<div class="article">`     | `<article>`                | Represents independent content, such as a post.  |
| `<div class="section">`     | `<section>`                | Defines a section or piece of content with a title.     |
| `<div id="footer">`         | `<footer>`                 | Represents the footer of a page or section.              |
| `<div class="main">`        | `<main>`                   | Defines the main content of the page.                  |
| `<div id="aside">`          | `<aside>`                  | Represents related but non-essential content.      |
| `<div class="heading">`     | `<h1>`, `<h2>`, `<h3>`, etc.| Defines headings and subheadings, structuring the content.    |
| `<div class="button">`      | `<button>`                 | Represents an action button.                            |


---

## WAI-ARIA: Giving Accessibility a Hand
Now, **WAI-ARIA** (Accessible Rich Internet Applications) comes into the picture. It's like an extra assistant, helping to make your site accessible when **semantic HTML** isn't enough to describe the functionality of an element, such as in dynamic applications or more complex interfaces. The **WAI-ARIA** provides "extra information" for assistive technologies, such as screen readers, to ensure that all users, regardless of their limitations, can interact with the content efficiently.

Now that you know what **WAI-ARIA** is, let's talk about two of its attributes: **aria** and **role**.


---

### ARIA Attributes
**ARIA attributes** are used to provide additional information to assistive technologies, such as screen readers, when standard HTML is not sufficient to clearly describe the functionality or state of an element.

Below are some common **ARIA attributes** that can be very useful in your day-to-day development. For a complete list, check the documentation [here](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes).


---


 **Examples of ARIA Attributes:**

| ARIA Attributes     | Description                                                                | Example                                  |
|-------------------|--------------------------------------------------------------------------|------------------------------------------|
| **aria-label**    | Provides a descriptive text for interface elements without visible text.| `<button aria-label="Close">X</button>` |
| **aria-hidden**   | Hides an element from screen readers without affecting its visibility.                              | `<div aria-hidden="true">This content will not be read by the screen reader</div>`    |
| **aria-description**    | Provides a more detailed description of an element.                              | `<div aria-description="This button submits the form">Enviar</div>`    |
| **contenteditable**   |Indicates that a field is editable, useful when using a `<div>` instead of an `<input>`.                             | `<div contenteditable="true">Edit this text</div>`    |
| **aria-required**   | Marks a form field as required.                            | `<input type="text" aria-required="true" />`    |
| **aria-invalid**    | 	Indicates that a field contains an invalid value.                     | `<input type="text" aria-invalid="true" />`    |
| **aria-expanded**    | Specifies whether a menu or accordion is expanded or collapsed.                               | `<button aria-expanded="false">Menu</button>`    |
| **aria-labelledby**    | References another element to provide an accessible name.                            | `<h1 id="header">Title</h1><div aria-labelledby="header">Content associated with the title</div>`    |
| **aria-details**     | Provides additional information or a more detailed description of an element.                            | `<button aria-details="info">More information</button>`    |

---


### ARIA Roles
By default, many semantic **HTML elements** already have predefined roles. For example, an  `<input type="radio">` has the role of "radio." Non-semantic elements like  `<div>` and  `<span>` require the role attribute to define their function.

Below are some common roles that can be very useful in your day-to-day development. For a complete list, check the documentation [here](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles).

---

 **Role Examples:**

| ARIA Roles     | Description                                                                | Example                                  |
|-------------------|--------------------------------------------------------------------------|------------------------------------------|
| **role="alert"**    | Communicates an important and usually time-sensitive message to the user.| `<div role="alert">Error: required field not filled in.</div>` |
| **role="definition"**   |Indicates that the element contains the definition of a term or concept.                         | `<div role="definition">Accessibility: the practice of making the web accessible to everyone.</div>`    |
| **role="search"**    | Defines the search area of the page.                             | `<div role="search">Search box</div>`    |
| **role="modal"**   |Indicates that the element is a modal.                            | `<div role="modal">This is a modal</div>`    |
| **role="dialog"**   |Indicates that the element is a dialog window.                           | `<div role="dialog">This is a dialog window</div>`    |

---

## Let's Put It into Practice?

And there it is! Now you know how **semantic HTML** and **WAI-ARIA** can work together to improve your website's accessibility. Using **semantic HTML**  is like building a house with a solid and well-planned structure, while **WAI-ARIA** is that final touch that ensures everyone can access and interact with it, regardless of limitations. By applying these practices, you not only make your website more inclusive, but also optimize the user experience and help improve SEO.

Web accessibility is more than just a good practice — it's a commitment to a fairer and more accessible digital world for everyone.

Now that you know the basics, how about starting to apply these concepts in your next project? Remember: every small step counts!