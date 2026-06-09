INNOVATOR Month3 Week2
# input文とelifを知ろう

# 目的
input文を使って、キーボードから入力した文字を変数に代入する<br>
if / else / elif を使って、入力された言葉によって返事が変わるプログラムを作る<br>

# 目次
- [前回の復習](#前回の復習)
- [elseを復習しよう](#elseを復習しよう)
- [input文について](#input文について)
- [input文とif文を組み合わせよう](#input文とif文を組み合わせよう)
- [参考文献](#参考文献)

</details>

# 今日やること

チャットボットを作成する

# 前回の復習
## if文とは<br>
if文は、条件を満たしたとき(True)だけ処理を実行する。<br>

前回は、点数が合格点以上かどうかを判定するプログラムを作りました。<br>

```python
# 点数を変数に入れる
score = 80

# scoreが70以上なら、合格と表示する
if score >= 70:
  print("合格")
```

このプログラムでは、`score >= 70` が True なので、`print("合格")` が実行されます。<br>

今回は、点数ではなく**自分が入力した言葉**を使います。<br>
そのため、今日よく使う条件式は `==` です。<br>

## if文の形<br>
if文の形をもう一度確認しましょう。<br>

```python:python
if 条件式:
  条件を満たしたときの処理
```

大事なポイントは3つです。<br>

- `if` の後に条件式を書く<br>
- 条件式の後に `:` を書く<br>
- if文の中の処理は、インデントを開ける<br>

## == の意味<br>
`==` は、**左**と**右**が**同じかどうか**を調べる記号です。<br>

例えば、以下の条件式を考えます。<br>

```python
tenki == "くもり"
```

これは、<br>

```
変数 tenki の中身は「くもり」と同じですか？
```

という意味です。<br>
同じなら True、違う(晴れ・雨など)なら False になります。<br>

## = と == の違い<br>
`=` と `==` は意味が違います。<br>

```python
word = "こんにちは"
```

これは、`word` に `"こんにちは"` を入れるという意味です。<br>

```python
word == "こんにちは"
```

これは、`word` と `"こんにちは"` が同じかを調べるという意味です。<br>

## Work1 同じかどうかを調べよう<br>
以下のプログラムを実行してください。<br>

```python
tenki = "雨"

print(tenki == "雨")
```

実行すると`True`と表示されるはずです。<br>

これは、

```
tenki の中身が"雨"と同じだよ
```

という意味の`True`です。

tenki の中身をくもりにすると何が表示されるかを考えてみてください。

このように、合ってるか間違ているか、 True か False かを判定してくれるのが条件式です。

条件式を使って、True の時だけ何かを実行するのが、以下のような if 文です。

```python
tenki = "雨"

if tenki == "雨":
  print("傘が必要です。")
```

実行すると、`tenki == "雨"`が`True`になるので、`傘が必要です。` と表示されるはずです。<br>

次に、`tenki` の**中身だけ**を `"くもり"` に変えて実行してください。<br>

```python:demo.py
tenki = "くもり"

if tenki == "雨":
  print("傘が必要です。")
```

この場合、条件を満たしていないので、何も表示されません。<br>
これはエラーではありません。<br>
**条件を満たさなかったので、if文の中の処理が実行されなかった**ということです。<br>

# elseを復習しよう
## 条件を満たさなかったときの処理<br>
if文だけでは、条件を満たしたときの処理しか書けません。<br>
条件を満たさなかったときの処理を書くには、**else** を使います。<br>

```python:python
if 条件式:
  条件を満たしたときの処理
else:
  条件を満たさなかったときの処理
```

例えば、以下のようなプログラムです。<br>

```python:demo.py
tenki = "雨"

if tenki == "雨":
  print("傘が必要です。")
else:
  print("傘は不要です。")
```

## Work2 elseを使ってみよう<br>
上のプログラムの `tenki` を、次の3つに変えて実行してください。<br>

```
晴れ
くもり
雨
```

それぞれ、どのように表示されるか確認しましょう。<br>

# input文について

## STEP1 input文を使ってみよう
ここからは、新しく **input文** を学びます。<br>
input文を使うと、自分で入力した文字を変数に代入できるようになります。<br>

まずは、`()` の中を空にした状態で使ってみます。<br>

```python:demo.py
num = input()
print(num+"円払ってください")
```

このプログラムを実行すると、入力できる状態になります。<br>
好きな数字を入力して、Enterキーを押してください。<br>

## STEP2 input文の説明
最初のプログラムは、変数に入力された文字を代入しています。

```python:demo.py
# 入力された文字を変数に入れる
test = input()
```

このプログラムでは、入力した文字が `num` に保存されます。<br>
その後、`print(num)` で、入力した文字を表示しています。<br>

## STEP3 inputの中に文字を入れてみよう
`input()` の中には、入力するときに表示する案内文を書くことができます。<br>

今のプログラムを、以下のように変更してください。<br>

```python:demo.py
num = input("何円持ってますか？:")
print(num+"円払ってください")
```

`input("何円持ってますか？: ")` と書くと、入力欄に `何円持ってますか？: ` と表示されます。<br>
入力する人に、何を入力すればよいかを伝えられるので、プログラムが使いやすくなります。<br>

## Work5 名前を使ってあいさつしよう<br>
次のプログラムを実行してください。<br>

```python:demo.py
# 入力された名前を変数に入れる
name = input("名前を入力してください: ")

# 名前を使ってあいさつする
print("こんにちは、" + name + "さん")
```

実行して、自分の名前を入力してみましょう。<br>

# input文とif文を組み合わせよう
ここからは、input文とif文を組み合わせます。<br>
入力された言葉によって、表示する返事を変えるプログラムを作ります。<br>

まずは、合言葉を判定するプログラムを作りましょう。合言葉は**何でも構いません。**<br>

```python:demo.py
# 入力された合言葉を変数に入れる
word = input("合言葉を入力してください: ")

# 合言葉がpythonと同じなら正解、違うなら不正解と表示する
if word == "python":
  print("正解！")
else:
  print("合言葉が違います")
```

このプログラムでは、入力された文字が `"python"` と同じかどうかを調べています。<br>
同じなら `正解！`、違うなら `合言葉が違います` と表示されます。<br>

## STEP1 elifを使ってみよう
### elifとは<br>
if と else だけでは、結果を2つに分けることしかできません。<br>

```
条件に合う
条件に合わない
```

しかし、会話プログラムでは、入力された言葉によって、いろいろな返事をしたいことがあります。<br>
そのようなときに使うのが、**elif** です。<br>

```python:python
if 条件式1:
  条件式1を満たしたときの処理
elif 条件式2:
  条件式2を満たしたときの処理
else:
  どの条件も満たさなかったときの処理
```

`elif` は、**そうでなければ、次の条件を調べる**という意味です。<br>

### elifを使った会話プログラム<br>
次のプログラムを実行してください。<br>

```python:demo.py
# 入力された言葉を変数に入れる
message = input("話しかけてください: ")

# 入力された言葉に合わせて返事を変える
if message == "こんにちは":
  print("こんにちは！")
elif message == "ありがとう":
  print("どういたしまして！")
else:
  print("その言葉はまだわかりません")
```

このプログラムでは、上から順番に条件を調べます。<br>

```
message は「こんにちは」と同じ？
↓ 違う場合
message は「ありがとう」と同じ？
↓ 違う場合
どれにも当てはまらないので else を実行
```

## STEP2 返事の種類を増やそう
`elif` を増やすと、返事の種類を増やすことができます。<br>

```python:demo.py
# 入力された言葉を変数に入れる
message = input("話しかけてください: ")

# 入力された言葉に合わせて返事を変える
if message == "こんにちは":
  print("こんにちは！")
elif message == "ありがとう":
  print("どういたしまして！")
elif message == "元気？":
  print("元気です！")
else:
  print("その言葉はまだわかりません")
```

`elif` は、必要に応じて増やすことができます。<br>
ただし、条件が増えるとプログラムが長くなるので、コメントを書いて整理することが大切です。<br>

### Work8 返事を1つ追加しよう<br>
上のプログラムに、好きな言葉と返事を1つ追加してください。<br>

例：<br>

```python:demo.py
elif message == "好きな食べ物は？":
  print("カレーが好きです！")
```

<details><summary>答えの例</summary>

```python:demo.py
# 入力された言葉を変数に入れる
message = input("話しかけてください: ")

# 入力された言葉に合わせて返事を変える
if message == "こんにちは":
  print("こんにちは！")
elif message == "ありがとう":
  print("どういたしまして！")
elif message == "元気？":
  print("元気です！")
elif message == "好きな食べ物は？":
  print("カレーが好きです！")
else:
  print("その言葉はまだわかりません")
```

</details>

# Mission Innovator Month5 week2

配布プリントを参照してください。

# 参考文献
[1] https://www.python.org/<br>
[2] https://docs.python.org/ja/3/tutorial/controlflow.html<br>
[3] https://docs.python.org/ja/3/library/functions.html#input<br>
[4] Eric Matthes. "Python Crash Course, 3rd Edition: A Hands-On, Project-Based Introduction to Programming". No Starch Press Inc.<br>

**Acknowledgement**  
This material was reviewed and refined with the assistance of ChatGPT (OpenAI).

Kazuma Aoyama(kazuma-a@akamafu.com)