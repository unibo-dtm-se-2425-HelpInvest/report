---
title: Home
layout: home
has_children: false
nav_order: 1
---

# Project title

### Author
- [Michele Cucchiaro](mailto:michele.cucchiaro@studio.unibo.it)

## Abstract

The aim of the project is to create a simple tool for simulating the returns of different financial portfolios under different conditions, applying the compound interest. The tool is a web application, that will allow users to choose how much to invest in the portfolio, for how long they want to keep going and what is the risk profile that suits them best. After making these choices, the web application will present a graphical representation of the returns of the portfolio, with three different scenarios (better than expected, as expected and worse than expected).
From the client side, users will be able to:
-	Choose the **base capital** they want to start with
-	Choose how much they want to add to the portfolio as **monthly deposits**
-	Choose for **how many years** they want to invest
-	Choose their **risk profile** (between high, medium and low)
  
On the server side, the Flask framework is used to manage the communications between the backend and the frontend. The Flask framework allows the backend to retrieve the inputs provided by the users, which are used to generate the graphical simulation through the Matplotlib library, and save it in memory as an image, which will be then presented to the user. 

