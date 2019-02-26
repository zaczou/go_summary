# go_summary

## 命名规范
### 骆驼命名法
Go语言应该使用 MixedCase(不要使用 names_with_underscores)
首字母缩写词都应该用大写,譬如ServeHTTP、sceneID、CIDRProcessor。


```go
package main
import (
    "fmt"
)
```
```go
声明：var a [3]int
声明初始化：var a [3]int = [3]int{1, 2, 3}
var a = [3]int{1, 2, 3}
var a  = [3]int{1, 2, 3}
var a = [...]int{1, 2, 3}
函数体：
   a := [3]int{1, 2, 3}

 for range 遍历
 for i, v := range a {
 }
 ```
 
## 切片
```
var a [5]int = [5]int{23, 45, 21, 65, 43}  //创建数组
var b []int = a[1:4] // 切片
var c = []int{6, 7, 8}  //直接创建切片
d := make([]type, len, cap)  //make创建切片
func main() {
	i := make([]int, 5, 5)
	fmt.Println(i)
}
```

## map
```go
func main(){
    personSalary := make(map[string]int)
    personSalary["zy"] = 1000
    personSalary["yz"] = 2000
    fmt.Println("personSalary")
)

func main() {
	personSalary := map[string]int {
	    "zy": 1000,
	    "yz": 2000,  // 记得有逗号
	}
	personSalary["mike"] = 3000
	employee := "zy"
	newEmp := "joe"
	value, ok := map[newEmp] 
	if ok == true {
	    fmt.Println
	} else {
	    fmt.Println(newEmp, "not found")
	}
	fmt.Println("salary of", employee, "is", personSalary[employee])
	fmt.Println(personSalary)
}
```

map遍历
```go

func main() {
	personSalary := map[string]int {
	    "zy": 1000
		"yz": 2000
	}
	personSalary["mike"] = 3000
	delete(personSalary, "zy") // 删除键
    for key, value := range personSalary {  // 不保证顺序相同
	    fmt.Println("personSalary[%s] = %d\n", key, value)
	}
}
```
map 之间不能使用 == 操作符判断，== 只能用来检查 map 是否为 nil

## 函数
### 多返回值
```go
package main
import (
    "fmt"
)

func rectProps(length, width float64)(float64, float64) {
    var area = length * width
    var perimeter = (length + width) * 2
    return area perimeter
}

func main() {
    area, perimeter := rectProps(10.8, 5.6)
    fmt.Prinf()
}
```
### 命名返回值
```go
func rectProps(length, width float64)(area, perimeter float64) {
    var area = length * width
    var perimeter = (length + width) * 2
    return // 不需要明确指定返回值，默认返回area, perimeter的值
}
### 空白符
```go
func main() {
    area, _ := rectProps(10.8, 5.6) // 返回值周长被丢弃
    fmt.Printf()
}
```

## 方法
### 创建方法
```go
func (t Type) methodname(parameter list) {
}
```
### 示例
```go
package main

import (
    "fmt"
    "math" // 小括号，没有逗号
)

type Rectangle struct {
    length float64
    width  float64
}

type Circle struct {
    radius float64
}

func (r Rectangle) Area() float64 {
    return r.length * r.width
}

func (c Circle) Area() float64 {
    return math.Pi * c.radius * c.radius
}

func main() {
    r := Rectangle{
         length: 10,
	 width:  5,
    } // 大括号，冒号，有逗号
	 
    fmt.Printf("Area of rectangle %d\n", r.Area())
    
    c := Circle{
         radius: 12,
    }
    fmt.Println()
}
```

### 指针接收器
```go
package main

import (
    "fmt"
)

type Employee struct {
    name string
    age  int
}

/*
使用值接收器的方法。
*/
func (e Employee) changeName(newName string) {
    e.name = newName
} 

// 使用指针接收器的方法
func (e *Employee) changeAge(newAge int) {
    e.age = newAge
}

func main() {
    e := Employee{
        name: "zy",
	age:  27,
    }
    fmt.Printf("Employee name before change: %s", e.name)
    e.changeName("zouyang")
    fmt.Printf("\nEmployee name after change: %s", e.name)

    fmt.Printf("\n\nEmployee age before change: %d", e.age)
    (&e).changeAge(26) // 与e.changeAge(51)作用相同
    fmt.Printf("\nEmployee age after change: %d", e.age)
}

/*
Employee name before change: zy
Employee name after change: zy

Employee age before change: 27
Employee age after change: 26
/*

```


















