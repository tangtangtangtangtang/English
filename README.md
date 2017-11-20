# English

第一题在firstTopic下、第三题在thirdTopic下

面试题
英语流利说的笔试题
###1. 数据处理

给定一组数据，结构如下（仅作参考，不是实际数据）
```
const originalData = [
  { name: 'jch', age: 30, score: 90, sex: 1, lesson: 'math' },
  { name: 'oh', age: 31, score: 80, sex: 1, lesson: 'math' }, 
  { name: 'jia', age: 27, score: 70, sex: 0, lesson: 'math' }, 
  { name: 'jch', age: 30, score: 80, sex: 1, lesson: 'english' }
];
```
请用编写程序

给定age = x， 返回所有age大于x (不含等于) 的人的平均分，并按lesson和sex进行先后归类。
比如
```
returns { math: { 0: 73, 1: 82 }, english: { 0: 65, 1: 43 } }
```
要求： 
1). 你可以自己裸写，也可也使用lodash等第三方库。
2). 你需要编写一些单元测试用例，来测试你的算法是否正确。你可以真正搭建测试环境，也可以根据主流测试框架的api编写伪代码。

###2. 拓展ajax函数

已有一个通用的异步请求函数，签名如下

// options 是个object，一般有url， method等异步请求相关的参数。
ajax: (options) => Promise
但是ajax请求有概率会失败，

现在请基于这个函数，写一个带重试功能的函数：

ajaxWithRetry: (options) => Promise
其中重试的次数在options.retryCount中，如果使用者不传递，那么默认是5次。
新的函数里，重试retryCount次后依然失败，才算真的失败。

请思考怎么编写单元测试，确保你的函数行为是正确的。

###3. 请写一个弹窗demo

效果大致如图片 http://cdn.llscdn.com/fe-static/campus-test/modal.png
分为白色背景的内容区和半透明的遮罩

可以使用React、Vue或 angular 2(及之后版本), 也可以直接使用原始dom api

要求：

点击弹窗内容区，弹窗不消失；点击遮罩，弹窗消失。
弹窗的内容区需要上下左右都居中；遮罩需要一直覆盖整个屏幕。
只需兼容最新版chrome和safari。
本题需要展示，你可以通过github pages、codepen 等方式进行展示，或者提供详细步骤，让我们可以根据这些步骤看到最终效果。
加分项： 一些弹出和消失的动画；你的代码是最终是可复用的（可用以某种形式给你的同事直接使用，并可一定程度定制弹窗的外观等，而不是让他们复制黏贴）。
