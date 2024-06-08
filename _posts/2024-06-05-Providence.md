---
title: "Providence"
date: 2024-06-05
categories: [Libraries]
tags: [open_source, javascript, typescript, react, redux, state_management]
description: "A state management library that brings the safety of Redux to mere mortals."
image:
  path: /assets/img/posts/providence.jpg
  alt: A photo of the Eye of Providence as featured on the US Dollar.
---

## Abstract

Providence is a library that makes it easy to keep track of state across multiple components in a React project,
and which makes state management for most real-world apps and use cases easy. [Home page here](https://eye-of-providence.readthedocs.io/en/latest/) and [source code here](https://gitlab.com/opencraft/dev/providence/). Here's [a press release](https://opencraft.com/better-state-management-for-react-using-providence/) I wrote when we published the project.

## Role

At the time of writing, I am the sole implementer of Providence. I designed and developed it, wrote its documentation, and built its demo.

## Background

In 2018, when first beginning work on Artconomy, it became apparent that a common pattern was used on nearly every web page: Fetch some JSON-serializable model from the remote server, display it, update it, send the changes back.

Multiple components might need access to the same state for these models in different parts of the hierarchy, and may need to update based on their changes. There was an existing 'solution' for this, Redux and Vuex, but they came with such intense amounts of boilerplate that most teams either wasted immense amounts of time using them or else did whatever they could to avoid them.

A more intuitive solution was needed-- something that felt like working with native JavaScript instead of having to learn an entirely new language. To solve this, an internal set of state management tools was developed for Artconomy. This resulted in dynamically generated Vuex stores with an easy-to-use controller object that could handle the fetching, errors, and updating for any remote model, as well as arrays of models. Oh, and forms, too.

After this initial development, progress was rapid and code was far more readable.

A few years later, OpenCraft needed to launch a new application, [Listaflow](/posts/Listaflow/). It ran across several similar problems, but was being written in React, while Artconomy was written in Vue. A direct port was not possible. However, a re-implementation using Redux as a backend instead of Vuex was.

The code was ported as the 'Eye of Providence State Management Library', and is now used extensively to simplify loading, tracking, and updating remote state.

## Tools/Technologies used

React, Redux, TypeScript, Git, NPM, Jest, Markdown, MkDocs
