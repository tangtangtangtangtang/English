Codepen地址：https://codepen.io/tangtangtangtangtang/pen/WXdogb

参数说明：

        /**
         * 获取文件统计信息。返回一个包含一下信息的对象。
         * * `modalImg` 图片的src
         * * `modalHeight` 模态框的高度
         * * `modalWidth` 模态框的宽度
         * * `modalBackgroundColor` 模态框的背景颜色
         * * `animation` 进入动画效果（animate.css），使用animate.css的关键字（关于展现的比如rollIn）即可
         * * `imgHeight` 图片的高度
         * * `imgWidth` 图片的宽度
         * * `modalContent`文字内容，为一个对象
         */
         
@example

```
init({
modalImg: 'http://img.hb.aicdn.com/d0b84f947ec4bbf544a739495ce323a631d0613876274-BJ1UU5_fw658',
modalHeight: "200px",
modalWidth: "200px",
modalBackgroundColor: "green",
modalContent: {
        title: 'This Is a Title',
        content: 'this is the  content',
},
animation: "animated rollIn",
imgHeight: null,
imgWidth: null
});
```
