# OOCSS

====================================================================================

## What is it?
* Object Oriented CSS
* a method of creating reusable CSS

## How do you write CSS when your program spans thousands of pages??
* by applying OOCSS of course!
* __3 major goals__:
    - fast/efficient
    - scalable
    - maintainable
* fast/efficient b/c pretty much zero repetition if executed correctly
* scalable & maintainable b/c classes can be reused and mixed in with any objects, _without_ worrying about context!

## So... What is an "object" in CSS?
* visualize the website in your mind... see the repeating patterns? (button designs, header designs... etc) those are the objects
    - objects can be abstracted independently (into HTML, CSS, and even JS)
    - objects can be used over and over again throughout the website

## Two Main Principles
1. separate structure from skin
2. separate container from content

## Separate Structure from Skin
* think of all (repeating) visual features of the page as "skins"
    - e.g. colors, borders, background patterns...
* think of all other "invisible" things as "structures"
    - e.g. positioning, padding, margins...
* so... separate the structure from the skin!
    - enables a lot of variety in terms of aesthetics, without a ton of code
* give classes to the elements of the skin and structure, to that you can refer to multiple elements of the page in a single CSS call
    - __do not__ mix "structure"/positioning properties with "skin"/styling properties on the same class
        + prevents code duplication

### Some examples using code

* before applying OOCSS...
```
    #button {
        width: 250px;
        height: 70 px;
        padding: 5 px;
        border: 3px solid #ccc;
        background-color: #40FF34;
    }

    #box {
        width: 340px;
        overflow: hidden;
        padding: 2 px;
        border: 3px solid #ccc;
        background-color: #40FF34;
    }

    #widget {
        width: 700px;
        min-height: 300px;
        overflow: auto;
        border: 3px solid #ccc;
        background-color: #40FF34;
    }
```

* notice that these use IDs, which are supposed to be unique/aren't supposed to be repeated
    - extract out the common styling properties and apply OOCSS!

* after applying OOCSS!!
```
.button {
    width: 250px;
    height: 70px;
}

.box {
    width: 340px;
    overflow: hidden;
}

.widget {
    width: 700px;
    min-height: 300px;
    overflow: auto;
}

.skin {
    border: 3px solic #ccc;
    background-color: #40FF34;
}
```
* __note__ that instead of using IDs, we are now using classes, which can be reused; this code can later be easily fixed/modified to fit expanding code base

## Separate Container from Content
* do __NOT__ using styling that depends on the location of the tag
    - in other words, DON'T style all `<h2>` tags that are a child of the `<div class="treat-container">`

### Some examples... 

__THIS IS BAD. DO NOT DO THIS. REPEAT... DON'T DO THIS.__

* an example of what _not_ to do... 
``` 
#sidebar h2 {
    font-style: sans-serif;
    font-size: 18px;
    color: #ff33ff;
    font-weight: bold;
}
```
* in this case, what happens when we want to apply the same styling (except font size) to the `<h2>` inside the `<footer>`? 
``` 
#sidebar h2, #footer h2 {
    font-style: sans-serif;
    font-size: 18px;
    color: #ff33ff;
    font-weight: bold;
}

#footer h2 {
    font-size: 11px;
}
```

__DUN DUN DUN__ _or worse_ ...

``` 
#sidebar h2, #footer h2 {
    font-style: sans-serif;
    font-size: 18px;
    color: #ff33ff;
    font-weight: bold;
}

#footer h2 {
    font-style: sans-serif;
    font-size: 11px;
    color: #ff33ff;
    font-weight: bold;
}
```





