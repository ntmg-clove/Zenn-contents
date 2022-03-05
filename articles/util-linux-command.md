---
title: "Linuxコマンドで色々やる"
emoji: "🌊"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Linuxコマンド"]
published: false
---

# カレンダーの月の英語表記を取得
## 実行コマンド
```bash
$ LANG=C cal -y | grep -Eo '[A-Z][a-z]{2,}'
```

## 出力結果
:::details クリックして表示
January
February
March
April
May
June
July
August
September
October
November
December
:::

## コメント
ロケール設定がポイント。
正規なやり方だとdateコマンドとかを使うのでしょうか…。


# スケジュール表作成
## 実行コマンド
```bash
echo {{0,1}{0..9},2{0..3}}:{00,30} | tr ' ' '\n'
```
## 出力結果

:::details クリックして表示
00:00
00:30
01:00
01:30
02:00
02:30
03:00
03:30
04:00
04:30
05:00
05:30
06:00
06:30
07:00
07:30
08:00
08:30
09:00
09:30
10:00
10:30
11:00
11:30
12:00
12:30
13:00
13:30
14:00
14:30
15:00
15:30
16:00
16:30
17:00
17:30
18:00
18:30
19:00
19:30
20:00
20:30
21:00
21:30
22:00
22:30
23:00
23:30
:::

## コメント

# IPv4アドレスの生成
↑と少し似ています。
```bash
# クラスBのプライベートアドレス
echo 192.168.{0..255}.{0..255} 
```

# 素数生成
```bash
factor {2..100} | tr -d : | awk '$1==$2'
```
この記事でも紹介していますが、後々考えてみるとfactorの方が楽だったなと思いました…