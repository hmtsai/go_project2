# go_project2

Here is another repo (another go module) to import github.com/hmtsai/go_project1/hello package

1. create main.go to import "github.com/hmtsai/go_project1/hello"
```
$ cat main.go
package main

import (
	"fmt"
	"github.com/hmtsai/go_project1/hello"
)

func main() {
	fmt.Println(hello.Greet2())
}
```

2. go mod init github.com/hmtsai/go_project2

It is better for one repo contain only one module. 
Here we create the go.mod file by go mod init "the same path of the repo"

4. go mod tidy

the go.mod is updated, you will see the **require** statment. 
that is the way that this module use other module's.


```
$ cat go.mod
module github.com/hmtsai/go_project2

go 1.16

require github.com/hmtsai/go_project1 v0.0.0-20210723054617-fe271f1d0203
```
