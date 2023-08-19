---
layout: post
title:  "V: The fusion programming language I didn't know I needed"
date:   2023-03-29 00:00:00 -0500
categories: programming
---

#### As many of you know, the programming language I am most comfortable with is [Go](https://go.dev). However, just because a language is *comfortable* doesn't mean it's perfect. Enter [V](https://vlang.io).

![](https://vlang.io/img/veasel.png)
<center><i>V's incredibly adorable mascot, the Veasel.</i></center>

<br><br>

## Pros

Where do I even begin?

### The syntax
According to their website, V's syntax is about 80% identical to that of Go. Using the language, I believe it. Using V feels like Go on steroids sometimes. Here are some of the most important syntax changes for me:

#### - Error checks
In Go, error checks are frequent and bulky:
```go
var, err := someFunction();
if err != nil {
     panic(err)
}
```

Compare this to V, which simplifies it to:
```go
var := someFunction() or { panic(err) }
```

As you can see, much cleaner.

<br>

#### - Checking for presence in an array
In Go, to check for a value in an array, you'd do something like this:
```go
var present bool
for _, var := range arr; do {
     if var == 2 {
         present = true
         break
     }
}
fmt.Println(present)
```

In V:
```go
println(2 in arr)
```

<br>

#### - Methods on primitive types
In Go, you'd do something like this:
```go
// Given string `s`
strings.Replace(strings.Replace(s, "a", "A", -1), "b", "B", -1)
```

Whereas in V:
```go
// Given string `s`
s.replace('a', 'A').replace('b', 'B')
```

<br>

#### - Quick append to string
In Go:
```go
// Given string 's'
s = append(s, "owo")
```

In V:
```go
// Given string 's'
s += "owo"
```
<br>
#### **Now that was a lot of syntax.**

### Crazy fast compilation
V transpiles your code into C before compiling it, so it finishes shockingly quick. I'm talking **half a second** quick. You won't believe it until you try it.

<br>

### Live updates
V supports having a running program automatically update itself when code is compiled. This makes figuring out small bugs a breeze.

<br>

### Wide range of official libraries
The V libraries comprise [many, many different applications.](https://github.com/vlang/V/tree/master/examples)

<br>

### Control over memory management methods
V is memory safe and efficient by default. However, V also provides [many methods to manage memory.](https://github.com/vlang/v/blob/master/doc/docs.md#memory-management)

<br>

### Transpile C --> V
You can even translate DOOM into V code. [I'm not joking.](https://www.youtube.com/watch?v=6oXrz3oRoEg)

<br>

## Cons
### Only one variable declaration method
V only supports the `n := val` method of declaration; it does *not* support `var n int`, which I use in Go frequently.

<br>

### Lacking library support
As with most small programming languages, a lot of niche topics are not covered by people's open source projects. This could be a killer in some situations, as dealing with some APIs via straight web requests is even more of a pain than just using another language entirely.

<br>
<br>
<br>

## Final thoughts
Despite what the former content may lead you to believe, I am not maining V in the forseeable future. Go gives me nearly all of the tools I need, and does so in an almost-perfect fashion. For some projects, however, V shines on top, especially for quick scripts. Anyways, my blog post for the month of March is done, so that's good enough for me. Thank you for reading!
