---
title: "快速开始"
draft: false
weight: 2
---

在这个快速入门, 我们将搜集来自代码段的见解，并学习如何:

## 要求

- Go 1.9 以上

> Go 1.7 或 Go 1.8 很快将不再支持.

## 安装

安装 Gin 包, 您需要首先安装 Go 并设置 Go 工作区.

1. 下载并安装它:

```sh
$ go get -u github.com/gin-gonic/gin
```

2. 导入它在你的代码:

```go
import "github.com/gin-gonic/gin"
```

3. (可选的) 导入 `net/http`. 如果使用常量如 `http.StatusOK` 这对实例是必需的 .

```go
import "net/http"
```

1. 创建项目文件夹和 `cd` 内

```sh
$ mkdir -p $GOPATH/src/github.com/myusername/project && cd "$_"
```

2. 起始模板复制你的项目中

```sh
$ curl https://raw.githubusercontent.com/gin-gonic/examples/master/basic/main.go > main.go
```

3. 运行项目

```sh
$ go run main.go
```

## 入门

> 不确定如何编写和执行`Go`代码？ [点击这里](https://golang.org/doc/code.html).

首先，创建一个名为 `example.go` 文件:

```sh
# assume the following codes in example.go file
$ touch example.go
```

接下来，把下面的代码房子`example.go`内:

```go
package main

import "github.com/gin-gonic/gin"

func main() {
	r := gin.Default()
	r.GET("/ping", func(c *gin.Context) {
		c.JSON(200, gin.H{
			"message": "pong",
		})
	})
	r.Run() // listen and serve on 0.0.0.0:8080
}
```

和, 您可以通过 `go run example.go` 运行代码 :

```sh
# run example.go and visit 0.0.0.0:8080/ping on browser
$ go run example.go
```
