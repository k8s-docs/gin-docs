---
title: "如果没有默认中间件"
draft: false
---

Use

```go
r := gin.New()
```

instead of

```go
// Default With the Logger and Recovery middleware already attached
r := gin.Default()
```
