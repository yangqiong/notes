### range
```
for _, v := range array {
    v.field = "foo"
    b = &v
}
```
1. v是原来数组中元素的一个拷贝，修改v不能修改原数组
2. 不要使用v的地址复制给其他变量，v的内容最终是array的最后一个元素