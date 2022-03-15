`@authon:aslanwang`
`@time:2022-3-7`
# 关于`Go`的常用`package`
## `fmt`
### `%v,%+v,%#v`的区别
* `%v`输出所有的值
* `%+v`先输出字段名（如果有），再输出对应值
* `%#v`先输出对象类型，再输出对象的值：字段名（如果有）+对应值
```
type Student struct {
	name string
	age  int16
}

func testFmt1() {
	s1 := new(Student)
	s1.name = "张三"
	fmt.Printf("%v\n", s1)  // &{张三 0}
	fmt.Printf("%+v\n", s1) // &{name:张三 age:0}
	fmt.Printf("%#v\n", s1) // &main.Student{name:"张三", age:0}

	a2 := []string{"Jenny, Danny"}
	fmt.Printf("%v\n", a2)  // [Jenny, Danny]
	fmt.Printf("%+v\n", a2) // [Jenny, Danny]
	fmt.Printf("%#v\n", a2) // []string{"Jenny, Danny"}
}
```