# Web 性能指标组成

页面性能一直都是 Web 开发人员最关注的领域。以往度量页面性能指标的唯一方式，就是提高代码复杂程度和巧妙地使用 JavaScript 的 Date 对象。

**Web Timing API** 改变了这个局面，让开发人员通过 JavaScript 就能使用浏览器内部的度量结果，通过直接读取这些信息可以做任何想做的分析。

Web 计时机制的核心是 **window.performance** 对象。

window.performance 对象有两个属性，navigation 和 timing。

**navigation** 属性包含与页面导航有关的多个属性，即页面加载前的重定向次数、刚刚发生的导航类型。

**timing** 属性都是时间戳（从软件纪元开始经过的毫秒数），不同的事件会产生不同的时间戳。这些时间戳包括以下几个阶段：

这些属性的定义如下：

- navigationStart：开始导航到当前页面的时间。

- unloadEventStart：前一个页面的 unload 事件开始的时间。但只有在前一个页面与当前页面来自同一个域时这个属性才会有值；否则，值为 0。但实际上目前主流浏览器在实现时都将 unloadEvent 放置在了 fetchStart 之后，请避免踩坑。所以到底是 fetchStart 还是 responsestart ？

- unloadEventEnd：前一个页面的 unload 事件结束的时间。但只有在前一个页面与当前页面来自同一个域时这个属性才有值；否则，值为 0。

- redirectStart：到当前页面的重定向开始的时间。但只有在重定向的页面来自同一个域时这个属性才会有值；否则，值为 0。

- redirectEnd：到当前页面的重定向结束的时间。但只有在重定向的页面来自同一个域时这个属性才会有值；否则，值为 0。

- fetchStart：开始通过 HTTP GET 取得页面的时间。

- domainLookupStart：开始查询当前页面 DNS 的时间。

- domainLookupEnd：查询当前页面 DNS 结束的时间。

- connectStart：浏览器尝试连接服务器的时间。

- connectEnd：浏览器成功链接服务器的时间。

- secureConnectionStart：浏览器尝试以 SSL 方式链接服务器的时间。不使用 SSL 方式连接时，这个属性的值为 0；

- requestStart：浏览器开始请求页面的时间。

- responseStart：浏览器接收到页面第一字节的时间。

- responseEnd：浏览器接收到页面所有内容的时间。

- domLoading：document.readyState 变成“loading”的时间。

- domInteractive：document.readyState 变成“interactive”的时间。

- domContentLoadedEventStart：发生 DOMContentLoaded 事件的时间。

- domContentLoadedEventEnd：DOMContentLoaded 事件已经发生且执行完所有事件处理程序的时间。

- domComplete：document.readyState 变成“complete”的时间。

- loadEventStart：发生 load 事件的时间。

- loadEventEnd：load 事件已经发生且执行完所有事件处理程序的时间。

通过这些事件值，就可以全面了解页面在被加载到浏览器的过程中都经历了哪些阶段，而哪些阶段可能是影响性能的瓶颈。

# 指标

## Prompt for unload

### 组成

### 标准

### 影响因素

### 解决方案

## Redirect

## AppCache

## DNS

## TCP

## Request

## Response

## Processing

## Load