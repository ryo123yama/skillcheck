# paizaスキルチェック用標準入力取得テンプレート（Python）

## 1行 1文字列（数値）
例）10  

```python
# を標準入力から取得する
n = int(input())
print("score = " + str(n))
```
***
## 1行 空白区切り 2文字列（数値）
例）10 20  

```python
# を標準入力から取得する
n1, n2 = map(int, input().split())
print("score1 = " + str(n1) + ", score2 = " + str(n2))
```
***
## 複数行 1行目データ数 空白区切り複数文字列（数値）
例）2  
 　　10 20  
 　　10 20  

```python
import math

# を標準入力から取得する
n = int(input())
for i in range(n):
    # を標準入力から取得する
	s = input().rstrip().split(' ')
    # 文字列→整数変換
	n1 = int(s[0])
    # 文字列→浮動小数点変換
	f1 = float(s[1])
	# 切り捨て除算
	print(str(n1) + " / 2 = " + str(n1 // 2)))
	# 余り
	print(str(n1) + " % 2 = " + str(n1 % 2))
    # 浮動小数点除算
	print(str(f1) + " / 2 = " + str(f1 / 2))
```

***
## 1行 1文字列
例）abcdefg  

```python
# を標準入力から取得する
s = input()
# 1文字ずつ処理する
for c in s:
	if c != 'b':
		print(c)
# 文字列長
if len(s) > 5:
    # 部分文字列
	print(s[1:3])
# 文字列検索（不在は-1が返る）
print(s.find("d"))
```

