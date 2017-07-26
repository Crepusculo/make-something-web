# intro
@import "step/style.css"
+ slice a card into pieces and keep the container
+ group a few pieces into one card
<br>
+ create part-response element

# step 1
@import "step/1.html"

Create `<div>` using flexbox.

# step 2
@import "step/2.html"

1. create `div .card` after your `<a>` tags.
    + the html now look like this:
```html
<div class="container">
    <a></a>
    <a></a>
    <a></a>
    <a></a>
    <div class="card">card</div>
</div>
```

2. using `~` to link `a:hover&focus` with `card` in css.
> The general sibling combinator is made of the "tilde" (U+007E, ~) character that separates two sequences of simple selectors. The elements represented by the two sequences share the same parent in the document tree and the element represented by the first sequence precedes (not necessarily immediately) the element represented by the second one.
```css
.container a:hover ~ .card, .container a:focus ~ .card{
    opacity: 1;
}
```
# step 3:
set `transform` for each `a:hover~.card` & `a:focus~.card`.
    it seems a bit of a mess if you using pure css selector
@import "step/3.html"
```css
.container a:nth-child(1):hover ~.transform{
    transform-origin: right bottom;
    transform: rotateX(10deg) rotateY(-10deg) translateZ(0);
}
.container a:nth-child(2):hover ~.transform{
    transform-origin: left bottom;
    transform: rotateX(10deg) rotateY(10deg) translateZ(0);
}
.container a:nth-child(3):hover ~.transform{
    transform-origin: left top;
    transform: rotateX(-10deg) rotateY(10deg) translateZ(0);
}
.container a:nth-child(4):hover ~.transform{
    transform-origin: right top;
    transform: rotateX(-10deg) rotateY(-10deg) translateZ(0);
}
```
notice that all hover/focus effects on `<a>`tags **not** on `<div class="card transform">`
> for showing and explaining how HTML & css organized, i use `transform` and `card` two class here. in fact, one is enough.

if you using *scss* or others css language, the selector will be clearer.
```scss
.container{
    a{
        &:hover,&:focus{
            ~ .transform{
                // set common effects here
                ....
            }
        }
        &:nth-child(1){
            ...
            &:hover,&:focus{
                ~ .transform{
                    // set spec effects here
                    ....
                }
            }
        }
    }
}
```
# step 4
remove `a` background and add transition,

@import "step/4.html"

# REF
https://codepen.io/gabriellewee/post/how-to-create-direction-aware-css-only-hover-effects
