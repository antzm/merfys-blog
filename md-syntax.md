# Markdown Syntax Overview

This text is an overview of the markdown syntax used in the GitHub .md files

Firstly, the markdown syntax is shown in the highlighted window and then, just below, the output format appears

## Headings:

```
# this is a size 1 heading
## this is a size 2 heading
### this is a size 3 heading
#### this is a size 4 heading
##### this is a size 5 heading
###### this is a size 6 heading
```

# this is a size 1 heading
## this is a size 2 heading
### this is a size 3 heading
#### this is a size 4 heading
##### this is a size 5 heading
###### this is a size 6 heading

## Bold and Italics:
```
**this thext is bold**

_this text is italized_

**combination of _italized_ and bold**

_combination of **bold** and italized_

```
**this thext is bold**

_this text is italized_

**combination of _italized_ and bold**

_combination of **bold** and italized_

## Ordered Lists:
```
1. first item
2. second item
3. third item
```
1. first item
2. second item
3. third item
```
1. first item
2. second item
   1. second item a
   2. second item b
   3. second item c
3. third item
   1. third item a
   2. third item b
   3. third item c
```
1. first item
2. second item
   1. second item a
   2. second item b
   3. second item c
3. third item
   1. third item a
   2. third item b
   3. third item c

## Unordered Lists:

```
* first item
* second item
* third item
```
* first item
* second item
* third item
```
* first item
* second item
   * second item a
   * second item b
   * second item c
* third item
   * third item a
   * third item b
   * third item c
```
* first item
* second item
   * second item a
   * second item b
   * second item c
* third item
   * third item a
   * third item b
   * third item c

## Task Lists:

```
* [ ] unchecked item 1
* [x] checked item 2
* [x] checked item 3
```

* [ ] unchecked item 1
* [x] checked item 2
* [x] checked item 3

```
* [ ] unchecked item 1
    * [ ] subitem 1a
    * [ ] subitem 1b
* [x] checked item 2
* [x] checked item 3
    * [x] subitem 3a
```

* [ ] unchecked item 1
    * [ ] subitem 1a
    * [ ] subitem 1b
* [x] checked item 2
* [x] checked item 3
    * [x] subitem 3a

## Tables:
```
header one | header two | header three
-----------|------------| ------------
first item in #1 | first item in #2 | first item in # 3
second item in # 1 | second item in # 2 | second item in # 3
third item in # 1 | third item in # 2 | third itemm in # 3
```
header one | header two | header three
-----------|------------| ------------
first item in #1 | first item in #2 | first item in # 3
second item in # 1 | second item in # 2 | second item in # 3
third item in # 1 | third item in # 2 | third itemm in # 3

```
items align left | items align center | items align right
:---   |   :---:   |   ---:
item 1a | item 2a | item 3a
item 1b | item 2b | item 3b
item 1c | item 2c | item 3c
```
items align left | items align center | items align right
:---   |   :---:   |   ---:
item 1a | item 2a | item 3a
item 1b | item 2b | item 3b
item 1c | item 2c | item 3c

## Code:

`` this is an `inline code` example ``

this is an `inline code` example

````
```
This is a longer

code example
```
````

```
This is a longer

code example
```

## Code highlighting:

### JavaScript:
````
```javascript
for (i=0; i<10; i++) {
  console.log(i);
}
```
````

```javascript
for (i=0; i<10; i++) {
  console.log(i);
}
```

### HTML:
````
```html
<section class="intro">
   <h1 class="intro-heading">intro heading</h1>
   <p class="intro-text">intro text</p>
</section>
```
````

```html
<section class="intro">
   <h1 class="intro-heading">intro heading</h1>
   <p class="intro-text">intro text</p>
</section>
```

### CSS:
````
```css
.intro {
   margin: 0;
   padding: 0;
   color: #1f3d7a;
   font: Verdana, Arial, sans-serif;
}
```
````

```css
.intro {
   margin: 0;
   padding: 0;
   color: #1f3d7a;
   font: Verdana, Arial, sans-serif;
}
```

## Links:

```
https://www.google.com
```
https://www.google.com

```
[GitHub](http://github.com)
```
[GitHub](http://github.com)

## Quote:

```
>“We change the world not by what we say or do, but as a consequence of what we have become.”
— David R. Hawkins
```
>“We change the world not by what we say or do, but as a consequence of what we have become.”
— David R. Hawkins

## Images:

```
![a black cat sitting next to a white computer mouse](DSC_1609.jpg)
```

![a black cat sitting next to a white computer mouse](DSC_1609.jpg)
