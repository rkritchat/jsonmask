Jsonmask use for mask sensitive data from json format

## Installation
```shell
go get github.com/rkritchat/jsonmask

```

Code example

```go
package main

import (
	"fmt"
	"github.com/rkritchat/jsonmask"
)

var j = []byte(`{"foo":1,"bar":2,"baz":[3,4],"phoneNo":123456789, "newField":"test", "userInfo":{"firstname":"Kritchat", "lastname": "Rojanaphruk"}}`)

func main() {
	m := jsonmask.Init([]string{"newField"}) //optional
	t, err := m.Json(j)
	if err != nil {
		panic(err)
	}
	fmt.Println(*t)
}

```

Default Sensitive fields

```go
var defaultSensitiveData = []string{
	"name",
	"surName",
	"firstName",
	"lastName",
	"identification",
	"national",
	"card",
	"phone",
	"phoneNo",
	"number",
	"username",
	"password",
	"email",
	"address",
	"phoneNo",
}
```

enjoy!
