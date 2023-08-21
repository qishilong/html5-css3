# 文本 Text

|                             属性                             |  版本  | 继承性 |                             描述                             |
| :----------------------------------------------------------: | :----: | :----: | :----------------------------------------------------------: |
| [text-transform](http://css.doyoe.com/properties/text/text-transform.htm) | CSS1/3 |   有   |                 定义元素的文本如何转换大小写                 |
| [white-space](http://css.doyoe.com/properties/text/white-space.htm) |  CSS1  |   有   | 指定元素是否保留文本间的空格、换行；指定文本超过边界时是否换行。 |
| [tab-size](http://css.doyoe.com/properties/text/tab-size.htm) |  CSS3  |   有   |                  定义元素内容中制表符的长度                  |
| [word-break](http://css.doyoe.com/properties/text/word-break.htm) |  CSS3  |   有   |           定义元素内容文本的字间与字符间的换行行为           |
| [word-wrap/overflow-wrap](http://css.doyoe.com/properties/text/overflow-wrap.htm) |  CSS3  |   有   |              定义元素内容文本遇到边界时如何换行              |
| [text-align](http://css.doyoe.com/properties/text/text-align.htm) | CSS1/3 |   有   |                  定义元素内容的水平对齐方式                  |
| [text-align-last](http://css.doyoe.com/properties/text/text-align-last.htm) |  CSS3  |   有   | 定义块内文本内容的最后一行（包括块内仅有一行文本的情况，这时既是第一行也是最后一行）或者被强制打断的行的对齐方式 |
| [text-justify](http://css.doyoe.com/properties/text/text-justify.htm) |  CSS3  |   有   |             定义使用什么方式实现文本内容两端对齐             |
| [word-spacing](http://css.doyoe.com/properties/text/word-spacing.htm) | CSS1/3 |   有   |                    指定单词之间的额外间隙                    |
| [letter-spacing](http://css.doyoe.com/properties/text/letter-spacing.htm) | CSS1/3 |   有   |                    指定字符之间的额外间隙                    |
| [text-indent](http://css.doyoe.com/properties/text/text-indent.htm) | CSS1/3 |   有   |                    定义块内文本内容的缩进                    |
| [vertical-align](http://css.doyoe.com/properties/text/vertical-align.htm) | CSS1/2 |   无   |              定义行内元素在行框内的垂直对齐方式              |
| [line-height](http://css.doyoe.com/properties/text/line-height.htm) |  CSS1  |   有   |                   定义元素中行框的最小高度                   |
| [text-size-adjust](http://css.doyoe.com/properties/text/text-size-adjust.htm) |  CSS3  |   有   |            定义移动端页面中元素文本的大小如何调整            |

# white-space

**white-space**：normal | pre | nowrap | pre-wrap | pre-line

**默认值**：normal

**适用于**：所有元素

**继承性**：有

**动画性**：否

**计算值**：指定值

**媒　体**：视觉

## 取值：

- normal：

    默认处理方式。会将序列的空格合并为一个，内部是否换行由换行规则决定。

- pre：

    原封不动的保留你输入时的状态，空格、换行都会保留，并且当文字超出边界时不换行。等同 pre 元素效果

- nowrap：

    与`normal`值一致，不同的是会强制所有文本在同一行内显示。

- pre-wrap：

    与`pre`值一致，不同的是文字超出边界时将自动换行。

- pre-line：

    与`normal`值一致，但是会保留文本输入时的换行。

## 说明：

**指定元素是否保留文本间的空格、换行；指定文本超过边界时是否换行。**

- 对应的脚本特性为：**whiteSpace**

# word-break

## 语法：

**word-break**：normal | keep-all | break-all | break-word

**默认值**：normal

**适用于**：所有元素

**继承性**：有

**动画性**：否

**计算值**：指定值

**相关属性**：[word-wrap/overflow-wrap](http://css.doyoe.com/properties/text/word-wrap.htm)

**媒　体**：视觉

## 取值：

- normal：

    默认的换行规则。依据各自语言的规则，允许在字间发生换行。

- keep-all：

    对于 CJK（中文，韩文，日文）文本不允许在字符内发生换行。Non-CJK 文本表现同`normal`

- break-all：

    对于 Non-CJK 文本允许在任意字符内发生换行。该值适合包含一些非亚洲文本的亚洲文本，比如使连续的英文字符断行。

- break-word：

    与`break-all`相同，不同的地方在于它要求一个没有断行破发点的词必须保持为一个整体单位。这与[word-wrap](http://css.doyoe.com/properties/text/word-wrap.htm)的`break-word`值效果相同

## 说明：

**定义元素内容文本的字间与字符间的换行行为。**

- 作为IE的私有属性之一，IE5.5率先实现了`word-break`，后期被w3c采纳成标准属性；

- 对于解决防止页面中出现连续无意义的长字符打破布局，应该使用`break-all | break-word`属性值；

- 同为强制打断单词的`break-all`与`break-word`的两个值，需要了解她们间的主要区别（下述2个示例需要在webkit/blink浏览器下查看）：

    **break-all：**

    做一个示例让大家更好的区分wordbreakbreakword与wordbreakbreakall的实际应用效果

    > `.test1 { word-break: break-all; }`

    break-all会在文本内容遇见边界时，强制将文本打断换行，而不考虑单词是否是完整的一个单位

    **break-word：**

    做一个示例让大家更好的区分wordbreakbreakword与wordbreakbreakall的实际应用效果

    > `.test2 { word-break: break-word; }`

    break-word同样也会在文本内容遇见边界时，强制将文本打断换行，不同的在于它会考虑单词是否完整，如果当前行无法放下需要被打断的单词，为了保持完整性，会将整个单词放到下一行进行展示

    ![image-20230413101025245](https://images-1305186932.cos.ap-beijing.myqcloud.com/images/202304131010297.png)

