# object-fit

**`object-fit`** [CSS](https://developer.mozilla.org/zh-CN/docs/Web/CSS) 属性指定[可替换元素](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Replaced_element)（例如：[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img) 或 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/video)）的内容应该如何适应到其使用高度和宽度确定的框。

您可以通过使用 [`object-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/object-position) 属性来切换被替换元素的内容对象在元素框内的对齐方式。

## [尝试一下](https://developer.mozilla.org/zh-CN/docs/Web/CSS/object-fit#尝试一下)

<iframe class="interactive is-default-height" height="200" src="https://interactive-examples.mdn.mozilla.net/pages/css/object-fit.html" title="MDN Web Docs Interactive Example" loading="lazy" data-readystate="complete" style="box-sizing: border-box; border: none; max-width: 100%; width: 755px; background-color: var(--background-secondary); border-radius: var(--elem-radius); color: var(--text-primary); height: 375px; margin: 1rem 0px; padding: 0px;"></iframe>

## [语法](https://developer.mozilla.org/zh-CN/docs/Web/CSS/object-fit#语法)

```css
object-fit: contain;
object-fit: cover;
object-fit: fill;
object-fit: none;
object-fit: scale-down;
/* Global values */
object-fit: inherit;
object-fit: initial;
object-fit: revert;
object-fit: revert-layer;
object-fit: unset;
```

object-fit 属性由下列的值中的单独一个关键字来指定。

### [取值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/object-fit#取值)

- `contain`

    被替换的内容将被缩放，以在填充元素的内容框时保持其宽高比。整个对象在填充盒子的同时保留其长宽比，因此如果宽高比与框的宽高比不匹配，该对象将被添加“[黑边](https://zh.wikipedia.org/wiki/黑邊)”。

- `cover`

    被替换的内容在保持其宽高比的同时填充元素的整个内容框。如果对象的宽高比与内容框不相匹配，该对象将被剪裁以适应内容框。

- `fill`

    被替换的内容正好填充元素的内容框。整个对象将完全填充此框。如果对象的宽高比与内容框不相匹配，那么该对象将被拉伸以适应内容框。

- `none`

    被替换的内容将保持其原有的尺寸。

- `scale-down`

    内容的尺寸与 `none` 或 `contain` 中的一个相同，取决于它们两个之间谁得到的对象尺寸会更小一些。

## [形式定义](https://developer.mozilla.org/zh-CN/docs/Web/CSS/object-fit#形式定义)

| [初始值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/initial_value) | `fill`            |
| :----------------------------------------------------------- | ----------------- |
| 适用元素                                                     | replaced elements |
| [是否是继承属性](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Inheritance) | 否                |
| [计算值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/computed_value) | as specified      |
| Animation type                                               | discrete          |

## [形式语法](https://developer.mozilla.org/zh-CN/docs/Web/CSS/object-fit#形式语法)

```css
object-fit = 
  fill        |
  contain     |
  cover       |
  none        |
  scale-down  
```

## [示例](https://developer.mozilla.org/zh-CN/docs/Web/CSS/object-fit#示例)

### [为图像设置 object-fit](https://developer.mozilla.org/zh-CN/docs/Web/CSS/object-fit#为图像设置_object-fit)

#### HTML

```html
<section>
  <h2>object-fit: fill</h2>
  <img class="fill" src="mdn_logo_only_color.png" alt="MDN Logo">

  <img class="fill narrow" src="mdn_logo_only_color.png" alt="MDN Logo">

  <h2>object-fit: contain</h2>
  <img class="contain" src="mdn_logo_only_color.png" alt="MDN Logo">

  <img class="contain narrow" src="mdn_logo_only_color.png" alt="MDN Logo">

  <h2>object-fit: cover</h2>
  <img class="cover" src="mdn_logo_only_color.png" alt="MDN Logo">

  <img class="cover narrow" src="mdn_logo_only_color.png" alt="MDN Logo">

  <h2>object-fit: none</h2>
  <img class="none" src="mdn_logo_only_color.png" alt="MDN Logo">

  <img class="none narrow" src="mdn_logo_only_color.png" alt="MDN Logo">

  <h2>object-fit: scale-down</h2>
  <img class="scale-down" src="mdn_logo_only_color.png" alt="MDN Logo">

  <img class="scale-down narrow" src="mdn_logo_only_color.png" alt="MDN Logo">
</section>
```

#### CSS

```css
h2 {
  font-family: Courier New, monospace;
  font-size: 1em;
  margin: 1em 0 0.3em;
}

img {
  width: 150px;
  height: 100px;
  border: 1px solid #000;
  margin: 10px 0;
}

.narrow {
  width: 100px;
  height: 150px;
}

.fill {
  object-fit: fill;
}

.contain {
  object-fit: contain;
}

.cover {
  object-fit: cover;
}

.none {
  object-fit: none;
}

.scale-down {
  object-fit: scale-down;
}
```