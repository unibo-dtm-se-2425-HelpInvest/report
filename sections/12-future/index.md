---
title: Future work
has_children: false
nav_order: 13
---

# Known issues and future work

This section should describe:
- What is missing
- What does not work as it should
- Potential future developments to improve/expand the software

N.B. Be honest, no inpact on the final mark.


- only one image
- too simple
- plots can look better
- thousand separator
- table with numbers

## What is missing
One thing that is missing, which I was not able to add, and which may be dertimental to the application's accessibility, is the thousand's separator on the plot. When visualising the plot, the numbers displayed on the **Y axis**, which measure the value of the protfolio overtime, the numbers over one thousand are displayed in the form *1000*, rather than *1.000*, which may make it difficult for users to read the actual value of their portfolio, especially when dealing with values in the order of hundreds of thousands or millions.

## What does not work as it should
One of the biggest possible issues is that every time a new plot is generated, it will be overwritten on the old one, therefore only one plot, the one in use, can be accessed at teh time, making it impossible to look at old ones without having to generate them from scratch.
Another issue, though less prominent, is that when the application is dealing with either long period of time (thousands of years) or extremely high starting capitlas (in the order of the billions), launching the generation of the plot will end up crashing the application.


## Potential future developments
For the future, it would be interesting to replicate real-world returns in real time, for instance of indexes such as the S&P500, rather than using a predetermined return rate hardcoded in the backend. Another possible improvement, could be to add a table which integrates the plot, givign a numerical representation of the tren of the investment. An example of the table could look like this:

| Years | Invested capital | Inflation adjusted | Low Return | average return | High return |
|-----|------|-----|-----|-----|-----|
| 1 | 1.000 | 1.000 | 1.000 | 1.000 | 1.000 |
| 2 | 2.200 | 2.156 | 2.211 | 2.222 | 2.233 |
| 3 | 3.400 | 3.289 | 3.428 | 3.456 | 3.484 |
| 4 | 4.600 | 4.399 | 4.651 | 4.702 | 4.756 |

The table shows an example of hot it would look likfe for a low risk scenario, with an initial capital of 1.000 euros and mnothly investments of 100 euros. 



















