---
description: By Hugo Silva (1231428)
---

# Fragmented Documentation Smell

## Definition

Fragmented Documentation Smells refer to issues that arise from disorganization or incompleteness, leading to poor developer experience. Smells helps us identify problems within documentation and understand and create documentation more clear and effective.

1. **Scattered Information:** Information related to a single concept or idea is dispersed throughout the documentation instead of being organized in a single block of information. It makes the search for all the necessary details more complex and tiresome.
2. &#x20;**Inconsistent Terminology:** If different parts of the documentation use different terms and naming conventions for the same concepts, that makes the document more complex and harder to understand.
3. &#x20;**Incomplete Examples:** This happens when well... examples are incomplete. Code blocks have incomplete implementation, written examples have incomplete context or none at all. This makes it harder for developers to test the API described and to understand its functionality to its fullest.
4. **Outdated Information:** Outdated information in an API can lead to wrong implementations by the developers, creating a discrepancy between the documentation and the actual API behavior.
5. **Missing Links:** The documentation can benefit from well used hyperlinks that facilitate the navigation and search process of the documentation. Without these shortcuts, the developer is forced to manually search the whole document to get to the desired information.
6. **Redundant Information:** Including repeating information without clear reasoning can lead to inconsistencies if one of those sections is updated and the others not.
7. **Poor Structure and Navigation:** The lack of a clear structure and navigation flow makes it difficult to developers to follow and understand the documentation.
8. **Sparse Descriptions:** Description of the API endpoints are too brief or general.
9. **Lack of context:** Documentation that fails to provide the necessary reasons for its existence only tend to cause confusion among developers that use the documentation. This leads developers into guessing and making incorrect assumptions about the documented API.
10. **Missing Cross-References:** Similar to missing links, not connecting related functionalities through navigation systems can cause developers to hunt the necessary information unnecessarily and without guidance.

## Large Language Models and Generative AI tools

The section explores the potential of Large Language Models and Generative AI tools, such as ChatGPT, in detecting, correcting and improving the examples given in the Contest Group of resources in PokéAPI, taking into consideration the Fragmented Documentation smell already described.

{% file src=".gitbook/assets/ContestGPTResponse.pdf" %}

The .pdf file above contains a conversation with ChatGPT that starts by presenting the Contest Group resources from PokéAPI, as well as the Fragmented Documentation Smell. The conversation also contains the detected, corrected, and improved documentation examples of the Tangled Documentation Smell on the Contest resource.

### Potential in Detecting

When asked to detect possible problems with the API documentation following the rules imposed by the Fragmented Documentation Smell Framework, ChatGPT identified the following issues:

**Scattered Information**

* ChatGPT deems that dividing Contest into three groups of endpoints can cause difficulties when searching for the necessary resources.
* Both contest effects and super contest effects are documented separately. This separation can make it harder for users to understand the overall impact of moves in contests and super contests without cross-referencing both sections, since both are very similar

**Inconsistent Structuring**

* The structure of the JSON responses for Contest Effects and Super Contest Effects are similar but not identical. This difference can cause confusion as users may expect a uniform structure when dealing with similar types of data.

**Redundancy and Overlap**

* Some information, such as language resources, is repeated across different sections. This redundancy can make the documentation harder to navigate and maintain.
* Each effect and flavor text entry includes language data, which is repeated across various entries and sections.

**Navigation Difficulties**

* There is no centralized location where users can get an overview of all contest-related information. Users must navigate to each endpoint individually to piece together a full understanding of the contests.

Although most of the problems marked above are correctly assessed, some don't make much sense if seen in a organizational manner. This is caused because ChatGPT follows strictly the rules imposed by the smell and fails to evaluate the overall user experience.&#x20;

For example, the idea that dividing the Contest Resources into three well defined endpoints is referred as a bad organization scheme, when in reality it helps with the research efficiency from a user point of view. The use of the language schema in many of the endpoints is also a "necessary evil" when evaluating the whole scope of the endpoints and the different communications needed with other resources.

Still, ChatGPT points out good flaws that the current documentation has. Those flaws can be turned into improvements to the structure of the documentation.&#x20;

### Potential in Documentation Improvement

The improvements suggested by ChatGPT to improve the documentation structure and read flow are as follows:

**Unified Contest Documentation**

* Create a central page that gives an overview of all contest-related data, with links to each specific endpoint (Contest Types, Contest Effects, Super Contest Effects).
* Consider combining the contest effects and super contest effects into a single section with clear subcategories, making it easier for users to understand the relationships and differences.

**Consistent Data Structure**

* Ensure that similar types of data (such as effects) have a consistent structure across different endpoints to reduce confusion.
* Utilize shared data types for common elements like language and flavor text to minimize redundancy.

**Enhanced Navigation**

* Provide clear links between related sections within the documentation, so users can easily jump from one related piece of information to another.
* Include summary tables or charts that compile key information from different endpoints, allowing users to get a quick overview without navigating away from the page.

**Comprehensive Examples**

* Offer comprehensive examples that show how data from different endpoints interact in a real-world context, such as a move's effects in both regular and super contests.
