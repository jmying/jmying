---
title: Hello World ! Spring Boot vs Node.js
date: 2017-06-29 18:26:13
categories:
- spring 全家桶
tags:
- Server-Side
- node.js
- spring
- spring boot
- java
---

在很长的时间里，java给我的印象是很low的。看到java的web应用jsp + servlet亦或是 struts2。繁琐的编码，配置，再打包发布到web容器，我始终认为生命不应如此浪费。原谅我没有经历过那个web刚刚诞生的年代，我知道当时拥有jvm虚拟机的java的推出是有多么伟大的创新，然而我就是不满足。

然而诸如node.js等后生晚辈从编码到运行起来是如此简介,没有对比就没有伤害

#### example.js
```
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n暴击传统java');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```
一键就启动,绝不拖泥带水

``` bash
$ node example.js
Server running at http://127.0.0.1:3000/
```
#### 其实java也可以，因为有你，Spring Boot

hello/SampleController.java

```
package hello;

import org.springframework.boot.*;
import org.springframework.boot.autoconfigure.*;
import org.springframework.stereotype.*;
import org.springframework.web.bind.annotation.*;

@Controller
@EnableAutoConfiguration
public class SampleController {

    @RequestMapping("/")
    @ResponseBody
    String home() {
        return "Hello World!";
    }

    public static void main(String[] args) throws Exception {
        SpringApplication.run(SampleController.class, args);
    }
}
```
#### 只多一步，一样酸爽的启动服务了！

``` bash
$ javac  hello/SampleController.java
$ java  hello/SampleController
```

#### 一样的酸爽，同样的简洁。为什么不继续node.js 又走回头路？
### 透过现象看本质
编译型语言vs 解释行语言

