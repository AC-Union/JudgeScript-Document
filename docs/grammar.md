# 语法入门

JudgeScript 使用 [Anko](https://github.com/mattn/anko) 作为脚本执行器。

## 基本语法

Anko 具有与 Golang 极其相似的语法。

在 JudgeScript 里面，入口点是一个名为 Judge 的 module。

定义如下：

```go
module Judge {

}
```

在一个 module 里，可以定义函数。

对于函数定义的语法：

```go
func functionName(argument01, argument02) {
    // Function body
}
```

在 Anko 中，分号是可以省略的。

定义一个变量的方法：

```go
var variableName = "variableValue"
```

Anko 是弱类型的。

调用一个函数：

```go
doSomeFunction("arguments")
```

获取一个 struct 的值或在上面执行函数：

```go
acoj.content("hello")
ctx.Code
```

通过 “.” 分割名称和方法/变量名。

## 对于包的引用

在 Anko 中，可以直接访问 Golang 标准库中大部分函数和类。但是为了安全起见，我们禁止了一部分。例如 `syscall`, `os.Stdin`, `os.Stdout`, `os.Stderr`, `runtime`, `ioutil.ReadFile`, `ioutil.WriteFile`, `ioutil.ReadDir`, `bufio`, `fmt.Println` 等等。当然，在不同的场景，我们的限制并不相同。

引用包的方法：

```go
var fmt = import("fmt")

fmt.Sprintf("Hello, %v", "ACUnion") // Hello, ACUnion
```
