---
description: By Cristóvão Sampaio (1201029)
---

# Lazy Documentation Smell

## Defining Lazy Documentation

**Documentation is categorised as ‘Lazy’ if it lacks the necessary information to convey to the readers.** In many cases, it is seen that the documentation does not contain any extra information except what can be perceived directly from the function name. Hence, this kind of documentation does not have much to offer to the readers. [\[1\]](lazy-documentation-smell.md#references)&#x20;

From the five documentation smells examined in the article "Automatic Detection of Five API Documentation Smells: Practitioners’ Perspectives" [\[1\]](lazy-documentation-smell.md#references), lazy documentation was revealed to be both the most common and most problematic smell, as 90% of the participants labelled it as problematic and frequent. It is possible to conclude that when this documentation smell is present, it hinders the developer, blocking them from using the API correctly.

An example of Lazy Documentation can be seen in Figure 1, which shows an example where the documentation explains the same that can be concluded, simply by looking at the function name itself.

<figure><img src=".gitbook/assets/Lazy Docs.png" alt=""><figcaption><p>Figure 1 - Lazy Documentation Example <a href="lazy-documentation-smell.md#references">[1]</a> </p></figcaption></figure>

In a study by Martin P. Robillard, where developers were interviewed about the obstacles they faced when trying to learn a new API, the most prominent issue was the lack of information and examples [\[2\]](lazy-documentation-smell.md#references), which further proves that Lazy Documentation is the most troublesome and frequent documentation smell.

## The Potential of Large Language Models and Generative AI tools

### Potential for Detecting Lazy Documentation



### Potential for Correcting Lazy Documentation



### Potential for Providing Examples of Lazy Documentation



## References

{% embed url="https://ieeexplore.ieee.org/abstract/document/9425926" %}
\[1] Automatic Detection of Five API Documentation Smells: Practitioners’ Perspectives
{% endembed %}

{% embed url="https://ieeexplore.ieee.org/abstract/document/5287006" %}
\[2] What Makes APIs Hard to Learn? Answers from Developers
{% endembed %}

{% embed url="https://dl.acm.org/doi/abs/10.1145/3377811.3380405?casa_token=QJKHxSIFtSsAAAAA:s4EfnUnh1CQ4RrzzmKsYZT4mKdsfi8yVCfIv_xruGu9TazcPwiJxTDkSILZaMo747J4yL0PTfrt0" %}
Software Documentation: The Practitioners’ Perspective
{% endembed %}
