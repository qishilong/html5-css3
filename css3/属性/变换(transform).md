# transform

## 语法：

**transform**：none | <transform-function> +

### transform-function list:

**matrix()** = matrix([number](http://css.doyoe.com/values/numeric/number.htm)[,[number](http://css.doyoe.com/values/numeric/number.htm)]{5,5})

**matrix3d()** = matrix3d([number](http://css.doyoe.com/values/numeric/number.htm)[,[number](http://css.doyoe.com/values/numeric/number.htm)]{15,15})

**translate()** = translate([[translation-value](http://css.doyoe.com/properties/transform/transform.htm#translation-value)[,[translation-value](http://css.doyoe.com/properties/transform/transform.htm#translation-value)]?)

**translate3d()** = translate3d([translation-value](http://css.doyoe.com/properties/transform/transform.htm#translation-value),[translation-value](http://css.doyoe.com/properties/transform/transform.htm#translation-value),[length](http://css.doyoe.com/values/length/index.htm))

**translatex()** = translatex([translation-value](http://css.doyoe.com/properties/transform/transform.htm#translation-value))

**translatey()** = translatey([translation-value](http://css.doyoe.com/properties/transform/transform.htm#translation-value))

**translatez()** = translatez([length](http://css.doyoe.com/values/length/index.htm))

**rotate()** = rotate([angle](http://css.doyoe.com/values/angle/index.htm))

**rotate3d()** = rotate3d([number](http://css.doyoe.com/values/numeric/number.htm),[number](http://css.doyoe.com/values/numeric/number.htm),[number](http://css.doyoe.com/values/numeric/number.htm),[angle](http://css.doyoe.com/values/angle/index.htm))

**rotatex()** = rotatex([angle](http://css.doyoe.com/values/angle/index.htm))

**rotatey()** = rotatey([angle](http://css.doyoe.com/values/angle/index.htm))

**rotatez()** = rotatez([angle](http://css.doyoe.com/values/angle/index.htm))

**scale()** = scale([number](http://css.doyoe.com/values/numeric/number.htm)[,[number](http://css.doyoe.com/values/numeric/number.htm)]?)

**scale3d()** = scale3d([number](http://css.doyoe.com/values/numeric/number.htm),[number](http://css.doyoe.com/values/numeric/number.htm),[number](http://css.doyoe.com/values/numeric/number.htm))

**scalex()** = scalex([number](http://css.doyoe.com/values/numeric/number.htm))

**scaley()** = scaley([number](http://css.doyoe.com/values/numeric/number.htm))

**scalez()** = scalez([number](http://css.doyoe.com/values/numeric/number.htm))

**skew()** = skew([angle](http://css.doyoe.com/values/angle/index.htm)[,[angle](http://css.doyoe.com/values/angle/index.htm)]?)

**skewx()** = skewx([angle](http://css.doyoe.com/values/angle/index.htm))

**skewy()** = skewy([angle](http://css.doyoe.com/values/angle/index.htm))

**perspective()** = perspective([length](http://css.doyoe.com/values/length/index.htm))

**<translation-value>** = [length](http://css.doyoe.com/values/length/index.htm) | [percentage](http://css.doyoe.com/values/numeric/percentage.htm)

**默认值**：none

**适用于**：所有块级元素及某些内联元素

**继承性**：无

**动画性**：是

**计算值**：指定值，但相对长度会转换为绝对长度

**媒体**：视觉

## 取值：

- none：

    无转换

### 2D Transform Functions：

- [matrix()](http://css.doyoe.com/properties/transform/transform.htm#matrix)：

    以一个含六值的(a,b,c,d,e,f)变换矩阵的形式指定一个2D变换，相当于直接应用一个[a,b,c,d,e,f]变换矩阵

- [translate()](http://css.doyoe.com/properties/transform/transform.htm#translate)：

    指定对象的2D translation（2D平移）。第一个参数对应X轴，第二个参数对应Y轴。如果第二个参数未提供，则默认值为0

- [translatex()](http://css.doyoe.com/properties/transform/transform.htm#translatex)：

    指定对象X轴（水平方向）的平移

- [translatey()](http://css.doyoe.com/properties/transform/transform.htm#translatey)：

    指定对象Y轴（垂直方向）的平移

- [rotate()](http://css.doyoe.com/properties/transform/transform.htm#rotate)：

    指定对象的2D rotation（2D旋转），需先有 <' [transform-origin](http://css.doyoe.com/properties/transform/transform-origin.htm) '> 属性的定义

- [scale()](http://css.doyoe.com/properties/transform/transform.htm#scale)：

    指定对象的2D scale（2D缩放）。第一个参数对应X轴，第二个参数对应Y轴。如果第二个参数未提供，则默认取第一个参数的值

- [scalex()](http://css.doyoe.com/properties/transform/transform.htm#scalex)：

    指定对象X轴的（水平方向）缩放

- [scaley()](http://css.doyoe.com/properties/transform/transform.htm#scaley)：

    指定对象Y轴的（垂直方向）缩放

- [skew()](http://css.doyoe.com/properties/transform/transform.htm#skew)：

    指定对象skew transformation（斜切扭曲）。第一个参数对应X轴，第二个参数对应Y轴。如果第二个参数未提供，则默认值为0

- [skewx()](http://css.doyoe.com/properties/transform/transform.htm#skewx)：

    指定对象X轴的（水平方向）扭曲

- [skewy()](http://css.doyoe.com/properties/transform/transform.htm#skewy)：

    指定对象Y轴的（垂直方向）扭曲

### 3D Transform Functions：

- [matrix3d()](http://css.doyoe.com/properties/transform/transform.htm#matrix3d)：

    以一个4x4矩阵的形式指定一个3D变换

- [translate3d()](http://css.doyoe.com/properties/transform/transform.htm#translate3d)：

    指定对象的3D位移。第1个参数对应X轴，第2个参数对应Y轴，第3个参数对应Z轴，参数不允许省略

- [translatez()](http://css.doyoe.com/properties/transform/transform.htm#translatez)：

    指定对象Z轴的平移

- [rotate3d()](http://css.doyoe.com/properties/transform/transform.htm#rotate3d)：

    指定对象的3D旋转角度，其中前3个参数分别表示旋转的方向x,y,z，第4个参数表示旋转的角度，参数不允许省略

- [rotatex()](http://css.doyoe.com/properties/transform/transform.htm#rotatex)：

    指定对象在x轴上的旋转角度

- [rotatey()](http://css.doyoe.com/properties/transform/transform.htm#rotatey)：

    指定对象在y轴上的旋转角度

- [rotatez()](http://css.doyoe.com/properties/transform/transform.htm#rotatey)：

    指定对象在z轴上的旋转角度

- [scale3d()](http://css.doyoe.com/properties/transform/transform.htm#scale3d)：

    指定对象的3D缩放。第1个参数对应X轴，第2个参数对应Y轴，第3个参数对应Z轴，参数不允许省略

- [scalez()](http://css.doyoe.com/properties/transform/transform.htm#scalez)：

    指定对象的z轴缩放

- [perspective()](http://css.doyoe.com/properties/transform/transform.htm#perspective)：

    指定透视距离

## 说明：

**设置或检索对象的转换。**

- 对应的脚本特性为**transform**。

## rotate()

rotate(<angle>)

