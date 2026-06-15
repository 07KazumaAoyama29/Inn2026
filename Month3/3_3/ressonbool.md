# INNOVATOR Month3 Week3
# randomとelifでモンスターガチャを作ろう

# 目的
randomモジュールを使って、ランダムな数字を作る<br>
if / elif / else を使って、数字に応じて1つだけ結果を選ぶプログラムを作る<br>
turtleを使って、出てきたモンスターに応じた図形を描く<br>
コメントを書きながら、処理の意味を整理する習慣を身につける<br>

# 目次
- [前回の復習](#前回の復習)
- [elifを使う理由](#elifを使う理由)
- [randomモジュールについて](#randomモジュールについて)
- [randomでガチャを作ろう](#randomでガチャを作ろう)

<details><summary> モンスターガチャ作成 </summary>

- [STEP1 randomでパワーを決めよう](#STEP1-randomでパワーを決めよう)
- [STEP2 ifだけで書くとどうなるか確認しよう](#STEP2-ifだけで書くとどうなるか確認しよう)
- [STEP3 elifでモンスターを1つだけ選ぼう](#STEP3-elifでモンスターを1つだけ選ぼう)
- [STEP4 turtleで図形を描こう](#STEP4-turtleで図形を描こう)

</details>

- [Mission モンスターガチャを完成させよう](#Mission-モンスターガチャを完成させよう)
- [Ex 発展課題](#Ex-発展課題)
- [まとめ](#まとめ)
- [参考文献](#参考文献)

</details>

# 今日やること
今日は、**モンスターガチャ**を作ります。<br>

プログラムを実行すると、0〜100のランダムな数字が作られます。<br>
その数字によって、出てくるモンスターと描く図形が変わります。<br>

```
100点      → 伝説のドラゴン
80点以上   → つよつよドラゴン
50点以上   → ロボモンスター
30点以上   → ぷにぷにスライム
それ以外   → よわよわ豆モンスター
```

# 前回の復習

## if文とは<br>
if文は、条件を満たしたとき(True)だけ処理を実行するプログラムです。<br>

```python:demo.py
# 天気を変数に入れる
tenki = "雨"

# tenkiが雨なら、傘が必要と表示する
if tenki == "雨":
  print("傘が必要です。")
```

このプログラムでは、`tenki == "雨"` が `True` なので、`print("傘が必要です。")` が実行されます。<br>

## elseとは<br>
`else` は、条件を満たさなかったときの処理を書くために使います。<br>

```python:demo.py
# 天気を変数に入れる
tenki = "晴れ"

# 雨なら傘が必要、そうでなければ傘は不要と表示する
if tenki == "雨":
  print("傘が必要です。")
else:
  print("傘は不要です。")
```

## elifとは<br>
`elif` は、条件を増やしたいときに使います。<br>

```python:python
if 条件式1:
  条件式1を満たしたときの処理
elif 条件式2:
  条件式2を満たしたときの処理
else:
  どの条件も満たさなかったときの処理
```

`elif` は、**そうでなければ、次の条件を調べる**という意味です。<br>

# elifを使う理由

## ifを連続で書くとどうなるか<br>
次のプログラムを見てください。<br>

```python:demo.py
# パワーを決める
power = 100

# ifを連続で書く
if power >= 100:
  print("伝説のドラゴン")

if power >= 80:
  print("つよつよドラゴン")

if power >= 50:
  print("ロボモンスター")

if power >= 30:
  print("ぷにぷにスライム")

else:
  print("よわよわ豆モンスター")
```

このプログラムでは、`power` が100です。<br>
100は、以下の条件をすべて満たします。<br>

```
power >= 100
power >= 80
power >= 50
power >= 30
```

そのため、ifを連続で書くと、複数のモンスターが出てしまいます。<br>

## モンスターは1つだけ出したい<br>
ガチャでは、出てくるモンスターは1つだけにしたいです。<br>
そのため、`if`を連続で書くのではなく、`elif`を使います。<br>

```python:demo.py
# パワーを決める
power = 100

# elifを使って、モンスターを1つだけ選ぶ
if power >= 100:
  print("伝説のドラゴン")
elif power >= 80:
  print("つよつよドラゴン")
elif power >= 50:
  print("ロボモンスター")
elif power >= 30:
  print("ぷにぷにスライム")
else:
  print("よわよわ豆モンスター")
```

このプログラムでは、上から順番に条件を調べます。<br>
最初に当てはまったところだけが実行されます。<br>

そのため、`power` が100のときは、`伝説のドラゴン` だけが表示されます。<br>

# randomモジュールについて

## randomモジュールとは<br>
Pythonには、便利な機能をまとめた **モジュール** というものがあります。<br>
randomモジュールを使うと、ランダムな数字を作ることができます。<br>

randomモジュールを使うには、プログラムの最初に以下を書きます。<br>

```python:demo.py
import random
```

## random.randint<br>
ランダムな整数を作るには、`random.randint()` を使います。<br>

```python:demo.py
# 0から100までの整数をランダムに1つ作る
power = random.randint(0, 100)

# 作った数字を表示する
print(power)
```

`random.randint(0, 100)` は、0から100までの整数の中から、ランダムに1つ選びます。<br>
100も出ますが、かなり低い確率です。<br>
つまり、100が出たらレアです。<br>

# randomでガチャを作ろう

## STEP1 randomでパワーを決めよう
まずは、ガチャでパワーを決めるプログラムを作ります。<br>

```python:demo.py
# randomモジュールを使えるようにする
import random

# 0から100までの整数をランダムに1つ作る
power = random.randint(0, 100)

# 作った数字を表示する
print(power)
```

このプログラムを何回か実行してください。<br>
実行するたびに、違う数字が出ることがあります。<br>

# STEP2 ifだけで書くとどうなるか確認しよう
次に、ガチャの結果によって表示を変えてみます。<br>
まずは、わざと `if` だけで書いてみます。<br>

```python:demo.py
# randomモジュールを使えるようにする
import random

# 0から100までの整数をランダムに1つ作る
power = random.randint(0, 100)

# ifだけでモンスターを判定する
if power >= 100:
  print("伝説のドラゴン")

if power >= 80:
  print("つよつよドラゴン")

if power >= 50:
  print("ロボモンスター")

if power >= 30:
  print("ぷにぷにスライム")

else:
  print("よわよわ豆モンスター")
```

このプログラムは、今回作りたいガチャとしては適切ではありません。<br>
なぜなら、`power` が大きいと複数のモンスターが表示されるからです。<br>

# STEP3 elifでモンスターを1つだけ選ぼう
次に、`elif` を使って書き直します。<br>

```python:demo.py
# randomモジュールを使えるようにする
import random

# 0から100までの整数をランダムに1つ作る
power = random.randint(0, 100)

# elifを使って、モンスターを1つだけ選ぶ
if power >= 100:
  print("伝説のドラゴン")
elif power >= 80:
  print("つよつよドラゴン")
elif power >= 50:
  print("ロボモンスター")
elif power >= 30:
  print("ぷにぷにスライム")
else:
  print("よわよわ豆モンスター")
```

`elif` を使うと、上から順番に条件を調べ、最初に当てはまったところだけが実行されます。<br>
そのため、`power` が100のときは `伝説のドラゴン` だけが表示されます。<br>

# STEP4 turtleで図形を描こう
ここからは、モンスターに合わせて turtle で図形を描きます。<br>

まずは、四角形を描くプログラムを確認します。<br>

```python:demo.py

# 四角形を描く
for i in range(4):
  fd(100)
  lt(90)
```

次に、五角形を描いてみます。<br>

```python:demo.py
# turtleを使えるようにする
from turtle import *

# 五角形を描く
for i in range(5):
  fd(100)
  lt(72)

done()
```

正多角形では、1回曲がる角度を以下のように決めます。<br>

```
360 ÷ 角の数
```

| 図形 | くり返し回数 | 曲がる角度 |
|---|---:|---:|
| 四角形 | 4 | 90 |
| 五角形 | 5 | 72 |
| 六角形 | 6 | 60 |
| 十二角形 | 12 | 30 |
| 三十六角形 | 36 | 10 |

# Mission モンスターガチャを完成させよう

## ミッション内容
randomで作ったパワーによって、出てくるモンスターと描く図形が変わるプログラムを作りましょう。<br>

### 条件
- `import random` を使う<br>
- `random.randint(0, 100)` を使う<br>
- `if / elif / else` を使う<br>
- turtleで図形を描く<br>
- コメントを5つ以上書く<br>

## 完成例
以下のプログラムを作って実行してください。<br>

```python:main.py
# turtleを使えるようにする
from turtle import *

# randomモジュールを使えるようにする
import random

# 描く速さを決める
speed(0)

# ガチャで0から100までのパワーを決める
power = random.randint(0, 100)

# パワーを表示する
print(power)

# パワーによって、出てくるモンスターを1つだけ決める
if power >= 100:
  print("伝説のドラゴン")
  color("red")

  # 四角形を描く
  for i in range(4):
    fd(100)
    lt(90)

elif power >= 80:
  print("つよつよドラゴン")
  color("orange")

  # 五角形を描く
  for i in range(5):
    fd(100)
    lt(72)

elif power >= 50:
  print("ロボモンスター")
  color("blue")

  # 六角形を描く
  for i in range(6):
    fd(100)
    lt(60)

elif power >= 30:
  print("ぷにぷにスライム")
  color("green")

  # 十二角形を描く
  for i in range(12):
    fd(50)
    lt(30)

else:
  print("よわよわ豆モンスター")
  color("gray")

  # 三十六角形を描く
  for i in range(36):
    fd(25)
    lt(10)

done()
```

実行するたびに、出てくる数字が変わります。<br>
数字が変わると、表示されるモンスターや描かれる図形も変わります。<br>

# Ex 発展課題

## Ex1 モンスターの名前を変えよう
モンスターの名前を、自分で考えた名前に変えてください。<br>

例：<br>

```
伝説のドラゴン → アルティメットもちドラゴン
つよつよドラゴン → からあげドラゴン
ロボモンスター → 宿題ロボ
ぷにぷにスライム → ぷにぷにプリン
よわよわ豆モンスター → 豆つぶくん
```

## Ex2 色を変えよう
`color()` の中身を変えて、図形の色を変えてください。<br>

```python:demo.py
color("purple")
```

## Ex3 図形を変えよう
モンスターごとに描く図形を変えてください。<br>

例：三角形を描く場合<br>

```python:demo.py
for i in range(3):
  fd(100)
  lt(120)
```

## Ex4 モンスターを1種類追加しよう
新しいモンスターを1種類追加してください。<br>

例：<br>

```python:demo.py
elif power >= 95:
  print("超レアもちドラゴン")
  color("purple")

  for i in range(3):
    fd(120)
    lt(120)
```

ただし、条件の順番に注意しましょう。<br>
大きい数字の条件を先に書かないと、思った通りに分かれないことがあります。<br>

# まとめ
今回は、randomモジュールとelifを使って、モンスターガチャを作りました。<br>

今日の大事なポイントは以下です。<br>

- `random.randint(0, 100)` でランダムな数字を作れる<br>
- `if` を連続で書くと、複数の条件が実行されることがある<br>
- `elif` を使うと、上から順番に調べて、最初に当てはまった1つだけを実行できる<br>
- turtleと組み合わせると、条件によって描く図形を変えられる<br>
- コメントを書くと、処理の意味を整理しやすくなる<br>

これで、if文のレッスンは一区切りです。<br>
条件によって動きが変わるプログラムは、ゲームや診断、チャットボットなど、いろいろな作品に使えます。<br>

# 参考文献
[1] https://www.python.org/<br>
[2] https://docs.python.org/ja/3/tutorial/controlflow.html<br>
[3] https://docs.python.org/ja/3/library/random.html<br>
[4] https://docs.python.org/ja/3/library/turtle.html<br>
[5] Eric Matthes. "Python Crash Course, 3rd Edition: A Hands-On, Project-Based Introduction to Programming". No Starch Press Inc.<br>

**Acknowledgement**  
This material was reviewed and refined with the assistance of ChatGPT (OpenAI).

Kazuma Aoyama(kazuma-a@akamafu.com)
