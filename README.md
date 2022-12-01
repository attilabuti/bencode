> ⚠️ This is a fork of https://github.com/anacrolix/torrent/tree/master/bencode ⚠️

Bencode encoding/decoding package. Uses similar API design to Go's json package.

## Install

```sh
go get github.com/attilabuti/bencode
```

## Usage

```go
package demo

import (
	bencode "github.com/attilabuti/bencode"
)

type Message struct {
	Query string `json:"q,omitempty" bencode:"q,omitempty"`
}

var v Message

func main(){
	// Encode
	data, err := bencode.Marshal(v)
	if err != nil {
		log.Fatal(err)
	}

	// Decode
	err := bencode.Unmarshal(data, &v)
	if err != nil {
		log.Fatal(err)
	}

	fmt.Println(v)
}
```
