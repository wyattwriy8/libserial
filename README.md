# libserial

[![Build Status](https://travis-ci.com/goiiot/libserial.svg)](https://travis-ci.com/goiiot/libserial) [![GoDoc](https://godoc.org/github.com/goiiot/libserial?status.svg)](https://godoc.org/github.com/goiiot/libserial) [![GoReportCard](https://goreportcard.com/badge/goiiot/libserial)](https://goreportcard.com/report/github.com/goiiot/libserial) [![codecov](https://codecov.io/gh/goiiot/libserial/branch/master/graph/badge.svg)](https://codecov.io/gh/goiiot/libserial)

Serial library for golang (no cgo)

## Usage

**TL;DR**: you can find a full example in [cmd/libserial/main.go](./cmd/libserial/main.go)

1.Import this package

```go
import (
    // ...
    "github.com/goiiot/libserial"
)
```

2.Open serial connection and check error

```go
// open serial port with default settings (9600 8N1)
conn, err := libserial.Open("/dev/serial0")

if err != nil {
    panic("hmm, how cloud it fail")
}
```

**Note**: You can add options when opening serial port, see [godoc - Option](https://godoc.org/github.com/goiiot/libserial#Option)

3.Read/Write data from serial connection

```go
buf := make([]byte, 64)
_, err := conn.Read(buf[:])

conn.Write([]byte{data})
```

## LICENSE

[![GitHub license](https://img.shields.io/github/license/goiiot/libserial.svg)](https://github.com/goiiot/libserial/blob/master/LICENSE.txt)

```text
Copyright Go-IIoT (https://github.com/goiiot)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```