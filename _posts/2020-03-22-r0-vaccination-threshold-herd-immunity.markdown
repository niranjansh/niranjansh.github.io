---
layout: post
title:  "R0, vaccination threshold, and herd immunity"
categories: covid19
---

<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

In the movie Contagion (2011), Dr. Erin Mears (played by Kate Winslet), an [Epidemic Intelligence Service (EIS)][eis] officer with the CDC, provided a brief but clear explanation of $$R_0$$ in under 2 minutes. This post is a deeper dive into this number and related concepts that have resurfaced again due to COVID-19. 

The **basic reporduction number ($$R_0$$)**, pronounced R-naught, of a disease is the number of people that are expected to get the disease from one contagious person. [$$R_0$$ for measles][r0_measles] ranges from 12 to 18, which means that each person with measles could on average infect 12-18 others in a population that is completely susceptible. The 1918 Influenza epidemic had an [$$R_0$$][r0_influenza] of 1.2-1.6. Preliminary [estimates for COVID-19][r0_covid19] put the $$R_0$$ estimates at between 2.06 and 2.52. $$R_0$$ depends on a number of factors, one of which is population density. For the [2009 H1N1 pandemic][r0_h1n1], $$R_0$$ in schools ranged from 2.8 to 16.9 compared to 1.2-2.4 in community settings. 

How exactly is $$R_0$$ derived? There are [several different approaches][r0_derivation] to derive it. We will instead take a simplification of a [simple approach][r0_sir] to understand it, one that I came across in the book [The Model Thinker][model_thinker] by [Scott E. Page][scott_page] which replaces continuous time values and derivatives with a discrete approach that is easier to understand[^1] . 

In this approach, to understand $$R_0$$ we first need to understand the factors that drive the spread of contagion and a model that uses these factors to estimate the number of people infected at any given time since the first infection. 

The factors that influence how quickly a disease spreads depends among others, on how likely someone with the disease is to come in contact with others i.e. **the contact probability $$P_{contact}$$**, and how likely they are to spread the disease when the contact occurs i.e. **the spread probability $$P_{spread}$$**. The spread is held back by the **recovery rate $$P_{recover}$$** i.e. the probability that those infected recover. 

The **SIR (Susceptible, Infected, Recovered) model** is a simple model that uses the above probabilities to come up with an estimate of the number of people infected at a future time step ($$I_{t+1}$$) given the number of those infected at present ($$I_t$$)

$$ I_{t+1}=I_t + P_{contact}.P_{spread}.\frac{I_t}{N_{POP}}.S_t - P_{recover}I_t$$

In the above model, $$N_{POP}$$ is the size of the relevant population i.e. people that can potentially catch the disease, and $$S_t$$ is the population of those susceptible at a given time instant $$t$$ i.e. the fraction of the population that has still not caught the disease.

Let $$I_0$$ be the initial number of infected people. The number of those infected at time instant 1 is: 

$$I_1 = I_0 + P_{contact}.P_{spread}.\frac{I_0}{N_{POP}}.S_0 - P_{recover}I_0$$

Approximating $$S_0$$, the number of those susceptible at time 0 to be the population size $$N_{POP}$$, we have

$$I_1 =I_0 + P_{contact}.P_{spread}.I_0 - P_{recover}I_0$$ 

$$    =I_0.(1+P_{contact}.P_{spread}-P_{recover})$$

Therefore the number of infected cases increases if $$P_{contact}.P_{spread} \geq P_{recover}$$. In other words, if we define the **basic reporduction number ($$R_0$$)** as:

$$R_0 = \frac{P_{contact}.P_{spread}}{P_{recover}}$$

then, if $$R_0$$ < 1 then the disease will recede and disappear over time, however if $$R_0 > 1$$ then the disease is likely to spread to an increasing number of people over time. 

The implications of this are important. In the absence of any vaccination, the above model suggests that the way to reduce spread is to reduce the contact probability $$P_{contact}$$ which in the case of COVID-19 can be achieved through measures such as social distancing, and to reduce the spread probability $$P_{spread}$$ given contact, achieved through measures such as sneezing into one's elbows instead of one's hands, and washing hands thoroughly. 

How about if we have a vaccine? Let $$V$$ represent the **vaccination threshold** i.e. the propotion of people vaccinated. Consequently the disease can now only spread to the proportion of the population that are not vaccinated i.e. $$(1-V)$$. We update our equation for the number of those infected at time instant 1 ($$I_1$$) as below:

$$I_1 =I_0 + P_{contact}.P_{spread}.I_0.(1-V) - P_{recover}I_0$$ 

This means that the spread of the disease will reduce over time if $$P_{contact}.P_{spread}.I_0.(1-V) < P_{recover}I_0$$ i.e. if 

$$R_0(1-V)\leq1$$

Rearranging the above, we get the following equation for the vaccination threshold to avoid the growth of a pandemic.  

$$ V \geq \frac{R_0-1}{R_0} $$

We can now plug in the value of $$R_0$$ for the different diseases to find out what proportion of the population needs to be vaccinated to avoid the spread of the pandemic. For example, for COVID-19 with an $$R_0$$ value of 2.5, we would need $$(2.5-1)/2.5$$  or 60% of the population to be vaccinated to control the spread of the pandemic. For measles with an $$R_0$$ of 15, the vaccination threshold is $$(15-1)/15$$ or 93.3%. Higher the $$R_0$$, higher the proportion of the at-risk population that needs to be vaccinated. 

It follows from the above that if the at-risk population is vaccinated to the level at or above the vaccination threshold, then the rest even if unvaccinated tend to be safe. This is referred to as **herd immunity**.The reasons for not getting vaccinated may vary by disease. For measles, there are those that prefer not to get vaccinated due to perceived side effects and invariably free-ride on the rest of the vaccinated population to avoid the disease. Recently, the UK govermnent came under criticism for suggesting that younger age groups exposed to the virus will have milder illness and will subsequently be immune to it, resulting in a form of  [herd immunity][uk_herd_immunity] that would then keep the rest of the population safe. Dr. Mears would have demurred. They later clarified that this was not what was meant. 

---

[^1]: Chapter 11: Broadcast, Diffusion, and Contagion


[r0]: https://www.imdb.com/title/tt1598778/
[r0_measles]: https://www.thelancet.com/journals/laninf/article/PIIS1473-3099(17)30307-9/fulltext
[r0_influenza]: https://www.weforum.org/agenda/2020/01/coronavirus-flu-healthcare-symptoms/
[r0_covid19]: https://www.ncbi.nlm.nih.gov/pubmed/32097725
[r0_h1n1]: https://www.who.int/influenza/resources/research/research_agenda_influenza_stream_2_limiting_spread.pdf
[r0_derivation]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6670001/
[r0_sir]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3935673/
[model_thinker]: https://www.basicbooks.com/titles/scott-e-page/the-model-thinker/9780465094639/
[uk_herd_immunity]: https://www.theatlantic.com/health/archive/2020/03/coronavirus-pandemic-herd-immunity-uk-boris-johnson/608065/
[scott_page]: https://sites.lsa.umich.edu/scottepage/bio/
[eis]: https://www.cdc.gov/eis/index.html
[george_box]: https://en.wikipedia.org/wiki/All_models_are_wrong


