---
title: "Listaflow"
date: 2024-06-07
categories: [Projects, Web Apps]
tags: [open_source, typescript, python]
description: "Checklists for Remote Teams."
image:
  path: /assets/img/posts/listaflow.jpg
  alt: An image of the Listaflow logo with a blurred screenshot of the application behind it.
---

## Abstract

Listaflow is an app for recurring checklists for teams. It shines at letting fully remote teams complete processes independently without manager intervention and without meetings. [Main website here](https://listaflow.com/), [source code here](https://gitlab.com/opencraft/dev/listaflow/). [Press Release here](https://opencraft.com/what-is-listaflow-and-how-is-it-being-used-by-the-open-edx-community/).

## Role

I was the co-product owner for this project. I directed the technical work, and worked with a UX-focused co-product owner to design the functionality of the application.

## Background

[OpenCraft](https://opencraft.com/) is an all-remote, mostly flat team of Open Source developers primarily focused around the Open edX Platform, an open-source learning management system. They are tapped for heavy customization and large-scale deployments of the platform for prestigious institutions.

OpenCraft would meet every two weeks to plan their sprint. This meeting would last several hours and always required a few team members to join in the early hours of the morning. The team wanted to move to a fully asynchronous planning system, but nothing quite fit their needs.

The project was shelved for an extensive period after initial design, with the team using hacky workarounds from other vendors in the interim. Not long after, its lead left the company and I picked it up, moving it forward.

After reviewing the project and scaffolding the initial backend work, I built a frontend library for its state management, [providence](/posts/Providence/), which was then used by myself and other team members to build the application.

The project was initially considered lower priority by the company-- important, but with the workarounds the company, not urgent.

Things changed.

OpenCraft is an active contributor to the Open edX community. Within the community, several developers across multiple companies had been granted 'Core Contributor' status, allowing them more control over the platform's direction. They had been using Friday.app to coordinate their weekly checkins. However, Friday.app was soon to shut down, leaving the Core Contributors without a way to perform their sprint checkins/retrospectives.

As Listaflow was already designed to do much of what was needed, we rapidly worked to design a few new features to close the gap. We then had two months to build an MVP so that the community could move over to the new tool. Using the resources available, I lead the team to develop and deliver the product an entire sprint before the deadline.

Listaflow continues to be used by the Open edX Core Contributors and OpenCraft to plan their sprints.

## Technologies used

Python, Django, Django REST framework, React, Redux, [Providence](/posts/Providence/), [Short Stuff](/posts/Short-stuff/), Kubernetes, Helm, Terraform/Tofu, Make, Bash, Docker, Git
