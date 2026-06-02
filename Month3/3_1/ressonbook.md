# INNOVATOR Month3 Week1
# if文で信号機を作ろう
# 目的
pythonのturtleを使って、if文で条件によって動きが変わるプログラムを作る<br>
また、プログラムにコメントを書き、あとから読み返しやすいコードを書く習慣を身につける<br>

# 目次
<details><summary> 導入 </summary>

- [今日作るもの](#今日作るもの)
- [プログラム全体図](#プログラム全体図)

</details>

<details><summary> if文 </summary>

- [if文とは](#if文とは)
  - [日常の判断をプログラムにする](#日常の判断をプログラムにする)
  - [if文の書き方](#if文の書き方)
  - [if文で何ができるか](#if文で何ができるか)

</details>

- [条件式の復習](#条件式の復習)
  - [比較演算子](#比較演算子)
  - [= と == の違い](#-と--の違い)
  - [True と False](#True-と-False)
  - [Work1 条件式の結果を考えよう](#Work1-条件式の結果を考えよう)

</details>

<details><summary> コメントアウト </summary>

- [コメントアウト](#コメントアウト)
  - [コメントとは](#コメントとは)
  - [なぜコメントを書くのか](#なぜコメントを書くのか)
  - [コメントを書く場所](#コメントを書く場所)
  - [Work2 コメントを書いてみよう](#Work2-コメントを書いてみよう)

</details>

</details>

<details><summary> if文の練習 </summary>

<details><summary> STEP1 if文を書いてみよう </summary>

- [STEP1 if文を書いてみよう](#STEP1-if文を書いてみよう)
  - [①点数を判定する](#①点数を判定する)
  - [②条件を変えて実行する](#②条件を変えて実行する)
  - [Work3 合格判定を作ろう](#Work3-合格判定を作ろう)

</details>

<details><summary> STEP2 elseを使ってみよう </summary>

- [STEP2 elseを使ってみよう](#STEP2-elseを使ってみよう)
  - [①条件を満たさなかったときの処理](#①条件を満たさなかったときの処理)
  - [②信号の判定をする](#②信号の判定をする)
  - [Work4 赤信号なら止まるプログラム](#Work4-赤信号なら止まるプログラム)

</details>

<details><summary> STEP3 elifを使ってみよう </summary>

- [STEP3 elifを使ってみよう](#STEP3-elifを使ってみよう)
  - [①3つ以上の条件に分ける](#①3つ以上の条件に分ける)
  - [②条件の順番に注意する](#②条件の順番に注意する)
  - [Work5 信号の色を判定しよう](#Work5-信号の色を判定しよう)

</details>

<details><summary> STEP4 turtleでif文を使おう </summary>

- [STEP4 turtleでif文を使おう](#STEP4-turtleでif文を使おう)
  - [①条件によって線の色を変える](#①条件によって線の色を変える)
  - [②条件によって塗りつぶしの色を変える](#②条件によって塗りつぶしの色を変える)
  - [Work6 点数によって色が変わる線を描こう](#Work6-点数によって色が変わる線を描こう)

</details>

</details>

<details><summary> ミッション </summary>

- [Mission レッスンブック](#Mission-レッスンブック)

</details>

<details><summary> まとめ </summary>

- [まとめ](#まとめ)
- [補足](#補足)
- [参考文献](#参考文献)

</details>

# プログラム全体図
- ①if文の書き方を学ぶ<br>
- ②条件式の書き方を復習する<br>
- ③コメントアウトの使い方を学ぶ<br>
- ④簡単な点数判定プログラムを作る<br>
- ⑤レッスンブックに準拠

# if文とは
## 日常の判断をプログラムにする<br>
私たちは、毎日の生活の中で条件によって行動を変えています。<br>

例えば、以下のような判断です。<br>

```
もし雨が降っていたら、傘を持っていく
もし信号が赤なら、止まる
もし点数が70点以上なら、合格
```

このような「もし〜なら」をプログラムで書くために使うのが、**if文**です。<br>

if文を使うと、プログラムに**条件を判断させる**ことができます。<br>

## if文の書き方<br>
if文は、以下のように書きます。<br>

```python:python
if 条件式:
  条件を満たしたときの処理
```

大事なポイントは3つです。<br>

- `if` の後に条件式を書く<br>
- 条件式の後に `:` を書く<br>
- if文の中の処理は、字下げして書く<br>

例えば、点数が70点以上なら「合格」と表示するプログラムは以下です。<br>

```python:demo.py
# 点数を変数に入れる
score = 80

# scoreが70以上なら、合格と表示する
if score >= 70:
  print("合格")
```

## if文で何ができるか<br>
if文を使うと、条件によってプログラムの動きを変えられます。<br>

例えば、以下のようなことができます。<br>

- 点数によって合格・不合格を判定する<br>
- 信号の色によって行動を変える<br>
- キャラクターの位置によって色を変える<br>
- ゲームで当たり判定を作る<br>

つまりif文は、プログラムに**判断**をさせるための命令です。<br>

# 条件式の復習
## 比較演算子<br>
条件式では、2つの値を比べます。<br>
値を比べるために使う記号を、**比較演算子**といいます。<br>

| 書き方 | 意味 | 例 |
|---|---|---|
| `a == b` | a と b が等しい | `score == 100` |
| `a != b` | a と b が等しくない | `signal != "red"` |
| `a > b` | a が b より大きい | `score > 80` |
| `a < b` | a が b より小さい | `score < 80` |
| `a >= b` | a が b 以上 | `score >= 70` |
| `a <= b` | a が b 以下 | `score <= 30` |

## = と == の違い<br>
Pythonでは、`=` と `==` は意味が違います。<br>

```python:python
score = 80
```

これは、`score` に `80` を入れるという意味です。<br>
このように、変数に値を入れることを**代入**といいます。<br>

```python:python
score == 80
```

これは、`score` と `80` が等しいかを調べるという意味です。<br>

よくある間違いは以下です。<br>

```python:demo.py
score = 80

if score = 80:
  print("80点です")
```

このプログラムは、条件式の中で `=` を使っているので正しくありません。<br>
正しくは、以下のように `==` を使います。<br>

```python:demo.py
score = 80

if score == 80:
  print("80点です")
```

## True と False<br>
条件式の結果は、必ず **True** か **False** になります。<br>

- `True` は「条件を満たしている」という意味<br>
- `False` は「条件を満たしていない」という意味<br>

例えば、以下のプログラムを考えてみます。<br>

```python:demo.py
score = 80

if score >= 70:
  print("合格")
```

`score >= 70` は、`80 >= 70` なので True です。<br>
そのため、`print("合格")` が実行されます。<br>

## Work1 条件式の結果を考えよう<br>
以下の条件式は、True か False のどちらになるでしょうか。<br>

```python:demo.py
score = 65

score >= 70
score < 100
score == 65
score != 65
```

<details><summary>答え</summary>

```python:demo.py
score = 65

score >= 70   # False
score < 100   # True
score == 65   # True
score != 65   # False
```

`score` は65なので、70以上ではありません。<br>
そのため、`score >= 70` は False になります。<br>
</details>

# コメントアウト
## コメントとは<br>
Pythonでは、`#` の後に書いた文字はプログラムとして実行されません。<br>
これを**コメント**といいます。<br>

```python:demo.py
# これはコメントです
print("こんにちは")
```

上のプログラムでは、`# これはコメントです` の部分は実行されません。<br>

## なぜコメントを書くのか<br>
コメントを書く目的は、主に3つあります。<br>

- プログラムの目的を説明する<br>
- あとから読み返したときに、処理の意味を分かりやすくする<br>
- 一時的にプログラムを実行しないようにする<br>

例えば、以下の2つのプログラムを比べてみましょう。<br>

```python:demo.py
score = 80
if score >= 70:
  print("合格")
```

```python:demo.py
# 点数を変数に入れる
score = 80

# 点数が70点以上なら、合格と表示する
if score >= 70:
  print("合格")
```

下のプログラムの方が、何をしているのか分かりやすくなっています。<br>

## コメントを書く場所<br>
コメントは、処理のまとまりの前に書くと読みやすくなります。<br>

```python:demo.py
# 信号の色を決める
signal = "red"

# 赤信号なら止まると表示する
if signal == "red":
  print("止まる")
```

授業では、次の順番でプログラムを書きます。<br>

```
①まずコメントで、何をしたいかを書く
↓
②その下にプログラムを書く
↓
③実行して動きを確認する
↓
④必要ならコメントやコードを直す
```

この書き方を習慣にすると、複雑なプログラムでも考えやすくなります。<br>

## Work2 コメントを書いてみよう<br>
以下のプログラムに、何をしているか分かるコメントを追加してください。<br>

```python:demo.py
score = 90

if score >= 80:
  print("すばらしい")
```

<details><summary>答えの例</summary>

```python:demo.py
# 点数を変数に入れる
score = 90

# 点数が80点以上なら、すばらしいと表示する
if score >= 80:
  print("すばらしい")
```

コメントには完全に決まった正解はありません。<br>
ただし、コードを読んだ人が「何をしている処理なのか」を理解できる書き方にしましょう。<br>
</details>

# STEP1 if文を書いてみよう
ここでは、点数を判定する簡単なプログラムを書きます。<br>
最初はturtleを使わず、`print`で結果を確認します。<br>

## ①点数を判定する<br>
以下のプログラムを実行してください。<br>

```python:demo.py
# 点数を変数に入れる
score = 80

# scoreが70以上なら、合格と表示する
if score >= 70:
  print("合格")
```

`score` は80なので、`score >= 70` は True になります。<br>
そのため、`合格` と表示されます。<br>

## ②条件を変えて実行する<br>
次に、`score` の値を50に変えて実行してください。<br>

```python:demo.py
# 点数を変数に入れる
score = 50

# scoreが70以上なら、合格と表示する
if score >= 70:
  print("合格")
```

この場合、`score >= 70` は False です。<br>
そのため、if文の中の `print("合格")` は実行されません。<br>

## Work3 合格判定を作ろう<br>
以下の条件を満たすプログラムを作ってください。<br>

- `score` という変数を作る<br>
- `score` が60以上なら、`"クリア"` と表示する<br>
- プログラムにはコメントを書く<br>

<details><summary>答え</summary>

```python:demo.py
# 点数を変数に入れる
score = 75

# scoreが60以上なら、クリアと表示する
if score >= 60:
  print("クリア")
```

`score` の値を30や100に変えて、表示がどう変わるか確認してみましょう。<br>
</details>

# STEP2 elseを使ってみよう
## ①条件を満たさなかったときの処理<br>
if文だけでは、条件を満たしたときの処理しか書けません。<br>
条件を満たさなかったときの処理を書くには、**else** を使います。<br>

```python:python
if 条件式:
  条件を満たしたときの処理
else:
  条件を満たさなかったときの処理
```

例えば、合格・不合格を判定するプログラムは以下です。<br>

```python:demo.py
# 点数を変数に入れる
score = 50

# scoreが70以上なら合格、そうでなければ不合格と表示する
if score >= 70:
  print("合格")
else:
  print("不合格")
```

## ②信号の判定をする<br>
次に、信号の色を判定します。<br>

```python:demo.py
# 信号の色を変数に入れる
signal = "red"

# 赤信号なら止まる、そうでなければ進む
if signal == "red":
  print("止まる")
else:
  print("進む")
```

このプログラムでは、`signal` が `"red"` のときだけ `"止まる"` と表示されます。<br>
それ以外のときは、`"進む"` と表示されます。<br>

## Work4 赤信号なら止まるプログラム<br>
以下の条件を満たすプログラムを作ってください。<br>

- `signal` という変数を作る<br>
- `signal` が `"red"` なら `"止まる"` と表示する<br>
- そうでなければ `"止まらない"` と表示する<br>
- プログラムにはコメントを書く<br>

<details><summary>答え</summary>

```python:demo.py
# 信号の色を変数に入れる
signal = "blue"

# 赤信号なら止まる、そうでなければ止まらないと表示する
if signal == "red":
  print("止まる")
else:
  print("止まらない")
```

`signal` を `"red"` や `"yellow"` に変えて、表示がどう変わるか確認しましょう。<br>
</details>

# STEP3 elifを使ってみよう
## ①3つ以上の条件に分ける<br>
信号には、赤・黄・青の3つがあります。<br>
このように3つ以上の条件に分けたいときは、**elif** を使います。<br>

```python:python
if 条件式1:
  条件式1を満たしたときの処理
elif 条件式2:
  条件式2を満たしたときの処理
else:
  どの条件も満たさなかったときの処理
```

信号の色で表示を変えるプログラムは、以下です。<br>

```python:demo.py
# 信号の色を変数に入れる
signal = "yellow"

# 信号の色によって、表示する言葉を変える
if signal == "red":
  print("止まる")
elif signal == "yellow":
  print("注意する")
else:
  print("進む")
```

## ②条件の順番に注意する<br>
`elif` を使うときは、条件の順番が大切です。<br>
上から順番に条件を調べ、最初にTrueになったところだけが実行されます。<br>

例えば、点数を判定するプログラムを考えます。<br>

```python:demo.py
# 点数を変数に入れる
score = 90

# 点数によって評価を変える
if score >= 80:
  print("すばらしい")
elif score >= 60:
  print("合格")
else:
  print("もう一度チャレンジ")
```

この順番なら、90点は `"すばらしい"` と判定されます。<br>

しかし、以下のように順番を逆にすると、結果が変わります。<br>

```python:demo.py
# 点数を変数に入れる
score = 90

# この順番だと、90点でも先にscore >= 60に当てはまる
if score >= 60:
  print("合格")
elif score >= 80:
  print("すばらしい")
else:
  print("もう一度チャレンジ")
```

90点は60点以上でもあるため、最初の条件で `"合格"` と表示されます。<br>
このように、条件の順番によって結果が変わることがあります。<br>

## Work5 信号の色を判定しよう<br>
以下の条件を満たすプログラムを作ってください。<br>

- `signal` が `"red"` なら `"止まる"` と表示する<br>
- `signal` が `"yellow"` なら `"注意する"` と表示する<br>
- それ以外なら `"進む"` と表示する<br>
- プログラムにはコメントを書く<br>

<details><summary>答え</summary>

```python:demo.py
# 信号の色を変数に入れる
signal = "red"

# 信号の色によって、表示する言葉を変える
if signal == "red":
  print("止まる")
elif signal == "yellow":
  print("注意する")
else:
  print("進む")
```

`signal` を `"red"`、`"yellow"`、`"blue"` に変えて、表示を確認しましょう。<br>
</details>

# STEP4 turtleでif文を使おう
ここからは、if文とturtleを組み合わせます。<br>
条件によって色が変わるプログラムを作ります。<br>

## ①条件によって線の色を変える<br>
以下のプログラムを実行してください。<br>

```python:demo.py
# 点数を変数に入れる
score = 85

# 点数が80点以上なら線の色を赤にする
if score >= 80:
  pencolor("red")

# 線を引く
forward(120)
```

このプログラムでは、`score` が80以上なので、赤い線が描かれます。<br>

## ②条件によって塗りつぶしの色を変える<br>
次は、条件によって四角形の色を変えます。<br>

```python:demo.py
# 点数を変数に入れる
score = 65

# 点数が70点以上なら青、そうでなければ赤にする
if score >= 70:
  color("blue")
else:
  color("red")

# 四角形を描いて塗りつぶす
beginfill()
for i in range(4):
  forward(100)
  right(90)
endfill()
```

`score` の値を変えると、四角形の色が変わります。<br>

## Work6 点数によって色が変わる線を描こう<br>
以下の条件を満たすプログラムを作ってください。<br>

- `score` が80以上なら、線の色を `"gold"` にする<br>
- `score` が60以上なら、線の色を `"blue"` にする<br>
- それ以外なら、線の色を `"red"` にする<br>
- 最後に `forward(150)` で線を描く<br>
- プログラムにはコメントを書く<br>

<details><summary>答え</summary>

```python:demo.py
# 点数を変数に入れる
score = 75

# 点数によって線の色を変える
if score >= 80:
  pencolor("gold")
elif score >= 60:
  pencolor("blue")
else:
  pencolor("red")

# 線を描く
forward(150)
```

`score` を90、70、40などに変えて、線の色がどう変わるか確認しましょう。<br>
</details>

# Mission レッスンブック

# 参考文献
[1] https://www.python.org/<br>
[2] https://docs.python.org/ja/3/tutorial/controlflow.html<br>
[3] https://docs.python.org/ja/3/library/turtle.html<br>
[4] Eric Matthes. "Python Crash Course, 3rd Edition: A Hands-On, Project-Based Introduction to Programming". No Starch Press Inc.<br>

**Acknowledgement**  
This material was reviewed and refined with the assistance of ChatGPT (OpenAI).

Kazuma Aoyama(kazuma-a@akamafu.com)