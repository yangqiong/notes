### range
```
for _, v := range array {
    v.field = "foo"
    b = &v
}
```
1. v是原来数组中元素的一个拷贝，修改v不能修改原数组
2. 不要使用v的地址复制给其他变量，v的内容最终是array的最后一个元素

### defer panic recover
1. panic或者其他异常抛出，会执行defer后的语句
2. 多个defer语句按照先进后出的原则
3. recover在defer函数中截取错误，继续执行后面语句类似于`try，catch`