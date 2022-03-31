---
title: "sed +α"
emoji: "✨"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["sed", "Linuxコマンド"]
published: false
---

# はじめに
Linux上でテキスト処理をする際に便利な「sedコマンド」について、あらゆる利用場面を例に魅力を紹介していけたらと思っています。

## 動作環境
:::message
- GNU bash, バージョン 4.4.20(1)-release (x86_64-redhat-linux-gnu)
- sed (GNU sed) 4.5
:::

# 最低限（急いでいる人向け）
置換処理
```txt:祝日リスト.csv
2020/01/01,元日
2020/01/13,成人の日
2020/02/11,建国記念の日
```
## オプション
### -e
### -E(-r)
### -z
### -n
## 置換・整形
```bash
sed 's/hoge/fuga/' 
```
```bash
sed 's/hoge/fuga/g' 
```
```bash:コメント行を削除
sed -n '/^ *#/!p' 
```
```bash:10行目から20行目まで表示
sed -n 10,20p
```
```bash:先頭10行を非表示
sed 10d
```
```bash
sed 's/:/\n/g' 
```
```bash
sed -E 's/ +/\n/g' 
```



# 置換処理
## sedと言えば置換
sedはスクリプト言語です。

## -nオプションとpコマンド
## 複数コマンド


# 行の抽出・削除


# 改行


# confの書き換え

# まとめ