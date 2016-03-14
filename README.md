# Today I Learned

## 14/03/2016 - CSS3 ch unit of measurement

This can be invaluable if you are trying to express the width of an element as a multiple of the character width.
The best part is that `ch` understands the changes in character width arising due to different font styles, sizes etc.

Example:

```css
.panel {
    font-style: Consolas, monospace;
    font-size: 12px;
}

.drawer {
    width: 10ch;
}
```

```html
<div class="panel">
    <p>1234567890</p>
    <div class="drawer"></div>
</div>
```

The above will render both the `p` and the `div.drawer` elements at equal widths (provided the margins and paddings are set accordingly, of course).

What's more, the browser support for this is remarkably good too.
