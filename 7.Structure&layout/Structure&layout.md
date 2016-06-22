##36.Intrinsic sizing
>主要知识点：fill, max-content, min-content, fit-content

##38.Styling by sibling count
>主要知识点：:first-child:nth-last-child
>:nth-last-child，类似于:nth-child，从后往前选择元素。
>语法：element:nth-last-child(an + b) {/*规则*/}
>tr:nth-last-child(-n+4)，匹配表格中的最后四行

问题：需要根据节点兄弟姐妹的个数，设置不同的样式。

[demo](http://violarong.github.io/cssSecretDemos/7.Structure&layout/38.StylingBySiblingCount.html)

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

[demo](http://violarong.github.io/cssSecretDemos/7.Structure&layout/39.FluidBackgroundFixedContent.html)

##40.Vertical centering
>主要知识点：calc()

问题：垂直居中
