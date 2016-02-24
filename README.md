# interpol

[![License](http://img.shields.io/badge/license-MIT-red.svg?style=flat)](https://github.com/imkira/go-interpol/blob/master/LICENSE.txt)
[![GoDoc](https://godoc.org/github.com/imkira/go-interpol?status.svg)](https://godoc.org/github.com/imkira/go-interpol)
[![Build Status](http://img.shields.io/travis/imkira/go-interpol.svg?style=flat)](https://travis-ci.org/imkira/go-interpol)
[![Coverage](http://img.shields.io/codecov/c/github/imkira/go-interpol.svg?style=flat)](https://codecov.io/github/imkira/go-interpol)

interpol is a [Go](http://golang.org) package for doing format-string like
string interpolation using named parameters.

Currently, a template only accepts variable placeholders delimited by brace
characters (eg. "Hello {foo} {bar}").

## Install

First, you need to install the package:

```go
go get -u github.com/imkira/go-interpol
```

## Documentation

For advanced usage, make sure to check the
[available documentation here](http://godoc.org/github.com/imkira/go-interpol).

## Example

The following code should use `interpol.WithMap` function, which simply
replaces every key with the corresponding value of the specified map.
When run, it should output `Hello World!!!`.

```go
package main

import "github.com/imkira/go-interpol"

func main() {
	m := map[string]string{
		"foo": "Hello",
		"bar": "World",
	}
	str, err := interpol.WithMap("{foo} {bar}!!!", m)
  if err != nil {
    fmt.Printf("Error: %v\n", err)
    return
  }
  fmt.Println(str)
}
```

## Contribute

Found a bug? Want to contribute and add a new feature?

Please fork this project and send me a pull request!

## License

go-interpol is licensed under the MIT license:

www.opensource.org/licenses/MIT

## Copyright

Copyright (c) 2016 Mario Freitas. See
[LICENSE](http://github.com/imkira/go-interpol/blob/master/LICENSE)
for further details.
