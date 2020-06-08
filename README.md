# rollSlide

滚动列表插件，全部演示示例见 `demo.html`

## 开始

将`static\rollSlide.js`复制到你的项目里，并引用。

依赖于绝对定位，父级元素css请设置 `postion: relative`，下例为向上间隔滚动。

### html

`.roll-body`的`top`需要和`offset`保持一致。

``` html
<div class="roll">
    <ul class="roll-body" style="position: absolute; top: 0;">
        <li class="li-1">1</li>
        <li class="li-2">2</li>
        <li class="li-3">3</li>
        <li class="li-4">4</li>
        <li class="li-1">5</li>
        <li class="li-2">6</li>
        <li class="li-3">7</li>
        <li class="li-4">8</li>
        <li class="li-2">9</li>
    </ul>
</div>
```

### js

``` javascript
$('.roll').rollSlide({
    rollBody: '.roll-body', //滚动主体
    rollItem: 'li',         //滚动单位
    orientation: 'top',    //滚动方向
    offset: 0,              //偏移量(相对于orientation)
    num: 4,                 //每次滚动数量
    v: 1000,                //滚动动画时长ms
    space: 3000,            //间隔时间ms
    isRoll: true            //自动开始
});
```

## API

### $.rollSlide(options)

间隔滚动

#### options: Object

| 参数 | 类型 | 默认值 | 必需 | 说明 |
| -- | :---: | :---: | :---: | -- |
| rollBody | 选择器 | - | 是 | 滚动主体 |
| rollItem | 选择器 | - | 是 | 滚动单位 |
| orientation | string | 'left' | 否 | 滚动方向：'left','right','top','bottom' |
| offset | number | 0 | 否 | 偏移量(相对于orientation) |
| num | number | 1 | 否 | 每次滚动数量 |
| v | number | 0 | 否 | 滚动速度 |
| space | number | 5000 | 否 | 间隔时间ms，最小100ms |
| isRoll | boolean | - | 是 | 自动开始 |


### rollNoInterval(options)

不间断滚动

#### options: Object

| 参数 | 类型 | 默认值 | 必需 | 说明 |
| -- | :---: | :---: | :---: | -- |
| rollBody | 选择器 | - | 是 | 滚动主体 |
| rollItem | 选择器 | - | 是 | 滚动单位 |

  
#### 方法

| 方法 |  说明 |
| -- | -- |
| .left() | 左方向滚动 |
| .right() | 右方向滚动 |
| .top() | 上方向滚动 |
| .bottom() | 下方向滚动 |

#### 示例

``` javascript
$('#roll').rollNoInterval({
    rollBody: '.roll-body', //滚动主体
    rollItem: 'li',         //滚动单位
}).left();
```

            
## 遗留

- 未完善 插件 的 相同多个class选择器调用
  
- 未完善 .rollNoInterval()方法 暂停滚动 和继续滚动 的事件
