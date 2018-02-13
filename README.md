# go-i3bar-protocol [![GoDoc](https://godoc.org/github.com/seankhliao/go-nord?status.svg)](https://godoc.org/github.com/seankhliao/go-nord) [![Build Status](https://img.shields.io/travis/seankhliao/go-nord.svg?style=flat-square)](https://travis-ci.org/seankhliao/go-nord) [![Go Report Card](https://goreportcard.com/badge/github.com/seankhliao/go-nord)](https://goreportcard.com/report/github.com/seankhliao/go-nord)

Go types for use with [i3bar](https://i3wm.org/docs/i3bar-protocol.html)

## Install

```bash
go get github.com/seankhliao/go-i3bar-protocol
```

## Example

```go
package main

import (
        "github.com/seankhliao/go-i3bar-protocol"
        "encoding/json"
        "fmt"
        "os"
)

func main() {
        e := json.NewEncoder("os.Stdout")
        e.Encode(protocol.MinimalHeader())

        // requires opening brace of inifinite array
        // is not valid json
        os.Stdout.Write([]byte("["))

        var blocks []protocol.Block
        // fill blocks

        for {
                e.Encode(blocks)
        }
}
```

## License

The MIT License (MIT) - see [`LICENSE.md`](LICENSE.md) for more details