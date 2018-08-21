# 评测库参考

我们为您提供了一套完整的评测库。

## 访问方式

我们已经自动为您 import 了这套评测库。

你可以直接使用 `acoj.*` 来访问它。

例子：

```go
acoj.path("hello")
```

提醒：除了这套评测库方法名是小驼峰外，其余都是大驼峰。

## 在 problem.yml 中的访问

您可以直接这样写:

```yaml
Content: $$acoj.content("something")
Limit:
  MemoryLimit: $$acoj.parseSize("12MB")
```

## 函数参考

| 名称          | 介绍                                                                                       | 参数              | 返回                         | 例子                      |
| ------------- | ------------------------------------------------------------------------------------------ | ----------------- | ---------------------------- | ------------------------- |
| content       | 获取题目目录下某个文件内容，仅在 problem.yml 使用，在 judge.ank 中使用会出现莫名其妙的错误 | 文件名:string     | 文件内容:string              | acoj.content("judge.ank") |
| path          | 获取某个目录的路径，仅在 problem.yml 使用，在 judge.ank 中使用会出现莫名其妙的错误         | 路径名:string     | 完整路径:string              | acoj.path("disklayer")    |
| bytesToString | 将 `[]byte` 转为 `string`                                                                  | bytes:[]byte      | str:string                   | acoj.bytesToString(byts)  |
| stringToBytes | 将 `string` 转为 `[]byte`                                                                  | str:string        | bytes:[]byte                 | acoj.stringToBytes(str)   |
| getJudgeData  | 获取评测数据，参数是在 JudgeData 配置项指定的目录下的文件名                                | 文件名:string     | 文件内容:string              | acoj.getJudgeData("1.in") |
| parseTime     | 解析时间字符串                                                                             | 时间字符串:string | 时间的数值（单位 us）:string | acoj.parseTime("120ms")   |
| parseSize     | 解析大小字符串                                                                             | 大小字符串:string | 大小的数值（单位 KB）:string | acoj.parseSize("64MB")    |

[返回主页](/README.md)
