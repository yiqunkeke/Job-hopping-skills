### 前端错误分类
1. 运行时错误 -- 一般使用 window.onerror 捕获
2. 资源加载错误  -- 使用window.addEventListener('error')捕获，window.onerror捕获不到资源加载错误
3. 接口错误

### JS 运行时错误
1. js运行时错误，一般使用 window.onerror 捕获
```
window.onerror = function (msg, url, lineNo, columnNo, error) 
    { 
       // 处理error信息
    } 
 
    window.addEventListener('error', event =>  
    {  
       console.log('addEventListener error:' + event.target); 
    }, true); 
    // true代表在捕获阶段调用，false代表在冒泡阶段捕获。使用true或false都可以
```
2. Uncaught (in promise)
当promise被reject并且错误信息没有被处理的时候，会抛出一个unhandledrejection，并且这个错误不会被window.onerror以及window.addEventListener('error')捕获，需要用专门的window.addEventListener('unhandledrejection')捕获处理
```
window.addEventListener('unhandledrejection', event => 
    { 
       console.log('unhandledrejection:' + event.reason); // 捕获后自定义处理
    });
```
3. console.error
一些特殊情况下，还需要捕获处理console.error，捕获方式就是重写window.console.error
```
var consoleError = window.console.error; 
window.console.error = function () { 
    alert(JSON.stringify(arguments)); // 自定义处理
    consoleError && consoleError.apply(window, arguments); 
};
```

总结：
使用window.onerror捕获JS运行时错误
使用window.addEventListener('unhandledrejection')捕获未处理的promise reject错误
重写console.error捕获console.error错误
在跨域脚本上配置crossorigin="anonymous"捕获跨域脚本错误
window.addEventListener('error')捕获资源加载错误。因为它也能捕获js运行时错误，为避免重复上报js运行时错误，此时只有event.srcElement inatanceof HTMLScriptElement或HTMLLinkElement或HTMLImageElement时才上报
重写window.XMLHttpRequest和window.fetch捕获请求错误