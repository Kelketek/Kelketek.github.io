---
title: "Building a Raspberry Pi Kube Cluster"
date: 2025-08-05
categories: [Writing, Blogs]
tags: [open_source, kubernetes, devops, ansible, ceph]
description: "Building a home laboratory Kubernetes cluster for fun and profit."
image:
  path: /assets/img/beep.png
  alt: Beep boop
  caption: Beeeeeep booop
---

Kubernetes is a bit of a monster. The first time you learn about it, it bends your mind trying to make sense of all of its abstraction and indirection. Once you 'get it', however, you might find yourself wishing you had its benefits for your own small projects, without paying a fortune in cloud hosting and hardware. That's where I found myself lately-- wanting to deploy some small applications for my homelab in a more redundant configuration.

Sure, it's 'overkill', but it's a lot of fun, and I'd already done the hard part of learning how to administrate a Kubernetes cluster. I wanted to learn it deeper-- enough that I could conceivably consult on setting it up for clients who wanted their own 'internal cloud.' That meant building my own Kubernetes cluster at home. Now, I'm not made of money, and I just have a little network closet to work with, so I thought 'Why not just grab a few Raspberry Pis and see what I can do?'

There are a few goals for this project:

* I should be able to run real Kubernetes loads across multiple devices
* The disk storage claims should have some redundancy
* It should allow me to replace or add Pis without having to worry about what workload was on which machine.

This will have a few challenges. We'll go through them one by one, but first we need to set up the hardware. Here's my bill of materials:

| Item                        | Required? | Quantity | Description                                    |
|-----------------------------|:---------:|----------|------------------------------------------------|
| [Raspberry Pi 4 Model B] |     ✅[^1]     | 3-10     | Small, cheap all-in-one computer boards.       |
| [PoE Hat]                |     ❌[^2]     | 1 per Pi | Power over Ethernet adapter card for Pi.       |
| [Ethernet patch cables]  |     ✅[^3]     | 1 per Pi | Standard Network cable. Buy or make.           |
| [Raspberry Pi Network Rack] |     ❌[^4]     | 1        | For clean organization and ventilation of Pis. |
| [SD Micro Storage Cards] (512GB) |     ✅[^5]     | 1 per Pi | Disk storage for Pi.                           |

See the footnotes for advice on how you might substitute based on your own needs.

[Raspberry Pi 4 Model B]: https://www.amazon.com/dp/B0899VXM8F/
[PoE Hat]: https://www.amazon.com/dp/B08CVDQWXF/
[Raspberry Pi Network Rack]: https://www.amazon.com/dp/B0F6NMNJQ7/
[Ethernet patch cables]: https://www.amazon.com/dp/B0CQXG1WPC
[SD Micro Storage Cards]: https://www.amazon.com/dp/B0B7NVXLLM

[^1]: You can get later models, but the cost goes up significantly. This model looked like the sweet spot for what we intend to do. Note that if you pick a different model, you will need to ensure any accessories, such as the PoE Hat and Rack, or external case if you choose one, match with the model you select.
[^2]: Power Over Ethernet is preferable here, but assumes you have a Power over Ethernet switch. These have come down greatly in price in recent years and can be had quite affordably second-hand. If your network switch does not have Power over Ethernet, switch, you will need to purchase USB-C power plugs for each Pi instead.
[^3]: It is possible to do this over WiFi, if you hate yourself and think performance is for suckers. I assume my readers at least pretend to value their mental health and mark this as required. You'll need an open switch port available for each Pi.
[^4]: This device requires 2U of space in a server rack. If you don't get this, at least purchasing a basic case for your Pis is strongly advised, as they come as bare boards.
[^5]: You might be able to get away with smaller sizes, but I'd not recommend it. You can always go bigger.
