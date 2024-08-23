---
title: "What is @tailwind base, components, utilities in global.css when using tailwind"
descriptions: "Create next.js project style using tailwind.css and global.css files"
last_modified_at: 2024-08-23T20:00:00-05:00
# header:
#   teaser: /assets/images/logo.png
categories:
  - nextjs
tags:
  - tailwindcss
  - globalcss
---

Create next.js project style using tailwind.css and global.css files

## Intro

When working with Tailwind CSS in a Next.js project, the global.css file often includes <span style='background: #222222; color:white;'>three powerful directives: @tailwind base, @tailwind components, and @tailwind utilities</span>. These directives play a crucial role in structuring and applying styles throughout your project. Understanding how each of these works can significantly enhance your ability to create consistent, maintainable, and efficient designs.


### Add @layer using theme() and @apply

- <span style="color: green;">**`theme()`**</span>: This function allows you to access values from your Tailwind configuration, such as colors, spacing, and font sizes. This is useful when you want to reference these values directly in your custom CSS.

- <span style="color: green;">**`@apply`**</span>: This directive lets you inline Tailwind's utility classes within your custom CSS. This can help you maintain consistency and leverage Tailwind's design system even within custom styles.

- <span style="color: green;">**`@layer`**</span>: This directive enables you to add custom styles to Tailwind's predefined layers (`base`, `components`, and `utilities`). This provides a structured way to organize and manage your custom styles, ensuring they integrate seamlessly with Tailwind's core functionality.


#### [Case1] @tailwind base;

```css
/* global.css */
@tailwind base;

@layer base {
  h1 {
    @apply text-2xl font-bold;
  }

  p {
    @apply text-base leading-6;
  }

  a {
    @apply text-blue-600 underline hover:text-blue-800;
  }
}
```

#### [Case2] @tailwind components;

```css
/* global.css */
@tailwind components;

@layer components {
  .btn {
    @apply inline-block px-4 py-2 rounded bg-blue-500 text-white font-semibold;
  }

  .card {
    background-color: theme("colors.white");
    border-radius: theme("borderRadius.lg");
    padding: theme("spacing.6");
    box-shadow: theme("boxShadow.xl");
  }
}
```

#### [Case3] @tailwind utilities;

```css
/* global.css */
@tailwind utilities;

@layer utilities {
  .content-auto {
    content-visibility: auto;
  }

  .bg-gradient {
    background-image: linear-gradient(to right, var(--tw-gradient-stops));
  }

  .text-shadow {
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
  }
}
```
