##36.Intrinsic sizing
>主要知识点：fill, max-content, min-content, fit-content


##39.Fluid background, fixed content
>主要知识点：calc()

问题：背景自适应，中间内容固定。如常见的footer的处理。

![alt text](./res/39_footer.jpg "footer")

传统做法：使用两个标签。外标签使用背景图，并自适应。内标签给定一个宽度，内容写在内标签里，如下所示：

```js
<footer>
    <div class="wrapper">
        <!-- Footer content here -->
    </div>
</footer>

footer {
    background: #333;
} .wrapper {
    max-width: 900px;
    margin: 1em auto;
}

```
解决方案：只使用一个标签。padding: 1em;渐进增强。这样在不支持calc()的浏览器中，也有1em的padding。因为calc(50% - 450px)，450*2不管怎样都是900px，不需要再写max-width:900px。如果要缩小宽度或扩大宽度，只需要改一处地方即可。

```js
footer {
    padding: 1em;
    padding: 1em calc(50% - 450px);
    background: #333;
}
```

[demo](./39.FluidBackgroundFixedContent.html)
