---
title: "测试"
draft: false
weight: 7
---

## 如何为 Gin 编写测试用例?

`net/http/httptest` 包是 HTTP 测试优选方式.

{{<highlight go>}}

package main

func setupRouter() *gin.Engine {
r := gin.Default()
r.GET("/ping", func(c *gin.Context) {
c.String(200, "pong")
})
return r
}

func main() {
r := setupRouter()
r.Run(":8080")
}
{{</highlight>}}

Test for code example above:

```go
package main

import (
	"net/http"
	"net/http/httptest"
	"testing"

	"github.com/stretchr/testify/assert"
)

func TestPingRoute(t *testing.T) {
	router := setupRouter()

	w := httptest.NewRecorder()
	req, _ := http.NewRequest("GET", "/ping", nil)
	router.ServeHTTP(w, req)

	assert.Equal(t, 200, w.Code)
	assert.Equal(t, "pong", w.Body.String())
}
```
