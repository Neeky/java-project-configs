## 读取配置文件
对于 spring 框架自己就能做的事情用起来是真的省心，之前用 python 解析配置文件还要自己来，对于 spring 来说都不用自己动手，配置一下就行了。

---

## 场景
给我的应用系统加一个版本号的功能，但是我又不想把这个写死在代码里面，于是想把这个放到配置里面。 application.yaml 关于 版本的部分如下。
```yaml
app:
  name: read-config-file-demo
  version: 0.0.1

```
---

## 添加一个用于读取配置的类
```java
package com.example.demo;

import lombok.Data;
import org.springframework.boot.context.properties.ConfigurationProperties;
import org.springframework.stereotype.Component;

@Data
@Component
@ConfigurationProperties("app")
public class AppConfig {
    private String name;
    private String version;
}

```

---

## 在 crontroller 中使用
```java
package com.example.demo;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RequestMapping("/about")
@RestController
public class DefaultController {
    @Autowired
    private AppConfig appConfig;

    @GetMapping("")
    public String index() {
        return this.appConfig.getName() + "-" + this.appConfig.getVersion();
    }
}

```
---

## 检查效果
```bash
curl http://127.0.0.1:8080/about/
read-config-file-demo-0.0.1

```

---