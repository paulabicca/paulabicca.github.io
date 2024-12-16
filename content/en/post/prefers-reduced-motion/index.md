---
title: Why You Should Start Using prefers-reduced-motion
description: Learn how to implement prefers-reduced-motion on your site to promote a more accessible and comfortable browsing experience.
slug: why-you-should-start-using-prefers-reduced-motion
date: 2024-12-16 00:00:00+0000
tags:
  - accessibility
  - frontend
  - web
categories:
  - front-End
  - programming
  - accessibility
---

On the web, animations and visual effects are popular tools to make pages more dynamic and engaging. However, for some users—especially those sensitive to rapid or excessive motion—these features can cause discomfort, such as nausea or dizziness.

Fortunately, we can use `prefers-reduced-motion`,, which allows us to adjust or disable animations, offering a smoother alternative for those who prefer a more stable browsing experience. In this text, we’ll explore what `prefers-reduced-motion`, is, how to implement it on your site, and how users (including you, if desired) can adjust their preferences for a more comfortable experience.

## **What is prefers-reduced-motion?**

`prefers-reduced-motion` is a CSS feature that allows developers to adjust the browsing experience for users who prefer to reduce or eliminate animations and motion in the interface. This is especially important for those who feel uncomfortable with excessive motion on the screen, such as visual effects or autoplaying videos.

The "reduce motion" setting can be enabled directly in the user’s system preferences. When enabled, the browser communicates this preference, allowing developers to adapt the page content—whether by disabling animations or reducing their intensity. This can range from turning off autoplay videos to restructuring interface interactions, making them more stable and simplified for those who prefer less motion.

## **How to Adjust Your Preferences**
The "reduce motion" setting can be enabled directly in your device settings. Here’s how to modify your preferences on different systems:

- **Windows 10:** Settings > Ease of Access > Video > Show animations in Windows.
- **Windows 11:** Settings > Accessibility > Visual Effects > Animation effects.
- **macOS:** System Preferences > Accessibility > Display > Reduce Motion.
- **iOS:** Settings > Accessibility > Motion.
- **Android 9+:** Settings > Accessibility > Remove Animations.


## **Why is prefers-reduced-motion Important for Accessibility?**
Implementing this feature is a crucial aspect of web accessibility, particularly under the AAA criterion of the WCAG (Web Content Accessibility Guidelines), specifically item 2.3.3: Animation from Interactions. Learn more about it [here](https://www.w3.org/WAI/WCAG21/Techniques/css/C39).

Some users, especially those with vestibular conditions, may experience unwanted side effects from animations, such as dizziness or nausea. For example, in pages with parallax scrolling (where the background moves at a different pace than the main content), the extra motion can trigger these issues, even if the scrolling itself is user-controlled.

By integrating `prefers-reduced-motion`, you provide a more comfortable alternative for these users, ensuring a more inclusive experience.


## **How to Implement prefers-reduced-motion in CSS**
Implementing `prefers-reduced-motion` in CSS is simple. Just add a media query that detects the user’s preference and applies alternative styles when the setting is enabled. Here’s an example:

```css
@media (prefers-reduced-motion: reduce) {
  .notification {
    animation: none;
    transition: none;
  }
}
```
[Try it out on CodePen!](https://codepen.io/paulabicca/pen/wBwgwYo)  
(_(Don’t forget to disable “Animation effects” in your system settings.)_)

## **How to Implement prefers-reduced-motion in JavaScript**
In JavaScript, you can use the `window.matchMedia` property to detect the user’s preference for reduced motion and modify the page behavior accordingly. Here’s how:

```js
const prefersReducedMotion = window.matchMedia(
  "(prefers-reduced-motion: reduce)"
);
```
[Try it out on CodePen!](https://codepen.io/paulabicca/pen/zxONOym)  
(_(Don’t forget to disable “Animation effects” in your system settings.)_)

## **Why You Should Start Using prefers-reduced-motion?**
Incorporating  `prefers-reduced-motion` into your site isn’t just a technical decision—it’s a commitment to inclusion. By allowing users to choose how they interact with your page, you provide a more comfortable and accessible experience for everyone.

Additionally, this practice enhances compliance with accessibility guidelines, ensuring your page is accessible to a wider audience, including those with conditions that make excessive animations challenging. Whenever possible, implement solutions that respect the preference for less motion, fostering a more inclusive and less exhausting web for all.