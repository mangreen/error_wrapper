# Error Wrapper

> error wrapper for golang

## Install

```bash
go get -u github.com/androvideo-dev/error_wrapper
```

## How to use

```golang
package main

import (
	"github.com/androvideo-dev/error_wrapper"

	"errors"
	"fmt"
)

func main() {
	w := error_wrapper.ErrorWrapper{}
	w.Do(func() error {
		fmt.Println("task 1")
		return nil
	})
	w.Do(func() error {
		fmt.Println("task 2")
		return errors.New("oops")
	})
	w.Do(func() error {
		fmt.Println("task 3")
		return nil
	})

	fmt.Println(w.GetErr())
}
// result
// task 1
// task 2
// oops
```
