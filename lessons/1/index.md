# Understanding HTML & CSS Basics
A simple guide that will cover the basics of HTML & CSS and how the work together to display a website.

## What We'll Cover
- [basic html layout](#0-basic-html-layout)
- [writing performant css](#1-writing-performant-css)
- [linking-your-css](#2-linking-your-css)

## 0. Basic HTML Layout
For a fantastic break down of syntax check out mozilla's [anatomy-of-an-html-document](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started). The typical HTML Document consits of the following basic format:

`<!DOCTYPE html>`: In modern website design this is all you need at the top of your page.

`<html>`: Called the `root` element `<html>` wraps all the content on the page.

`<head>`: A container for metadata, links to css, descriptions and pretty much anything that **isn't content**'

`<meta charset="utf-8">`: Specifies your character set. Omitting this may cause issues. There's no reason not to do this.

`<title>`: The information that is displayed in browser tabs, bookmarks, and SEO results.

`<body>`: The element that will contain all your content.

### Putting it all together
Create a document with the name `index.html`

```html
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="utf-8">
            <title>My first web site</title>
        </head>
        <body>
            <h1>Welcome to my website!</h1>
            <p>Here is some basic content.</p>
        </body>
    </html>
```

What about all those other cool tags like `<header>`, `<main>`, `<section>`, and `<footer>`? Don't worry we going to cover them later.

## 1. Writing performant CSS
When making a very basic website you won't need to worry about [computed style calculation](https://developers.google.com/web/fundamentals/performance/rendering/reduce-the-scope-and-complexity-of-style-calculations) but in the future, if you are altering elements on your page through animations or javascript you will cause the browser to recalculate element styles. 

> Roughly 50% of the time used to calculate the computed style for an element is used to match selectors, and the other half is used for constructing the RenderStyle from the matched rules.

What does this even mean? Consider how CSS works under the hood by looking at this html:

```html
    <div>
        <div class="box">
            <div class="title"></div>
        </div>
        <div class="box">
            <div class="title"></div>
        </div>
    </div>
```

What we want to do is target the `.title` of the last `.box` element. You might think of something like this:

```css
.box:last-child .title{
    /* styles */
}
```
Your browser will read this from **right to left** asking: 
Is this an element of `.title` belonging to the last element with a class of `.box`? This is a simple example, but regardless the browser will take additional time to figure this out. 

To get pin-point accuracy, we can add a class to the final box:

```html
    <div>
        <div class="box">
            <div class="title"></div>
        </div>
        <div class="box">
            <div class="last-box-title"></div>
        </div>
    </div>
```

And target it directly:

```css
.last-box-title{
    /* styles */
}
```
For more information and tips on how to write better queries checkout [Block, Element, Modifier](https://css-tricks.com/bem-101/)

## 2. Linking your CSS
Now that you understand HTML layout, and how CSS works, it's time to put it all together! Let's start by adding a `<link>` element to our `<head>`'
```html
<link rel="stylesheet" href="css.css"/>
```

### 3. Parallax Design
Parallax in website designs involves moving the background at a different speed than the foregraound. Let start by creating our HTML document.

```html
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="utf-8">
            <title>Parallax Effect</title>
            <link rel="stylesheet" href="css.css"/>
        </head>
        <body>
            <main class="parallax">
                <section class="parallax-1">
                    <h1>Parallax 1</h1>
                </section>
                <section class="parallax-content-1">
                    <h2>Page content</h2>
                    <p>This will be regular content.</p>
                </section>
                <section class="parallax-2">
                    <h2>Parallax 2</h2>
                </section>
            </main>
        </body>
    </html>
```



