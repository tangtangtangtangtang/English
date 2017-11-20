1. 数据处理

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

我的代码如下：
```
function a(){
    var x = document.getElementById("input").value;
    x = parseInt(x);
    var result = {},temp = [] , resultAuxiliary = {} ,sex;
    for(var i = 0 ;i <originalData.length; i++){
        if(originalData[i].age>x){
            if(result[originalData[i].lesson] !== undefined){
                sex = originalData[i].sex;
                result[originalData[i].lesson][sex] +=originalData[i].score;
                resultAuxiliary[originalData[i].lesson][sex] ++;                
            }else{
                result[originalData[i].lesson] = {
                                                    1:0,
                                                    0:0
                                                 };
                resultAuxiliary[originalData[i].lesson] = {
                                                    1:0,
                                                    0:0
                                                 }; 
                sex =  originalData[i].sex;                             
                result[originalData[i].lesson][sex] += originalData[i].score;
                resultAuxiliary[originalData[i].lesson][sex] ++;
            }
        }
    }
    for(var key in result){
        if(resultAuxiliary[key][0] !== 0){
            result[key][0] = result[key][0]/resultAuxiliary[key][0];   
        }
        if(resultAuxiliary[key][1] !== 0 ){
            result[key][1] = result[key][1]/resultAuxiliary[key][1];            
        }
    }
    return result; 
}
```
