---
title: API Reference

language_tabs:
  - shell
  - haskell
  - html

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the try-reflex docs! You can use this guide to get information on building various web gui elements with Reflex-dom.

We have language bindings in Shell, Haskell, and HTML! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example documentation page was created with [Slate](http://github.com/tripit/slate). Feel free to submit pull requests to update the information.

# General Overview

> To start, import Reflex:

```haskell
import           Reflex.Dom
```

```html

```

```shell
# Within try-reflex, you can just run the script to install dependencies:

./try-reflex
```

> Make sure you've installed GHCJS.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace `meowmeowmeow` with your personal API key.
</aside>

# CSS

## Buttons

### Button Tags
### Submit Button

### Close Button

### Button State

Active State 

Disabled State

## Images


### Thumbnails


# Components

## Dropdowns


## Button Groups

## Button Dropdowns

## Input Groups

## Navs

## Navbar

## Pagination

## Labels

## Alerts

## Panels

## Tabs 


# Media Objects

## Video Player Embed

## Image Carousel

## Document embed

# More Interactions

## Transitions

## Modals

## Popover

## Collapse



# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Isis",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/3"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Isis",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the cat to retrieve

