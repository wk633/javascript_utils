## CSS



- box model
- js get element height/width
- BFC
- 3 columns layout
- differences between inline, block and inline-block?



### box model

- width/height only content
- width/height contains padding and border

```css
box-sizing: content-box/border-box; 
```



### js get element height/width

```javascript
window.getComputedStyle(dom).width/height
```

- clientWidth(visible width)
- offsetWidth(visible width with scroll bar width)
- scrollWidth(visible width and invisible width)



###BFC

block formatting context

ways to create BFC

- floats (elements where [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) is not `none`)
- absolutely positioned elements (elements where [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position) is `absolute` or `fixed`)
- [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) has a value other than `visible`(`overflow: auto`)



### 3 columns layout

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        html * {
            padding: 0px;
            margin: 0px;
        }
        article>div{
            min-height: 300px;
        }
    </style>
</head>
<body>
    <style>
        .left-right-center{
            display: flex;
        }
        .flex .left{
            width: 300px;
            background: red;
        }
        .flex .right{
            width: 300px;
            background: blue;
        }
        .flex .center{
            background: yellow;
            flex: 1;
        }
    </style>
    <section class="flex">
        <article class="left-right-center">
            <div class="left"></div>
            <div class="center">
                <h2>flex</h2>
                <h3>flex solution</h3>
            </div>
            <div class="right"></div>
        </article>
    </section>
</body>
</html>

```



### differences between inline, block and inline-block?

`inline`

elements do not break the flow. 

- margin/ padding will push other elements horizontally not vertically. 
- ignores height and width.

`block`

breaks the flow and dont sits inline.

 they are usually container like div, section, ul and also text p, h1, etc.

`inline-block`

 will be similar to inline and will go with the flow of the page. 

has height and width.