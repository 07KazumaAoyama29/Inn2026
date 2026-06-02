# INNOVATOR Month3 Week1
# if文を知ろう
# 目的
if文で条件によって動きが変わるプログラムを作る<br>
また、プログラムにコメントを書き、あとから読み返しやすいコードを書く習慣を身につける<br>

# 目次
- [if文とは](#if文とは)
- [条件式の復習](#条件式の復習)
- [コメントアウト](#コメントアウト)

<details><summary> if文の練習 </summary>

- [STEP1 if文を書いてみよう](#STEP1-if文を書いてみよう)
- [STEP2 elseを使ってみよう](#STEP2-elseを使ってみよう)
- [STEP3 turtleでif文を使おう](#STEP4-turtleでif文を使おう)
</details>

- [Mission レッスンブック](#Mission-レッスンブック)
- [まとめ](#まとめ)
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
- if文の中の処理は、インデントを開ける<br>

例えば、点数が70点以上なら「合格」と表示するプログラムは以下です。<br>

```python:demo.py
# 点数を変数に入れる
score = 80

# scoreが70以上なら、合格と表示する
if score >= 70:
  print("合格")
```

## Work1 レッスンブックのワーク１を取り組もう<br>
ただし、60点以上なら合格と出力するようなプログラムにすること。

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

## Work2 条件式の結果を考えよう<br>
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

## Work3 レッスンブックのワーク１のプログラムにコメントを書こう<br>

<details><summary>答えの例</summary>

```python:demo.py
# 数字を変数に入れる
num = 80

# 点数が60点以上なら、すばらしいと表示する
if score >= 60:
  print("合格")
```

コメントには完全に決まった正解はありません。<br>
ただし、コードを読んだ人が「何をしている処理なのか」を理解できる書き方にしましょう。<br>
</details>

# STEP1 if文を書いてみよう
ここでは、点数を判定する簡単なプログラムを書きます。<br>
最初はturtleを使わず、`print`で結果を確認します。<br>
レッスンブックのワーク１のプログラムをアップデートしていきます。

## 条件を変えて実行する<br>
次に、`num` の値を50に変えて実行してください。<br>

```python:demo.py
# 点数を変数に入れる
score = 50

# scoreが60以上なら、合格と表示する
if score >= 60:
  print("合格")
```

この場合、`num >= 60` は False です。<br>
そのため、if文の中の `print("合格")` は実行されません。<br>

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

# STEP3 turtleでif文を使おう
ここからは、if文とturtleを組み合わせます。<br>
条件によって色が変わるプログラムを作ります。<br>
レッスンブックのワーク２に取り組みましょう。

# Ex. レッスンブック
時間があれば、レッスンブックのミッションに取り組みましょう。

# 参考文献
[1] https://www.python.org/<br>
[2] https://docs.python.org/ja/3/tutorial/controlflow.html<br>
[3] https://docs.python.org/ja/3/library/turtle.html<br>
[4] Eric Matthes. "Python Crash Course, 3rd Edition: A Hands-On, Project-Based Introduction to Programming". No Starch Press Inc.<br>

**Acknowledgement**  
This material was reviewed and refined with the assistance of ChatGPT (OpenAI).

Kazuma Aoyama(kazuma-a@akamafu.com)