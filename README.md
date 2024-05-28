---
description: By Marta Ribeiro (1201592)
---

# Tangled Documentation Smell

## Definition

Tangled documentation smells refer to issues in software documentation that make it confusing, difficult to understand, or maintain. These "smells" are indicators of poor documentation practices, much like code smells in software development highlight problematic areas in the codebase.

1. **Inconsistent Terminology**: Using different terms for the same concept, which can confuse readers and make the documentation harder to follow.
2. **Outdated Information**: Documentation that is not regularly updated and contains obsolete information.
3. **Redundancy**: Repeating the same information in multiple places, which can lead to inconsistencies and increase maintenance effort.
4. **Poor Structure**: Lack of a clear, logical structure that makes it difficult for users to navigate and find the information they need.
5. **Incomplete Information**: Missing critical details, leaving users without the necessary information to understand or use the software effectively.
6. **Overly Complex Language**: Using unnecessarily complex language or jargon that makes the documentation hard to understand for the target audience.
7. **Lack of Examples**: Failing to provide practical examples or use cases that illustrate how to use the software.

## Large Language Models and Generative AI tools

The potential of Large Language Models and Generative AI tools, such as ChatGPT, in detecting, correcting and improving examples of API tangled documentation smells is explored in this section, with a connection to the resource Berries from the PokeAPI.

{% file src=".gitbook/assets/ChatGPT Data Export.pdf" %}
ChatGPT Data Export - Berry Attributes Summary
{% endfile %}

The .pdf file above contains a conversation with ChatGPT that starts by presenting the Berries resource from PokeAPI, as well as the Tangled Documentation Smell. The conversation also contains the answers of ChatGPT to Detecting, Correcting, and Improving Examples of the Tangled Documentation Smell on the Berries resource.

### Potential in Detecting

Regarding the detection of Tangled Documentation Smells in the documentation for the Berries resource, ChatGPT identified the following issues:

#### Inconsistent Terminology

* There might be inconsistencies in naming conventions, such as "growth\_time" vs. "time to grow".

#### Outdated Information

* The documentation may lack details on how often it's updated or checked for accuracy.

#### Redundancy

* Repetition of the explanation of common terms across different sections.

#### Poor Structure

* Information is scattered without a clear flow, which can make it difficult to follow.

#### Incomplete Information

* Missing context or explanations for certain terms, such as what "natural\_gift\_power" means in practical terms.

#### Overly Complex Language

* Use of jargon without adequate explanation.

#### Lack of Examples

* Absence of practical examples on how to use the endpoints effectively.

#### Conclusion

ChatGPT correcly detects Tangled Documentation Smells, following the definition provided. Only one smell is detected for each of the Tangled Documentation Smells examples provided in the definition, however, using a different prompt could result on more smells being identified.

### Potential in Correcting

Regarding the correction of Tangled Documentation Smells in the documentation for the Berries resource, ChatGPT suggested the following corrections:

**Title and Introduction**

**Current**:

```sql
Berries (group)
Berries (endpoint)
Berries are small fruits that can provide HP and status condition restoration, stat enhancement, and even damage negation when eaten by Pokémon. Check out Bulbapedia for greater detail.
```

**Improved**:

```csharp
### Berries Endpoint

Berries are small fruits in the Pokémon world that provide various benefits such as HP restoration, status condition recovery, stat enhancement, and damage negation when eaten by Pokémon.

**Note**: For more detailed information, refer to [Bulbapedia](https://bulbapedia.bulbagarden.net/wiki/Main_Page).
```

**Endpoint Description**

**Current**:

```bash
GET https://pokeapi.co/api/v2/berry/{id or name}/
```

**Improved**:

```bash
### GET Berries

**Endpoint**: `GET https://pokeapi.co/api/v2/berry/{id or name}/`

Retrieve information about a specific berry by its `id` or `name`.
```

**JSON Response Example**

**Current**:

```json
{
  "id": 1,
  "name": "cheri",
  ...
}
```

**Improved**:

```json
{
  "id": 1,
  "name": "cheri",
  "growth_time": 3,
  "max_harvest": 5,
  "natural_gift_power": 60,
  "size": 20,
  "smoothness": 25,
  "soil_dryness": 15,
  "firmness": {
    "name": "soft",
    "url": "https://pokeapi.co/api/v2/berry-firmness/2/"
  },
  "flavors": [
    {
      "potency": 10,
      "flavor": {
        "name": "spicy",
        "url": "https://pokeapi.co/api/v2/berry-flavor/1/"
      }
    }
  ],
  "item": {
    "name": "cheri-berry",
    "url": "https://pokeapi.co/api/v2/item/126/"
  },
  "natural_gift_type": {
    "name": "fire",
    "url": "https://pokeapi.co/api/v2/type/10/"
  }
}
```

**Attributes Description**

**Current**:

```sql
Berry (type)
Name	Description	Type
id	The identifier for this resource.	integer
name	The name for this resource.	string
growth_time	Time it takes the tree to grow one stage, in hours. Berry trees go through four of these growth stages before they can be picked.	integer
max_harvest	The maximum number of these berries that can grow on one tree in Generation IV.	integer
...
```

**Improved**:

```sql
### Berry Attributes

- **id**: (integer) The unique identifier for the berry.
- **name**: (string) The name of the berry.
- **growth_time**: (integer) Time in hours for the berry tree to grow one stage. Berry trees go through four growth stages before they can be picked.
- **max_harvest**: (integer) Maximum number of berries that can be harvested from one tree.
- **natural_gift_power**: (integer) The power of the move "Natural Gift" when used with this berry.
- **size**: (integer) The size of the berry in millimeters.
- **smoothness**: (integer) The smoothness value used in making Pokéblocks or Poffins.
- **soil_dryness**: (integer) The rate at which the berry dries out the soil.
- **firmness**: (NamedAPIResource) The firmness type of the berry, used in making Pokéblocks or Poffins.
- **flavors**: (list of BerryFlavorMap) List of flavors and their potency associated with this berry.
- **item**: (NamedAPIResource) Reference to the item data for this berry.
- **natural_gift_type**: (NamedAPIResource) The type of the "Natural Gift" move inherited when using this berry.
```

**Examples**

**Current**:

No examples provided.

**Improved**:

```csharp
### Example Request

To get information about the Cheri Berry:
```

```bash
GET https://pokeapi.co/api/v2/berry/1/
```

```csharp
### Example Response
```

```json
{
  "id": 1,
  "name": "cheri",
  "growth_time": 3,
  "max_harvest": 5,
  "natural_gift_power": 60,
  "size": 20,
  "smoothness": 25,
  "soil_dryness": 15,
  "firmness": {
    "name": "soft",
    "url": "https://pokeapi.co/api/v2/berry-firmness/2/"
  },
  "flavors": [
    {
      "potency": 10,
      "flavor": {
        "name": "spicy",
        "url": "https://pokeapi.co/api/v2/berry-flavor/1/"
      }
    }
  ],
  "item": {
    "name": "cheri-berry",
    "url": "https://pokeapi.co/api/v2/item/126/"
  },
  "natural_gift_type": {
    "name": "fire",
    "url": "https://pokeapi.co/api/v2/type/10/"
  }
}
```

#### Conclusion

The corrections suggested by ChatGPT don't mention the Tangled Documentation Smells examples provided in the definition. The suggestions also don't relate to the smells identified before. However, the corrections suggested are still relevant and eliminate some of the Tangled Documentation Smells.

### Potential in Improving Examples

Regarding the improvement that should be made to each example of the Tangled Documentation Smells, in the documentation for the Berries resource, ChatGPT provided the following improvements:

1. **Consistent Terminology**: Ensure all terms are used consistently.
2. **Update Regularly**: Add a note about the last update.
3. **Remove Redundancy**: Consolidate repeated information.
4. **Improve Structure**: Organize sections logically.
5. **Complete Information**: Provide thorough explanations.
6. **Simplify Language**: Use clear, simple language appropriate for the target audience.
7. **Add Examples**: Include practical examples and use cases.

#### Conclusion

ChatGPT correctly suggests how to make improvements for each of the Tangled Documentation Smells examples provided in the definition. The improvements suggested are relevant and should eliminate the Tangled Documentation Smells if implemented correctly.

### Potential Conclusion

As can be seen in the conclusions made on the previous sections, ChatGPT shows high potential in detecting, correcting and improving examples of API tangled documentation smells.
