---
title: Reflex Reference

language_tabs:


toc_footers:
  - IRC #reflex-frp *irc.freenote.net*
  - <a href="http://www.reddit.com/r/reflexfrp">Related Links</a>
  - <a href='https://github.com/ryantrinkle/try-reflex'>Download latest Reflex release</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the try-reflex docs! 

You can use this guide to get information on getting started with various Reflex-FRP applications.

You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

*It is currently still a work in progress and not ready for dissemination.*

# General Overview

What is it?

- Reflex is the FRP implementation itself.
- Try-Reflex is the installer that makes it easy to get all set up with Reflex.
- Reflex-Dom is the application of Reflex to that of web page building.

Where to get more help?

- IRC channel #reflex-frp (*irc.freenote.net*)
- <a href="http://www.reddit.com/r/reflexfrp">Related Links</a>


## Reflex

Reflex is the FRP implementation itself.

## Try-Reflex

This is the installer that makes it easy to get all set up with Reflex. To get a copy of this, <a href='https://github.com/ryantrinkle/try-reflex'>Clone this repo and run the ./try-reflex script</a>.

> To start, import Reflex:

```haskell
import           Reflex.Dom
```

> Within try-reflex, you can just run the script: `./try-reflex`
> 
> Make sure you've already installed GHCJS.

Reflex's companion library, Reflex-DOM, contains a number of functions used to build and interact with the Document Object Model. Let's start by getting a basic app up and running.


`import Reflex.Dom`

`main = mainWidget $ el "div" $ text "Welcome to Reflex"`

Saving this file as `source.hs` and compiling it produces a `source.jsexe` folder (the name of the jsexe folder is based on the name of the hs file). Inside the `source.jsexe` folder you'll find `index.html`. Opening that in your browser will reveal a webpage with a single div containing the text "Welcome to Reflex".

<aside class="notice">
Highlighted extra note `meowmeowmeow`.
</aside>

Most Reflex apps will start the same way: a call to `mainWidget` with a starting `Widget`. A `Widget` is some DOM wrapped up for easy use with Reflex. In our example, we are building the argument to `mainWidget`, (in other words, our starting `Widget`) on the same line.

`el` has the type signature:

```haskell
el :: MonadWidget t m => String -> m a -> m a
```

The first argument to `el` is a `String`, which will become the tag of the html element produced. The second argument is a `Widget`, which will become the child of the element being produced. 

> #### Sidebar: Interpreting the MonadWidget type
> FRP-enabled datatypes in Reflex take an argument `t`, which identifies the FRP subsystem being used.  This ensures that wires don't get crossed if a single program uses Reflex in multiple different contexts.  You can think of `t` as identifying a particular "timeline" of the FRP system.
> Because most simple programs will only deal with a single timeline, we won't revisit the `t` parameters in this tutorial.  As long as you make sure your `Event`, `Behavior`, and `Dynamic` values all get their `t` argument, it'll work itself out.

## Reflex-Dom

This is the application of Reflex to that of web page building.

# Reflex-Dom

## Creating an element tag

&lt;body&gt;

&lt;div&gt;

&lt;a&gt;

## Buttons

### Button Tags

Use the button classes on an &lt;a>, &lt;button>, or &lt;input> element.

```haskell
main = mainWidget $ el "div" $ do
  let labelAttrs = "class" =: "btn btn-default"
  (labelTitle, _) <- elAttr' "button" labelAttrs $ do
    elAttr' "em" $ text "more"
    elAttr "i" ("class" =: "caret") end
```
<button class="btn btn-default">
  <em>more</em>
  <span class="caret"></span>
</button>

&lt;button class="btn btn-default"><br/>
  &lt;em>more&lt;/em><br/>
  &lt;i class="caret">&lt;/i><br/>
&lt;/button>



More Examples:

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


## Unordered List

<div style="padding-left:28px">
  <p>Reflex is:</p>
  <ul>
    <li>Efficient</li>
    <li>Higher-order</li>
    <li>Glitch-free</li>
  </ul>
</div>

```haskell
main = mainWidget $ el "div" $ do
  el "p" $ text "Reflex is:"
  el "ul" $ do
    el "li" $ text "Efficient"
    el "li" $ text "Higher-order"
    el "li" $ text "Glitch-free"
```
&lt;div><br />
&nbsp;&nbsp;&lt;p>Reflex is:&lt;/p><br />
&nbsp;&nbsp;&lt;ul><br />
&nbsp;&nbsp;&nbsp;&nbsp;&lt;li>Efficient&lt;/li><br />
&nbsp;&nbsp;&nbsp;&nbsp;&lt;li>Higher-order&lt;/li><br />
&nbsp;&nbsp;&nbsp;&nbsp;&lt;li>Glitch-free&lt;/li><br />
&nbsp;&nbsp;&lt;/ul><br />
&lt;/div><br />

## Dropdowns

<div class="dropdown"  style="padding-left:28px">
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

```haskell

```
<br/>

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

## Navs

## Navbar

## Pagination

## Forms

&lt;form&gt;
&lt;/form&gt;

### Input Groups

&lt;input&gt;

## Alerts

## Panels

## Tabs 

## Media Embeds

## Image Carousel

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

