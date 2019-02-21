# go_summary
```go
package main
import "fmt"
```

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
 
 
## 切片
var a [5]int = [5]int{23, 45, 21, 65, 43}
var b []int = a[1:4] 切片
var c = []int{6, 7, 8}

make创建切片
make([]type, len, cap)
func main() {
	i := make([]int, 5, 5)
	fmt.Println(i)
}


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
	    "zy": 1000
		"yz": 2000
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




















