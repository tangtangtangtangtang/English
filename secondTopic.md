已有一个通用的异步请求函数，签名如下
```
// options 是个object，一般有url， method等异步请求相关的参数。
ajax: (options) => Promise
```
但是ajax请求有概率会失败，

现在请基于这个函数，写一个带重试功能的函数：
```
ajaxWithRetry: (options) => Promise
```
其中重试的次数在options.retryCount中，如果使用者不传递，那么默认是5次。
新的函数里，重试retryCount次后依然失败，才算真的失败。

请思考怎么编写单元测试，确保你的函数行为是正确的。

 ``` 

function ajax(options) {
    var xhr = new XMLHttpRequest();
    var defaultOptions = {
        url: "",
        method: "get",
    }
    for (var key in options) {
        defaultOptions[key] = options[key];
    }
    if (defaultOptions.url === "") {
        return;
    }
    var promise = new Promise(function (reslove, reject) {
        xhr.open(defaultOptions.method, defaultOptions.url);
        xhr.onreadystatechange = handler;
        xhr.send();
        function handler() {
            if (this.readyState !== 4) {
                return;
            }
            if (this.status > 200 && this.status < 300) {
                if (!defaultOptions.success) {
                    return;
                }
                defaultOptions.success(this.response);
            } else {
                if (!defaultOptions.fail) {
                    return;
                }
                defaultOptions.fail(this.response);
            }
        }
    });
    return promise;
}

 ```
