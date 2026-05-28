---
title: "A Weekend with Vim Motions"
collection: musings
permalink: /musings/weekend-with-vim
date: 2026-05-10
excerpt: "How I spent a weekend forcing myself to use Vim keybindings, and what I learned."
---

Last weekend I decided to finally commit to learning Vim motions. Not full Vim — I'm not *that* brave — but the keybindings via a VSCode extension. Here's how it went.

## Day 1: Pain

Everything took three times longer. I kept reaching for the mouse out of muscle memory. `hjkl` felt unnatural. I accidentally entered visual mode more times than I care to admit.

The only thing that kept me going was `u` for undo.

## Day 2: Glimmers of Hope

Something clicked on day two. I started thinking in **motions** rather than mouse movements:

- `ciw` — change inner word. Suddenly renaming variables felt *fast*.
- `f` + character — jump to the next occurrence of a character on the line. Beautiful.
- `dd` then `p` — moving lines around without touching the mouse.

The key insight: Vim isn't about memorizing commands. It's about composing a **language** of text manipulation. `d` (delete) + `i` (inner) + `w` (word) = "delete inner word." Once you see the grammar, new commands become predictable.

## What I'm Keeping

I'm not going full Vim. But I'm keeping:
- `hjkl` for navigation (my right hand thanks me)
- `ci` + delimiter for changing inside quotes/brackets/parentheses
- `/` for in-file search (way faster than Ctrl+F somehow)
- `.` to repeat the last action

## The Meta-Lesson

Learning Vim is a lot like research: the first day you feel like you're going backwards, the second day you see the structure, and by the end you wonder how you ever worked without it.
