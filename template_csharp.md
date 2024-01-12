# paizaスキルチェック用標準入力取得テンプレート（C#）

## 1行 1文字列（数値）
例）10  

```C#
using System;

class Program
{
    static void Main()
    {
        // 標準入力から1行取得する
        var line = Console.ReadLine().Trim();
        // 数値に変換する
        var n = int.Parse(line);
        Console.WriteLine(n);
    }
}
```
***
## 1行 空白区切り 2文字列（数値）
例）10 20  

```C#
using System;

class Program
{
    static void Main()
    {
        // 標準入力から1行取得する
        var line = Console.ReadLine().Trim();
        // 配列に変換する
        string[] ary = line.Split(' ');
        Console.WriteLine("score1 = {0} , score2 = {1}", ary[0], ary[1]);
    }
}
```
***
## 複数行 1行目データ数 空白区切り複数文字列（数値）
例）2  
 　　10 20  
 　　10 20  

```C#
using System;

class Program
{
    static void Main()
    {
        // 標準入力から1行取得する
        var line = Console.ReadLine().Trim();
        // 数値に変換する
        var n = int.Parse(line);
        for (var i = 0; i < n; i++)
        {
            string[] ary = Console.ReadLine().Trim().Split(' ');
            var intnum = int.Parse(ary[0]);
            var floatnum = float.Parse(ary[1]);
            Console.WriteLine("{0} / 2 = {1}", intnum, intnum / 2);
            Console.WriteLine("{0} % 2 = {1}", intnum, intnum % 2);
            Console.WriteLine("{0} / 2 = {1}", floatnum, floatnum / 2);
        }
    }
}
```

***
## 1行 1文字列
例）abcdefg  

```C#
using System;
using System.Text;

class Program
{
    static void Main()
    {
        // 標準入力から1行取得する
        var line = Console.ReadLine().Trim();
        // 1文字ずつ処理する
        foreach (char c in line) {
            if (c != 'b') {
                Console.WriteLine(c);
            }
        }
        if (line.Length > 5) {
            // 部分文字列を出力する
            Console.WriteLine(line.Substring(1, 3));
        }
        // 指定文字の出現位置を出力する
        Console.WriteLine(line.IndexOf("d"));
    }
}
```

