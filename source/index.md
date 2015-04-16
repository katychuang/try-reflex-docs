---
title: API Reference

language_tabs:


toc_footers:
  - <a href='#'>Download latest Reflex release</a>
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

Use the button classes on an &lt;a>, &lt;button>, or &lt;input> element.

Example:

<a class="btn" href="#" role="button">Link</a>
<button class="btn" type="submit">Button</button>
<input class="btn" type="button" value="Input">
<input class="btn" type="submit" value="Submit">

&lt;a class="btn" href="#" role="button">Link&lt;/a><br/>
&lt;button class="btn" type="submit">Button&lt;/button><br/>
&lt;input class="btn" type="button" value="Input"><br/>
&lt;input class="btn" type="submit" value="Submit">


```html
<a class="btn btn-default" href="#" role="button">Link</a>
<button class="btn btn-default" type="submit">Button</button>
<input class="btn btn-default" type="button" value="Input">
<input class="btn btn-default" type="submit" value="Submit">
```

### Submit Button

<input class="btn btn-default" type="submit" value="Submit">

&lt;input class="btn btn-default" type="submit" value="Submit">

### Close Button

<input class="btn btn-default" type="submit" value="Close">

&lt;input class="btn btn-default" type="submit" value="Close">

### Button State

Active State 

Disabled State

## Images


### Thumbnails


# Components

## Dropdowns

<div class="dropdown">
  <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown" aria-expanded="true">
    Dropdown
    <span class="caret"></span>
  </button>
  <ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu1">
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Action</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Another action</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Something else here</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Separated link</a></li>
  </ul>
</div>
<div class="dropup">
  <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu2" data-toggle="dropdown" aria-expanded="true">
    Dropdown
    <span class="caret"></span>
  </button>
  <ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu2">
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Action</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Another action</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Something else here</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Separated link</a></li>
  </ul>
</div>

<span class="nt">&lt;div</span> <span class="na">class=</span><span class="s">"dropdown"</span><span class="nt">&gt;</span><br/>
  <span class="nt">&lt;button</span> <span class="na">class=</span><span class="s">"btn btn-default dropdown-toggle"</span> <span class="na">type=</span><span class="s">"button"</span> <span class="na">id=</span><span class="s">"dropdownMenu1"</span> <span class="na">data-toggle=</span><span class="s">"dropdown"</span> <span class="na">aria-expanded=</span><span class="s">"true"</span><span class="nt">&gt;</span><br/>
    Dropdown<br/>
    <span class="nt">&lt;span</span> <span class="na">class=</span><span class="s">"caret"</span><span class="nt">&gt;&lt;/span&gt;</span><br/>
  <span class="nt">&lt;/button&gt;</span><br/>
  <span class="nt">&lt;ul</span> <span class="na">class=</span><span class="s">"dropdown-menu"</span> <span class="na">role=</span><span class="s">"menu"</span> <span class="na">aria-labelledby=</span><span class="s">"dropdownMenu1"</span><span class="nt">&gt;</span><br/>
    <span class="nt">&lt;li</span> <span class="na">role=</span><span class="s">"presentation"</span><span class="nt">&gt;&lt;a</span> <span class="na">role=</span><span class="s">"menuitem"</span> <span class="na">tabindex=</span><span class="s">"-1"</span> <span class="na">href=</span><span class="s">"#"</span><span class="nt">&gt;</span>Action<span class="nt">&lt;/a&gt;&lt;/li&gt;</span><br/>
    <span class="nt">&lt;li</span> <span class="na">role=</span><span class="s">"presentation"</span><span class="nt">&gt;&lt;a</span> <span class="na">role=</span><span class="s">"menuitem"</span> <span class="na">tabindex=</span><span class="s">"-1"</span> <span class="na">href=</span><span class="s">"#"</span><span class="nt">&gt;</span>Another action<span class="nt">&lt;/a&gt;&lt;/li&gt;</span><br/>
    <span class="nt">&lt;li</span> <span class="na">role=</span><span class="s">"presentation"</span><span class="nt">&gt;&lt;a</span> <span class="na">role=</span><span class="s">"menuitem"</span> <span class="na">tabindex=</span><span class="s">"-1"</span> <span class="na">href=</span><span class="s">"#"</span><span class="nt">&gt;</span>Something else here<span class="nt">&lt;/a&gt;&lt;/li&gt;</span><br/>
    <span class="nt">&lt;li</span> <span class="na">role=</span><span class="s">"presentation"</span><span class="nt">&gt;&lt;a</span> <span class="na">role=</span><span class="s">"menuitem"</span> <span class="na">tabindex=</span><span class="s">"-1"</span> <span class="na">href=</span><span class="s">"#"</span><span class="nt">&gt;</span>Separated link<span class="nt">&lt;/a&gt;&lt;/li&gt;</span><br/>
  <span class="nt">&lt;/ul&gt;</span><br/>
<span class="nt">&lt;/div&gt;</span><br/>
<span class="nt">&lt;div</span> <span class="na">class=</span><span class="s">"dropup"</span><span class="nt">&gt;</span><br/>
  <span class="nt">&lt;button</span> <span class="na">class=</span><span class="s">"btn btn-default dropdown-toggle"</span> <span class="na">type=</span><span class="s">"button"</span> <span class="na">id=</span><span class="s">"dropdownMenu2"</span> <span class="na">data-toggle=</span><span class="s">"dropdown"</span> <span class="na">aria-expanded=</span><span class="s">"true"</span><span class="nt">&gt;</span><br/>
    Dropdown<br/>
    <span class="nt">&lt;span</span> <span class="na">class=</span><span class="s">"caret"</span><span class="nt">&gt;&lt;/span&gt;</span><br/>
  <span class="nt">&lt;/button&gt;</span><br/>
  <span class="nt">&lt;ul</span> <span class="na">class=</span><span class="s">"dropdown-menu"</span> <span class="na">role=</span><span class="s">"menu"</span> <span class="na">aria-labelledby=</span><span class="s">"dropdownMenu2"</span><span class="nt">&gt;</span>
    <span class="nt">&lt;li</span> <span class="na">role=</span><span class="s">"presentation"</span><span class="nt">&gt;&lt;a</span> <span class="na">role=</span><span class="s">"menuitem"</span> <span class="na">tabindex=</span><span class="s">"-1"</span> <span class="na">href=</span><span class="s">"#"</span><span class="nt">&gt;</span>Action<span class="nt">&lt;/a&gt;&lt;/li&gt;</span><br/>
    <span class="nt">&lt;li</span> <span class="na">role=</span><span class="s">"presentation"</span><span class="nt">&gt;&lt;a</span> <span class="na">role=</span><span class="s">"menuitem"</span> <span class="na">tabindex=</span><span class="s">"-1"</span> <span class="na">href=</span><span class="s">"#"</span><span class="nt">&gt;</span>Another action<span class="nt">&lt;/a&gt;&lt;/li&gt;</span><br/>
    <span class="nt">&lt;li</span> <span class="na">role=</span><span class="s">"presentation"</span><span class="nt">&gt;&lt;a</span> <span class="na">role=</span><span class="s">"menuitem"</span> <span class="na">tabindex=</span><span class="s">"-1"</span> <span class="na">href=</span><span class="s">"#"</span><span class="nt">&gt;</span>Something else here<span class="nt">&lt;/a&gt;&lt;/li&gt;</span><br/>
    <span class="nt">&lt;li</span> <span class="na">role=</span><span class="s">"presentation"</span><span class="nt">&gt;&lt;a</span> <span class="na">role=</span><span class="s">"menuitem"</span> <span class="na">tabindex=</span><span class="s">"-1"</span> <span class="na">href=</span><span class="s">"#"</span><span class="nt">&gt;</span>Separated link<span class="nt">&lt;/a&gt;&lt;/li&gt;</span><br/>
  <span class="nt">&lt;/ul&gt;</span><br/>
<span class="nt">&lt;/div&gt;</span>

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

