# INNOVATOR Month4 Week2
# 秘密の数字を当てろ！暗号解除ゲーム

# 目的
`input`で入力した数字を、`int`を使って計算や比較ができる形に変える<br>
`while`と`if / elif / else`を組み合わせ、正解するまで続くゲームを作る<br>
変数を使って挑戦回数を数える<br>

# 内容目標
- `input()`で入力した値は文字列になることを知る<br>
- `int()`で文字列を整数に変換できる<br>
- `while`を使って、条件を満たすまで処理をくり返せる<br>
- 条件式を使って、正解より大きい・小さい・同じを判定できる<br>

# 目次
- [今日作るもの](#今日作るもの)
- [プログラム全体図](#プログラム全体図)
- [前回の復習](#前回の復習)
- [数字を入力しよう](#数字を入力しよう)
- [randomの復習](#randomの復習)

<details><summary>暗号解除ゲームを作ろう</summary>

- [STEP1 秘密の数字を作ろう](#step1-秘密の数字を作ろう)
- [STEP2 入力した数字を判定しよう](#step2-入力した数字を判定しよう)
- [STEP3 正解するまでくり返そう](#step3-正解するまでくり返そう)
- [STEP4 挑戦回数を数えよう](#step4-挑戦回数を数えよう)
- [Mission 暗号解除ゲームを完成させよう](#mission-暗号解除ゲームを完成させよう)

</details>

<details><summary>発展課題</summary>

- [Ex1 数字の範囲を広げよう](#ex1-数字の範囲を広げよう)
- [Ex2 回数によってランクを変えよう](#ex2-回数によってランクを変えよう)
- [Ex3 5回以内に暗号を解除しよう](#ex3-5回以内に暗号を解除しよう)
- [Ex4 難易度を選べるようにしよう](#ex4-難易度を選べるようにしよう)

</details>

- [まとめ](#まとめ)
- [参考文献](#参考文献)

# 今日作るもの
今日作る作品は、**暗号解除ゲーム**です。<br>

コンピューターが1から20までの中から、秘密の数字を1つ決めます。<br>
プレイヤーは、ヒントを頼りに秘密の数字を当てます。<br>

```text
秘密の数字を入力してください: 10
もっと大きい数字です

秘密の数字を入力してください: 16
もっと小さい数字です

秘密の数字を入力してください: 13
暗号解除成功！
3回で解除できました
```

実行するたびに秘密の数字が変わるため、何度でも遊べます。<br>

# プログラム全体図
```text
① 1から20までの秘密の数字を作る
              ↓
② プレイヤーが数字を入力する
              ↓
③ 秘密の数字と入力した数字を比べる
              ↓
④ 大きい・小さいのヒントを表示する
              ↓
⑤ 正解でなければ、もう一度入力する
              ↓
⑥ 正解したら、挑戦回数を表示する
```

今回のゲームでは、これまでに学んだ次の命令を組み合わせます。<br>

- 変数
- `input`
- `while`
- `if / elif / else`
- `random`
- 条件式

# 前回の復習
Month4 Week1では、`input()`を使ってturtleをラジコンのように動かしました。<br>

```python:demo.py
command = input("コマンドを入力してください: ")

if command == "前":
  forward(100)
elif command == "右":
  right(90)
elif command == "左":
  left(90)
```

`input()`を使うと、キーボードで入力した内容を変数に入れられます。<br>
前回は、「前」「右」「左」のような**文字**を入力しました。<br>

今回は、数字を入力してゲームを作ります。<br>

# 数字を入力しよう
## inputで入力したものは文字になる<br>
次のプログラムを実行してください。<br>

```python:demo.py
num = input("好きな数字を入力してください: ")
print(num)
```

数字を入力しても、`input()`で受け取ったものは**文字列**になります。<br>
文字列とは、文字を並べたデータのことです。Pythonでは`str`とも呼びます。<br>

例えば、キーボードで`10`と入力した場合でも、Pythonは文字の`"10"`として受け取ります。<br>

```text
キーボードで 10 と入力
        ↓
inputが受け取るものは "10"
```

## intで整数に変えよう
入力した数字を計算や大小の比較に使うときは、`int()`を使います。<br>

```python:demo.py
num = int(input("好きな数字を入力してください: "))
print(num)
```

`int()`は、数字の形をした文字列を**整数**に変える命令です。<br>

```text
"10"  -- int() -->  10
文字列               整数
```

今回は、次の形をよく使います。<br>

```python:python
変数 = int(input("案内文"))
```

> 注意：このレッスンでは、入力するときに半角の数字を使ってください。数字以外の文字を入力するとエラーになります。

## Work1 入力した数字に10を足そう
入力した数字に10を足して表示するプログラムを作ってください。<br>

<details><summary>答え</summary>

```python:demo.py
num = int(input("数字を入力してください: "))
print(num + 10)
```

</details>

# randomの復習
`random`モジュールを使うと、ランダムな数字を作れます。<br>

```python:demo.py
import random

num = random.randint(1, 20)
print(num)
```

`random.randint(1, 20)`は、1から20までの整数をランダムに1つ作ります。<br>
1と20も出る可能性があります。<br>

何度か実行し、数字が変わることを確認してください。<br>

## Work2 サイコロを作ろう
1から6までの数字がランダムに出るプログラムを作ってください。<br>

<details><summary>答え</summary>

```python:demo.py
import random

dice = random.randint(1, 6)
print(dice)
```

</details>

# STEP1 秘密の数字を作ろう
まずは、コンピューターに秘密の数字を決めてもらいます。<br>

```python:main.py
# randomモジュールを使えるようにする
import random

# 1から20までの秘密の数字を作る
secret = random.randint(1, 20)

# 動作確認のため、秘密の数字を表示する
print(secret)
```

秘密の数字は、変数`secret`に入っています。<br>
今は動作を確認するために`print(secret)`を書いていますが、ゲームを完成させるときには消します。<br>

秘密の数字が見えていると、暗号解除ゲームにならないためです。<br>

# STEP2 入力した数字を判定しよう
次に、プレイヤーが予想した数字を入力できるようにします。<br>

```python:main.py
# randomモジュールを使えるようにする
import random

# 1から20までの秘密の数字を作る
secret = random.randint(1, 20)

# 予想した数字を入力する
guess = int(input("秘密の数字を入力してください: "))
```

秘密の数字と予想した数字を、`if / elif / else`で比べます。<br>

```python:main.py
# 秘密の数字と予想した数字を比べる
if guess == secret:
  print("暗号解除成功！")
elif guess < secret:
  print("もっと大きい数字です")
else:
  print("もっと小さい数字です")
```

上から順番に条件を確認します。<br>

```text
guessとsecretが同じ？
    ↓ 違う
guessはsecretより小さい？
    ↓ 違う
guessはsecretより大きい
```

## Work3 条件式を確認しよう
秘密の数字が`13`だった場合、次の入力では何が表示されるか考えてください。<br>

| 入力した数字 | 表示されるヒント |
|---:|---|
| 7 | ？ |
| 13 | ？ |
| 18 | ？ |

<details><summary>答え</summary>

| 入力した数字 | 表示されるヒント |
|---:|---|
| 7 | もっと大きい数字です |
| 13 | 暗号解除成功！ |
| 18 | もっと小さい数字です |

</details>

# STEP3 正解するまでくり返そう
今のプログラムでは、数字を1回しか入力できません。<br>
正解するまで何度も入力できるように、`while`を使います。<br>

## whileの復習
`while`は、条件式が`True`の間、処理をくり返します。<br>

```python:python
while 条件式:
  くり返す処理
```

暗号解除ゲームでは、次の条件を使います。<br>

```python:python
while guess != secret:
```

`!=`は「同じではない」という意味です。<br>
つまり、予想した数字と秘密の数字が同じではない間、入力をくり返します。<br>

最初はまだ予想していないため、`guess`に0を入れておきます。<br>
秘密の数字は1から20なので、最初から正解になることはありません。<br>

```python:main.py
# randomモジュールを使えるようにする
import random

# 1から20までの秘密の数字を作る
secret = random.randint(1, 20)

# 最初の予想を0にする
guess = 0

# 正解するまで入力をくり返す
while guess != secret:
  guess = int(input("秘密の数字を入力してください: "))

  # 秘密の数字と予想した数字を比べる
  if guess == secret:
    print("暗号解除成功！")
  elif guess < secret:
    print("もっと大きい数字です")
  else:
    print("もっと小さい数字です")
```

正解すると`guess != secret`が`False`になるため、whileのくり返しが終わります。<br>

# STEP4 挑戦回数を数えよう
変数を使って、暗号解除までに入力した回数を数えます。<br>

まず、くり返しの前に`count`を0にします。<br>

```python:python
count = 0
```

数字を1回入力するたびに、`count`を1増やします。<br>

```python:python
count = count + 1
```

`count = count + 1`は、今の`count`に1を足したものを、もう一度`count`に入れるという意味です。<br>

```text
最初のcountは0
      ↓ 1回入力
countは1
      ↓ もう1回入力
countは2
```

whileのくり返しが終わった後に、挑戦回数を表示します。<br>

```python:python
print(str(count) + "回で解除できました")
```

`str()`は、整数を文字列に変える命令です。<br>
文字と数字を`+`でつなげるために使います。<br>

# Mission 暗号解除ゲームを完成させよう
## ミッション内容
ヒントを使って、秘密の数字を当てるゲームを完成させましょう。<br>

## 完成条件
- `random.randint(1, 20)`で秘密の数字を作る<br>
- `int(input())`で数字を入力する<br>
- `while`を使い、正解するまで入力をくり返す<br>
- `if / elif / else`でヒントを表示する<br>
- 変数`count`で挑戦回数を数える<br>
- 処理の説明になるコメントを5つ以上書く<br>

## 完成例
```python:main.py
# randomモジュールを使えるようにする
import random

# ゲームの説明を表示する
print("=== 秘密の暗号を解除せよ！ ===")
print("秘密の数字は1から20までです")

# 1から20までの秘密の数字を作る
secret = random.randint(1, 20)

# 最初の予想と挑戦回数を決める
guess = 0
count = 0

# 正解するまで入力をくり返す
while guess != secret:
  # 予想した数字を入力する
  guess = int(input("秘密の数字を入力してください: "))

  # 挑戦回数を1増やす
  count = count + 1

  # 秘密の数字と予想した数字を比べる
  if guess == secret:
    print("暗号解除成功！")
  elif guess < secret:
    print("もっと大きい数字です")
  else:
    print("もっと小さい数字です")

# 暗号解除までにかかった回数を表示する
print(str(count) + "回で解除できました")
```

# Ex1 数字の範囲を広げよう
秘密の数字の範囲を、1から100までに変更してください。<br>
ゲームの説明も忘れずに変更しましょう。<br>

<details><summary>ヒント</summary>

```python:python
secret = random.randint(1, 100)
```

</details>

# Ex2 回数によってランクを変えよう
暗号解除までの挑戦回数によって、最後に表示するランクを変えてください。<br>

```text
3回以内 → Sランク
5回以内 → Aランク
それ以外 → Bランク
```

<details><summary>答えの例</summary>

```python:python
if count <= 3:
  print("Sランク！天才ハッカーです！")
elif count <= 5:
  print("Aランク！すばやい暗号解除です！")
else:
  print("Bランク！最後まであきらめませんでした！")
```

</details>

# Ex3 5回以内に暗号を解除しよう
入力できる回数を5回までにします。<br>
正解するか、5回入力したらwhileを終了します。<br>

条件を2つ同時に満たしているか調べるときは、`and`を使います。<br>

<details><summary>答えの枠組み</summary>

```python:main.py
import random

secret = random.randint(1, 20)
guess = 0
count = 0

# 不正解で、挑戦回数が5回より少ない間くり返す
while guess != secret and count < 5:
  guess = int(input("秘密の数字を入力してください: "))
  count = count + 1

  if guess == secret:
    print("暗号解除成功！")
  elif guess < secret:
    print("もっと大きい数字です")
  else:
    print("もっと小さい数字です")

# whileが終わった理由を判定する
if guess == secret:
  print(str(count) + "回で解除できました")
else:
  print("時間切れ！暗号は" + str(secret) + "でした")
```

</details>

# Ex4 難易度を選べるようにしよう
ゲームの最初に難易度を入力し、秘密の数字の範囲を変えてください。<br>

```text
かんたん → 1から10
ふつう   → 1から50
むずかしい → 1から100
```

<details><summary>答えの枠組み</summary>

```python:python
difficulty = input("難易度を選んでください（かんたん・ふつう・むずかしい）: ")

if difficulty == "かんたん":
  max_num = 10
elif difficulty == "ふつう":
  max_num = 50
else:
  max_num = 100

secret = random.randint(1, max_num)
print("秘密の数字は1から" + str(max_num) + "までです")
```

</details>

# まとめ
今日は、これまでに学んだ命令を組み合わせて暗号解除ゲームを作りました。<br>

今回の大事なポイントは次のとおりです。<br>

- `input()`で入力したものは文字列になる<br>
- `int()`を使うと、数字の形をした文字列を整数に変えられる<br>
- `random.randint()`で秘密の数字をランダムに作れる<br>
- `if / elif / else`で、大きい・小さい・同じを判定できる<br>
- `while`を使うと、正解するまで入力をくり返せる
- 変数の値を1ずつ増やすと、回数を数えられる

次回は、変数・input・while・if・randomを使って、モンスターと戦うゲームを作ります。<br>

# 参考文献
[1] https://www.python.org/<br>
[2] https://docs.python.org/ja/3/library/functions.html#input<br>
[3] https://docs.python.org/ja/3/library/functions.html#int<br>
[4] https://docs.python.org/ja/3/reference/compound_stmts.html#while<br>
[5] https://docs.python.org/ja/3/library/random.html<br>

**Acknowledgement**  
This material was reviewed and refined with the assistance of ChatGPT (OpenAI).

