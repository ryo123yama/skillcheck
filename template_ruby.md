# paizaスキルチェック用標準入力取得テンプレート（Ruby）

## 1行 1文字列（数値）
例）10  

```ruby
# 標準入力から1行取得する
line = gets.to_i
print "score = #{ line }\n";
printf "score = %d\n", line;
```
***
## 1行 空白区切り 2文字列（数値）
例）10 20  

```ruby
# 標準入力から1行取得して配列に変換する
s = gets.chomp.split(" ")
print "score1 = #{ s[0] }, score2 = #{ s[1] }\n";
printf("score1 = %d, score2 = %d\n", s[0], s[1]);
```
***
## 複数行 1行目データ数 空白区切り複数文字列（数値）
例）2  
 　　10 20  
 　　10 20  

```ruby
# 標準入力から1行取得する
line = gets.to_i
line.times do
	# 標準入力から1行取得して配列に変換する
	num = gets.chomp.split(" ")
	# 整数の割り算は小数点以下切捨て
	puts "#{ num[0] } / 2 = " + (num[0].to_i / 2).to_s
	# 剰余の計算
	puts "#{ num[0] } % 2 = " + (num[0].to_i % 2).to_s
	# 浮動小数の割り算
	puts "#{ num[1] } / 2 = " + (num[1].to_f / 2).to_s
end
```

***
## 1行 1文字列
例）abcdefg  

```ruby
# 標準入力から1行取得する
str = gets
# 1文字ずつ処理する
str.each_char {|c|
    if c != "b" then
    	puts c
    end
}
if str.length > 5 then
	# 部分文字列を出力する
	puts str[1, 3]
end
# 指定文字の出現位置を出力する
puts str.index("d")
```

