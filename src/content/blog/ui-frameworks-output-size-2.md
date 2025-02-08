---
title: "UI frameworks output size: how Svelte is even possible"
description: "Why React weights so much more than Svelte"
pubDate: "Feb 8 2025"
categories: ["UI framework", "JavaScript"]
author: "sinskiy"
language: "english"
---

I initially set out to write a deep dive into the source code and output code of React and Svelte. However, I realized that the post was becoming overly boring and lengthy, so here is a summary of the key takeaways I found out:

- Svelte is _essentially_ a modern React with no virtual DOM and some compile-time optimizations
- Svelte 5 runes reduces compile-time _magic_: the framework now mostly transpiles component files into pure functions, renames stuff like `$effect` -> `user_effect`/`template_effect`, and uses `set` and `get` for `$state`
- React, by contrast, only compiles JSX into JavaScript
- React’s larger size is likely due to its age and popularity. Virtual DOM doesn't help either
- I couldn't figure out how Svelte achieves its impressive compression rates
