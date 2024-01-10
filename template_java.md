# paizaスキルチェック用標準入力取得テンプレート（Java）

## 1行 1文字列（数値）
例）10

```java
        Scanner sc = new Scanner(System.in);
        // を標準入力から取得する
        int n = sc.nextInt();
        sc.close();
```
***
## 1行 空白区切り 2文字列（数値）
例）10 20

```java
        Scanner sc = new Scanner(System.in);
        // を標準入力から取得する
        int h = sc.nextInt();
        // を標準入力から取得する
        int w = sc.nextInt();
        sc.close();
```
***
