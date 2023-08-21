# display

[CSS](https://developer.mozilla.org/zh-CN/docs/Web/CSS) **`display`** 属性设置元素是否被视为[块或者内联元素](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flow_Layout)以及用于子元素的布局，例如[流式布局](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flow_Layout)、[网格布局](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout)或[弹性布局](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout)。

形式上，**`display`** 属性设置元素的内部和外部的*显示类型*。外部类型设置元素参与[流式布局](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flow_Layout)；内部类型设置子元素的布局。一些 `display` 值在它们自己的单独规范中完整定义；例如，在 CSS 弹性盒模型的规范中，定义了声明 `display: flex` 时会发生的细节。

## [语法](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#语法)

CSS `display` 规定使用的关键字。

```css
/* precomposed values */
display: block;
display: inline;
display: inline-block;
display: flex;
display: inline-flex;
display: grid;
display: inline-grid;
display: flow-root;

/* box generation */
display: none;
display: contents;

/* two-value syntax */
display: block flow;
display: inline flow;
display: inline flow-root;
display: block flex;
display: inline flex;
display: block grid;
display: inline grid;
display: block flow-root;

/* other values */
display: table;
display: table-row; /* all table elements have an equivalent CSS display value */
display: list-item;

/* Global values */
display: inherit;
display: initial;
display: revert;
display: revert-layer;
display: unset;
```

## [分组的值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#分组的值)

关键值可以被分组为六个种类。

### [外部表现](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#外部表现)

- [``](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display-outside)

    这些关键字规定元素的外部显示类型，实际上就是其在流式布局中的角色：`block`该元素生成一个块级元素盒，在正常的流中，该元素之前和之后产生换行。`inline`该元素生成一个或多个内联元素盒，它们之前或者之后并不会产生换行。在正常的流中，如果有空间，下一个元素将会在同一行上。

**备注：** 浏览器支持双值语法，当仅发现外部值时，例如当指定 `display: block` 或 `display: inline`，其将内部值设置为 `flow`。这种行为是预期的；例如，如果你指定一个元素是块元素，你将期望该元素的子元素将同块和内联元素一样参与正常的流布局。

### [内部表现](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#内部表现)

- [`` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/display-inside)

    这些关键字规定了元素的内部显示类型，其定义了该内容布局时的格式上下文的类型（假设它是一个非替换元素）：`flow` 实验性该元素使用流式布局（块和内联布局）来排布它的内容。如果它的外部显示类型是 `inline` 或 `run-in`，并且它参与一个块或者内联格式上下文，那么它将生成一个内联盒子。否则它将生成一个块容器盒。根据其他属性的值（例如 [`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position)、[`float`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/float) 或 [`overflow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/overflow)）以及它自身是否参与到块或者内联格式化上下文，它要么为它的内容建立新的[块级格式化上下文](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Block_formatting_context)（BFC），要么将其内容集成到其父元素的格式化上下文中。`flow-root`该元素生成一个块级元素盒，其会建立一个新的[块级格式化上下文](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Block_formatting_context)，定义格式化上下文的根元素。`table`该元素的行为类似于 HTML 中的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/table) 元素。它定义了一个块级别的盒子。`flex`该元素的行为类似块级元素并且根据[弹性盒模型](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout)布局它的内容。`grid`该元素的行为类似块级元素并且根据[网格模型](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout)布局它的内容。`ruby` 实验性该元素的行为类似内联元素并且根据 ruby 格式化模型布局它的内容。它的行为像关联的 HTML 的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ruby) 元素。

**备注：** 浏览器支持双值语法，当仅发现外部值时，例如当指定 `display: flex` 或 `display: grid`，其将外部值设置为 `block`。这种行为是预期的；例如，如果你指定一个元素是 `display: grid`，你将期望在网格容器中创建的盒子是块级别的盒子。

### [列表元素](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#列表元素)

- [`` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/display-listitem)

    该元素为内容生成一个块级盒子和一个单独的列表元素内联盒子。

`list-item` 的单独值将导致元素的行为类似于一个列表元素。其可以与 [`list-style-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-type) 和 [`list-style-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-position) 一起使用。

`list-item` 也可以与任意的 [``](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display-outside) 关键字和 [`` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/display-inside) 中的 `flow` 或 `flow-root` 关键字组合。

**备注：** 浏览器支持双值语法，如果没有指定内部值，默认为 `flow`。如果没有指定外部值，主体盒子将具有 `block` 的外部显示类型。

### [内部](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#内部)

- [``](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display-internal)

    一些布局模型，例如 `table` 和 `ruby` 有一个复杂的内置结构，它们的子孙后代可以扮演几个不同的角色。本节定义的这些“内部”display 值，仅在特定的布局模式下有用。`table-row-group`该元素的行为类似于 HTML 的 元素。`table-header-group`该元素的行为类似于 HTML 的 元素。`table-footer-group`该元素的行为类似于 HTML 的 元素。`table-row`该元素的行为类似于 HTML 的 元素。`table-cell`该元素的行为类似于 HTML 的 `](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/td) 元素。`table-column-group`该元素的行为类似于 HTML 的 元素。`table-column`该元素的行为类似于 HTML 元素。`table-caption`该元素的行为类似于 HTML 的 `](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/caption) 元素。`ruby-base` 实验性该元素的行为类似于 HTML 的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/rb) 元素。`ruby-text` 实验性该元素的行为类似于 HTML 的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/rt) 元素。`ruby-base-container` 实验性该元素是作为匿名盒子生成的。`ruby-text-container` 实验性该元素的行为类似于 HTML 的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/rtc) 元素。

### [盒](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#盒)

- [``](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display-box)

    这些关键词定义一个元素到底是否产生 display 盒。`contents`这些元素自身不会产生特定的盒子。它们被伪盒子（pseudo-box）和子盒子取代。请注意，CSS Display Level 3 规范中定义了 `contents` 值如何影响“异常元素”——这些元素不是纯粹由 CSS 盒模型概念呈现的（例如替换元素）。更多的细节请参见[附录 B：display 的影响：异常元素的内容](https://drafts.csswg.org/css-display/#unbox)。*由于浏览器的一个错误，该元素目前不会被添加到无障碍树中——屏幕阅读器将不会看到里面的内容。更多细节，参见下面的[无障碍问题](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#无障碍问题)。*`none`使元素不再显示，其对布局不会有影响（文档渲染得好像这个元素并不存在）。所有的后代元素也不会再显示。为了使元素占据一个它通常占据的空间，但实际上没有渲染任何东西，应该使用 [`visibility`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/visibility) 属性。

### [预组合](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#预组合)

- [``](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display-legacy)

    CSS 2 为 `display` 属性使用单关键字的预组合的语法，对相同布局模式的块级和内联级变体需要单独的关键字。`inline-block`该元素生成块级元素盒，如果它是一个单独的内联盒，它将盒周围的内容一起流动（行为类似于替换元素）。它等同于 `inline flow-root`。`inline-table``inline-table` 值在 HTML 中没有直接的映射。它行为类似于 HTML 的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/table) 元素，但实际是一个内联盒，而不是一个块级盒子。table 盒内部是一个块级上下文。它等同于 `inline table`。`inline-flex`元素的行为类似于内联元素并且它的内容根据弹性盒模型布局。它等同于 `inline flex`。`inline-grid`元素的行为类似于内联元素并且它的内容根据网格盒模型布局。它等同于 `inline grid`。

### [你现在应该使用什么语法？](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#你现在应该使用什么语法？)

Level 3 规范中详细描述了 `display` 的双值属性——明确地启用外部和内部显示类型的规范——但浏览器尚未很好地支持这一点。

预组合 `<display-legacy>` 方法允许单关键字产生相同的结果，并且直到双关键值语法有着更好的支持之前，它应该被开发人员青睐。例如，你可以按以下方式使用双值语法指定一个内联的弹性容器：

```css
.container {
  display: inline flex;
}
```

目前可以使用单个值来指定。

```css
.container {
  display: inline-flex;
}
```

有关规范中的这些更改的更多信息，请参考这篇文章[适应 display 的新的双值语法 (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/display/multi-keyword_syntax_of_display).

### [全局值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#全局值)

```css
/* Global values */
display: inherit;
display: initial;
display: unset;
```

## [描述](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#描述)

`display` 为不同类型的值设置了单独的页面，其中包含这些值的多个示例——请参阅[语法](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#语法)部分。此外，请参阅以下资料，其中深度展示了 display 的各种值。

- [适应 display 的新双值语法 (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/display/multi-keyword_syntax_of_display)

### [CSS 流式布局（display: block、display: inline）](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#css_流式布局（display_block、display_inline）)

- [常规流中的块和内联布局](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flow_Layout/Block_and_Inline_Layout_in_Normal_Flow)
- [流布局和溢出](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flow_Layout/Flow_Layout_and_Overflow)
- [流布局和书写模式](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flow_Layout/Flow_Layout_and_Writing_Modes)
- [格式化上下文简介](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flow_Layout/Intro_to_formatting_contexts)
- [流式布局以及如何脱离流式布局](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flow_Layout/In_Flow_and_Out_of_Flow)

### [display: flex](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#display_flex)

- [弹性盒基础概念](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
- [对齐弹性容器中的弹性项目](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout/Aligning_Items_in_a_Flex_Container)
- [控制 Flex 子元素在主轴上的比例](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout/Controlling_Ratios_of_Flex_Items_Along_the_Main_Ax)
- [跨浏览器弹性盒的混合](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout/Backwards_Compatibility_of_Flexbox)
- [掌握弹性物件的包装](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout/Mastering_Wrapping_of_Flex_Items)
- [弹性元素排序](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout/Ordering_Flex_Items)
- [弹性盒子与其他布局方法的联系](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout/Relationship_of_Flexbox_to_Other_Layout_Methods)
- [弹性盒的向后兼容](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout/Backwards_Compatibility_of_Flexbox)
- [弹性盒的典型用例](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout/Typical_Use_Cases_of_Flexbox)

### [display: grid](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#display_grid)

- [网格布局的基本概念](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout)
- [网格布局和其他布局方法的联系](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/Relationship_of_Grid_Layout)
- [基于线的定位](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid)
- [网格模板区域](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/Grid_Template_Areas)
- [使用命名线布局](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines)
- [网格布局中的自动定位](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/Auto-placement_in_CSS_Grid_Layout)
- [网格布局中的盒模型对齐](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/Box_Alignment_in_CSS_Grid_Layout)
- [网格、逻辑值和书写模式](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/CSS_Grid_Logical_Values_and_Writing_Modes)
- [CSS 网格布局和无障碍](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/CSS_Grid_Layout_and_Accessibility)
- [CSS 网格布局和渐进增强](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/CSS_Grid_and_Progressive_Enhancement)
- [利用网格布局实现常用布局](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout/Realizing_common_layouts_using_CSS_Grid_Layout)

## [无障碍问题](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#无障碍问题)

### [display: none](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#display_none)

在一个元素中使用 `display` 的值为 `none` 将会从[无障碍树中](https://developer.mozilla.org/zh-CN/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis)移除它。这将导致该元素及其所有后代元素不再通过屏幕阅读器技术展示。

如果你想要从视觉上隐藏元素，一个更好的替代方案是使用[属性的组合](https://gomakethings.com/hidden-content-for-better-a11y/#hiding-the-link)将其直观地从屏幕删除，但是通过屏幕阅读器等辅助技术依然可以解析。

### [display: contents](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#display_contents)

当前在大多数浏览器的实现是将任意 `display` 值为 `contents` 的元素从[无障碍树中](https://developer.mozilla.org/zh-CN/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis)移除（但是保留后代元素）。这将导致该元素自身不再通过屏幕阅读器技术展示。根据 [CSS 规范](https://drafts.csswg.org/css-display/#valdef-display-contents)，这是错误的行为。

- [更多带有 display: contents 的无障碍标记 | Hidde de Vries](https://hidde.blog/more-accessible-markup-with-display-contents/)
- [Display: Contents Is Not a CSS Reset | Adrian Roselli](https://adrianroselli.com/2018/05/display-contents-is-not-a-css-reset.html)

### [表格](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#表格)

将 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/table) 元素的 `display` 值改为 `block`、`grid` 或 `flex`，这将改变它在[无障碍树](https://developer.mozilla.org/zh-CN/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis)中的显示。这将导致表格不再通过屏幕阅读（screen reading）技术展示。

- [关于 CSS display 属性对表格语义的影响的简短说明——The Paciello Group](https://www.tpgi.com/short-note-on-what-css-display-properties-do-to-table-semantics/)
- [隐藏内容以获得更好的无障碍 | Go Make Things](https://gomakethings.com/hidden-content-for-better-a11y/)
- [MDN Understanding WCAG，标准 1.3 解释 (en-US)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable)
- [Understanding Success Criterion 1.3.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

## [形式定义](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#形式定义)

| [初始值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/initial_value) | `inline`                                                     |
| :----------------------------------------------------------- | ------------------------------------------------------------ |
| 适用元素                                                     | all elements                                                 |
| [是否是继承属性](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Inheritance) | 否                                                           |
| [计算值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/computed_value) | as the specified value, except for positioned and floating elements and the root element. In both cases the computed value may be a keyword other than the one specified. |
| Animation type                                               | Not animatable                                               |

## [形式语法](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#形式语法)

```txt
display = 
  [ <display-outside> || <display-inside> ]         |
  <display-listitem>                                |
  <display-internal>                                |
  <display-box>                                     |
  <display-legacy>                                  |
  <display-outside> || [ <display-inside> | math ]  

<display-outside> = 
  block   |
  inline  |
  run-in  

<display-inside> = 
  flow       |
  flow-root  |
  table      |
  flex       |
  grid       |
  ruby       

<display-listitem> = 
  <display-outside>?     &&
  [ flow | flow-root ]?  &&
  list-item              

<display-internal> = 
  table-row-group      |
  table-header-group   |
  table-footer-group   |
  table-row            |
  table-cell           |
  table-column-group   |
  table-column         |
  table-caption        |
  ruby-base            |
  ruby-text            |
  ruby-base-container  |
  ruby-text-container  

<display-box> = 
  contents  |
  none      

<display-legacy> = 
  inline-block  |
  inline-table  |
  inline-flex   |
  inline-grid   
```

## [示例](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#示例)

### [比较 display 的值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display#比较_display_的值)

在这个示例中，我们有两个块级的容器元素，每个元素有三个内联子元素。在下面，我们有一个选择菜单，允许你将不同的 `display` 值应用于容器，允许你去比较和对比不同的值如何影响元素及其他们子元素的布局。

我们在容器上以及它们的子元素中使用了 [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding) 和 [`background-color`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-color)，以便更容易看到 display 值的影响。

**备注：** 我们没有包含任何现代化的双值语法，因为对此的支持仍然相当有限。

#### HTML

```html
<article class="container">
  <span>First</span>
  <span>Second</span>
  <span>Third</span>
</article>

<article class="container">
  <span>First</span>
  <span>Second</span>
  <span>Third</span>
</article>

<div>
  <label for="display">Choose a display value:</label>
  <select id="display">
    <option selected>block</option>
    <option>inline</option>
    <option>inline-block</option>
    <option>none</option>
    <option>flex</option>
    <option>inline-flex</option>
    <option>grid</option>
    <option>inline-grid</option>
    <option>table</option>
    <option>list-item</option>
  </select>
</div>
```

#### CSS

```css
html {
  font-family: helvetica, arial, sans-serif;
  letter-spacing: 1px;
  padding-top: 10px;
}

article {
  background-color: red;
}

article span {
  background-color: black;
  color: white;
  margin: 1px;
}

article,
span {
  padding: 10px;
  border-radius: 7px;
}

article,
div {
  margin: 20px;
}
```

#### JavaScript

```js
const articles = document.querySelectorAll('.container');
const select = document.querySelector('select');

function updateDisplay() {
  articles.forEach((article) => {
    article.style.display = select.value;
  });
}

select.addEventListener('change', updateDisplay);

updateDisplay();
```

#### 结果

<iframe class="sample-code-frame" title="比较 display 的值 sample" id="frame_比较_display_的值" width="100%" height="440" src="https://live-samples.mdn.mozilla.net/zh-CN/docs/Web/CSS/display/_sample_.%E6%AF%94%E8%BE%83_display_%E7%9A%84%E5%80%BC.html" loading="lazy" style="box-sizing: content-box; border: 1px solid var(--border-primary); max-width: 100%; width: calc((100% - 2rem) - 2px); background: rgb(255, 255, 255); border-radius: var(--elem-radius); padding: 1rem;"></iframe>

**备注：** 你可以在页面上找到上面链接的每个单独 display 数据类型的更多示例。