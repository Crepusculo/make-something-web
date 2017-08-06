# 垂直居中的两个问题
@import "gallery/style.css"

总的来说 两个方面
+ 内嵌元素的居中方法
+ 匿名元素的居中方法

这是两个需要分开讨论的问题, 总的来说第一个比第二个简单
<!-- MDTOC maxdepth:6 firsth1:1 numbering:0 flatten:0 bullets:1 updateOnSave:1 -->

- [垂直居中的两个问题](#垂直居中的两个问题)   
- [内嵌元素的居中问题](#内嵌元素的居中问题)   
   - [表格](#表格)   
   - [里 · 表格](#里-·-表格)   
   - [绝对布局 position:absolute](#绝对布局-positionabsolute)   
   - [绝对布局 · 改进](#绝对布局-·-改进)   
   - [相对布局 position:relative](#相对布局-positionrelative)   
   - [相对-绝对布局](#相对-绝对布局)   
   - [弹性布局 flexbox](#弹性布局-flexbox)   
- [匿名元素的居中问题](#匿名元素的居中问题)   
- [Ref](#ref)   

<!-- /MDTOC -->
TODO::
+ 匿名元素的居中方法
    + 弹性布局 flexbox
    + 设置行高 (仅针对单行元素)
# 内嵌元素的居中问题
## 表格

@import "gallery/table.html"

(此处效果被`atom markdown-preview-enhanced` 覆盖)
反正这个方法很脏...

## 里 · 表格

@import "gallery/table-cell.html"

## 绝对布局 position:absolute

@import "gallery/absolute.html"

原理: $position = 0.5*rootheight - 0.5*correntheight$
从父元素到内部被居中的元素的高度是:
1. 先把居中子元素的顶部放到父元素高度的一半
2. 再将子元素的顶部向上移动其本身一半的高度

## 绝对布局 · 改进

## 相对布局 position:relative

@import "gallery/relative.html"

基本原理大概说起来就是
> "在相对布局中,先放一个50%高, 100%宽的占位元素。 这样一来下一个元素再`clear:both`一下, 下一个元素就找到 ‘中间’ 的位置了 这是真是太棒了"

+ -- 同样也有 `margin` 的干扰, 可以用和绝对布局的改进版同样的方法来回避这个问题

## 相对-绝对布局
@import "gallery/relative-absolute.html"

## 弹性布局 flexbox
@import "gallery/flexbox.html"
# 匿名元素的居中问题

# Ref
http://douglasheriot.com/tutorials/css_vertical_centre/demo4.html
_css secret_
