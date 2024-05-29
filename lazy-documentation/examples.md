---
description: By Cristóvão Sampaio - 1201029@isep.ipp.pt - 29/08/2024
---

# Examples

Using the PokéAPI as an example for a context of what could be API Documentation, it is possible to analyse a hypothetical scenario of Lazy Documentation in PokéAPI.

{% hint style="info" %}
This example was generated using ChatGPT and is meant to be used only as demonstration porpuses of what could be a Lazy Documentation, and then how to improve it, it doesn't reflect the PokéAPI in any way.&#x20;

PokéAPI in this case is only utilised as a context for an API.
{% endhint %}

## Lazy documentation

### The Example

#### Pokémon

`/pokemon/{id}`

Fetched a Pokémon by its ID.

Parameters

| Name | Type    | Description           |
| ---- | ------- | --------------------- |
| Id   | integer | The ID of the Pokémon |

**Response**

{% tabs %}
{% tab title="200" %}
```
Returns a Pokémon Object
```
{% endtab %}
{% endtabs %}

### The Issues

* **Lack of Detailed Description:** The description is too brief and doesn't explain what kind of information will be returned for the Pokémon.
* **Incomplete Parameters Information:** The `id` parameter is mentioned but there's no information on the acceptable range or format for the ID.
* **No Example Request:** No example shows how to request this endpoint.
* **No Example Response:** There is no example of what the JSON response looks like.
* **Missing Error Handling Information:** There is no information on possible error codes or messages that might be returned if the request fails.

## Improved Documentation

#### Pokémon

<mark style="color:blue;">`GET`</mark> `/pokemon/{id}`

Fetches detailed information about a Pokémon by its unique ID. This includes its name, types, abilities, stats, and more**.**

**Parameters**

<table><thead><tr><th width="110">Name</th><th width="113">Type</th><th width="133">Is Required</th><th>Description</th></tr></thead><tbody><tr><td>Id</td><td>integer</td><td>Yes</td><td>The unique identifier of the Pokémon. Acceptable values range from 1 to the total number of Pokémon available in the PokéAPI database.</td></tr></tbody></table>

**Example Request**

```http
GET /pokemon/1
```

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "id": 1,
  "name": "bulbasaur",
  "base_experience": 64,
  "height": 7,
  "is_default": true,
  "order": 1,
  "weight": 69,
  "abilities": [
    {
      "is_hidden": false,
      "slot": 1,
      "ability": {
        "name": "overgrow",
        "url": "https://pokeapi.co/api/v2/ability/65/"
      }
    },
    {
      "is_hidden": true,
      "slot": 3,
      "ability": {
        "name": "chlorophyll",
        "url": "https://pokeapi.co/api/v2/ability/34/"
      }
    }
  ],
  "types": [
    {
      "slot": 1,
      "type": {
        "name": "grass",
        "url": "https://pokeapi.co/api/v2/type/12/"
      }
    },
    {
      "slot": 2,
      "type": {
        "name": "poison",
        "url": "https://pokeapi.co/api/v2/type/4/"
      }
    }
  ],
  // Additional fields...
}

```
{% endtab %}

{% tab title="404" %}
Pokémon not found.
{% endtab %}
{% endtabs %}
