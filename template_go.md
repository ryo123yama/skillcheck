# paizaスキルチェック用標準入力取得テンプレート（Go）

## 1行 1文字列（数値）
例）10  

```go
package main
import (
	"fmt"
	"bufio"
	"os"
	"strconv"
)

func main() {
	sc := bufio.NewScanner(os.Stdin)
	// 標準入力から1行取得する
	sc.Scan()
	// 数値に変換する
	var n, _ = strconv.Atoi(sc.Text())
	fmt.Printf("score = %d\n", n)
	fmt.Println("score = " + strconv.Itoa(n))
}
```
***
## 1行 空白区切り 2文字列（数値）
例）10 20  

```go
package main
import (
	"fmt"
	"bufio"
	"os"
	"strconv"
	"strings"
)

func main() {
	sc := bufio.NewScanner(os.Stdin)
	// 標準入力から1行取得する
	sc.Scan()
	// 配列に変換する
	var nums = strings.Split(sc.Text(), " ")
	// 数値に変換する
	var n1, _ = strconv.Atoi(nums[0])
	var n2, _ = strconv.Atoi(nums[1])
	fmt.Printf("score1 = %d, score2 = %d\n", n1, n2)
}
```
***
## 複数行 1行目データ数 空白区切り複数文字列（数値）
例）2  
 　　10 20  
 　　10 20  

```go
package main
import (
	"fmt"
	"bufio"
	"os"
	"strconv"
	"strings"
)

func main() {
	sc := bufio.NewScanner(os.Stdin)
	// 標準入力から1行取得する
	sc.Scan()
	var n, _ = strconv.Atoi(sc.Text())
	for i := 0; i < n; i++ {
		sc.Scan()
		// 配列に変換する
		var nums = strings.Split(sc.Text(), " ")
		// 数値に変換する
		var n1, _ = strconv.Atoi(nums[0])
		var f1, _ = strconv.ParseFloat(nums[1], 64)
		// 整数の割り算は小数点以下切捨て
		fmt.Printf("%d / 2 = ", n1)
		fmt.Println(n1 / 2)
		// 剰余の計算
		fmt.Printf("%d %% 2 = ", n1)
		fmt.Println(n1 % 2)
		// 浮動小数の割り算
		fmt.Printf("%g / 2 = ", f1)
		fmt.Println(f1 / 2)
		// 数値精度変換
		// int(f1), float64(n1)
	}
}
```

***
## 1行 1文字列
例）abcdefg  

```go
package main
import (
	"fmt"
	"bufio"
	"os"
	"strings"
)

func main() {
	sc := bufio.NewScanner(os.Stdin)
	// 標準入力から1行取得する
	sc.Scan()
	var s = sc.Text()
	// 1文字ずつ処理する
	for _, c := range s {
		if string(c) != "b" {
			fmt.Println(string(c))
		}
	}
	if len(s) > 5 {
		// 部分文字列を出力する
		fmt.Println(s[1:3])
	}
	// 指定文字の出現位置を出力する
	fmt.Println(strings.Index(s, "d"))
}
```

