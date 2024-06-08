---
title: "Short Stuff"
date: 2024-06-03
categories: [Libraries]
tags: [open_source, javascript, typescript, python]
description: "A library for generating short codes useful in URLs."
image:
  path: /assets/img/posts/short-stuff.jpg
  alt: A photo of a short stack of pancakes. Photo by Sydney Troxell via Pexels
---

## Abstract

Short-stuff is a library for generating and translating shortcodes. It piggy-backs on UUID's byte format so
that it can be used in databases and in software that already understands UUID4. [Source code here](https://github.com/Artconomy/short_stuff).

## Role

I was the initial designer and implementor in Python.

## Background

While working on [Artconomy](/posts/Artconomy/), I found a need to generate non-sequential IDs for use in the database. PostgresSQL natively supported UUIDs. However, using these in a URL would be long and unwieldy. They also look weird compared to most shortcodes I've seen, such as YouTube video URLs.

It occured to me that if the UUIDs were transcribed as base64, they could look more like the IDs I'd seen on YouTube, and it's possible that said VideoIDs were, in fact, base64ed ID numbers. However, running base64 on a UUID still produces a very long string, and the string is not entirely URL native.

Short-stuff gets around these limitations by doing a couple of additional substitutions on the characters and zeroing out leading bytes in the UUID. This means less possible unique combinations, but this is OK for a single website. After all, UUID is designed to have enough possibilities that generating 1 billion of them a second for 100 years would be needed to have a 50% chance of encountering a collision.

Short-stuff includes an optional Django field for easy use in Django-based projects.

### TypeScript Port

After using it successfully in Artconomy, [OpenCraft](https://opencraft.com/) ported the Library to TypeScript on the frontend in order to support its use within [Listaflow](/posts/Listaflow/).

## Technologies used

* Python
* TypeScript
* Django
* Git
* PyPi
* NPM
