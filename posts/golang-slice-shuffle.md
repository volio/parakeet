---
title: Golang Slice Shuffle
date: 2020-01-21 17:28:00
tags: []
---

使用 rand 包提供的 Shuffle 方法

```
package main

import (
	"fmt"
	"math/rand"
	"strings"
)

func main() {
	words := strings.Fields("ink runs from the corners of my mouth")
	rand.Shuffle(len(words), func(i, j int) {
		words[i], words[j] = words[j], words[i]
	})
	fmt.Println(words)

}
```
