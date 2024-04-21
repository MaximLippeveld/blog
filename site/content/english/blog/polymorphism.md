---
title: "Expert Django: Integrating polymorphism with existing data"
meta_title: ""
description: "this is meta description"
date: 2024-04-21T20:00:00.000Z
image: "/images/image-placeholder.png"
categories: ["Django", "Python"]
author: "Maxim Lippeveld"
tags: ["nextjs", "tailwind"]
draft: true
---

Modelling data for software is an ever evolving process: requirements change, new insights emerge, a
company changes it's focus, ... Sometimes new requirements can lead to big refactors in the code
base. In this blog post, we'll focus on adding polymorphism to an existing data model. First, we'll
go over why doing this could lead to data loss, and secondly, we'll set up an example to show the
solution.

Say we're implementing a basic software for a bike shop that wants to keep track of the repairs that
come in. At first the shop was only repairing regular city bikes, and this was modelled with the
`Bike` class. Now, some years later the bikeshop has expanded and they also offer repairs for cargo
bikes. They want this to be reflected in the software, while keeping all their data that is
currently in the platform.

It was chosen to implement this new functionality with inheritance: the concrete `CargoBike`, and
`CityBike` will inherit from the `Bike` base class as shown in the UML-diagram below. 




