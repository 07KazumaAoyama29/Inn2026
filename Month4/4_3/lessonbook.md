# INNOVATOR Month4 Week3
# コマンドを選んでモンスターを倒そう！

# 目的
変数・`input`・`while`・`if / elif / else`・`random`を組み合わせて、モンスターバトルゲームを作る<br>
ゲームの流れを小さな処理に分け、コメントを書きながら順番にプログラムを組み立てる<br>
これまでに学んだPythonの基礎を使って、自分だけのゲームに改造する<br>

# 内容目標
- HPを変数で管理し、攻撃を受けた分だけ値を減らせる<br>
- 入力されたコマンドによって処理を変えられる<br>
- `random`を使って、毎回違うダメージを作れる<br>
- `while`を使って、決着がつくまでバトルをくり返せる<br>
- 複数の条件を`and`でつなげられる<br>

# 目次
- [今日作るもの](#今日作るもの)
- [プログラム全体図](#プログラム全体図)
- [前回の復習](#前回の復習)
- [バトルに必要な変数](#バトルに必要な変数)

<details><summary>モンスターバトルを作ろう</summary>

- [STEP1 攻撃でHPを減らそう](#step1-攻撃でhpを減らそう)
- [STEP2 ダメージをランダムにしよう](#step2-ダメージをランダムにしよう)
- [STEP3 コマンドを選べるようにしよう](#step3-コマンドを選べるようにしよう)
- [STEP4 決着がつくまでくり返そう](#step4-決着がつくまでくり返そう)
- [STEP5 モンスターの反撃を作ろう](#step5-モンスターの反撃を作ろう)
- [STEP6 勝敗を表示しよう](#step6-勝敗を表示しよう)
- [Mission モンスターバトルを完成させよう](#mission-モンスターバトルを完成させよう)

</details>

<details><summary>発展課題</summary>

- [Ex1 オリジナルモンスターを作ろう](#ex1-オリジナルモンスターを作ろう)
- [Ex2 回復コマンドを追加しよう](#ex2-回復コマンドを追加しよう)
- [Ex3 クリティカル攻撃を作ろう](#ex3-クリティカル攻撃を作ろう)
- [Ex4 モンスターにも必殺技を追加しよう](#ex4-モンスターにも必殺技を追加しよう)
- [Ex5 for文でHPゲージを作ろう](#ex5-for文でhpゲージを作ろう)

</details>

- [まとめ](#まとめ)
- [参考文献](#参考文献)

# 今日作るもの
今日作る作品は、**モンスターバトルゲーム**です。<br>

「こうげき」か「ひっさつ」を入力して、モンスターと戦います。<br>
プレイヤーとモンスターのどちらかのHPが0になるまで、バトルが続きます。<br>

```text
=== モンスターバトル ===

あなたのHP: 30
モンスターのHP: 40
行動を選んでください（こうげき・ひっさつ）: こうげき
あなたの攻撃！8ダメージ！
モンスターの攻撃！5ダメージ！

あなたのHP: 25
モンスターのHP: 32
行動を選んでください（こうげき・ひっさつ）: ひっさつ
必殺技！14ダメージ！
```

攻撃のダメージは毎回ランダムに変わります。<br>
必殺技は大きなダメージが出ることもありますが、外れて0ダメージになることもあります。<br>

# プログラム全体図
```text
① プレイヤーとモンスターのHPを決める
                  ↓
② プレイヤーがコマンドを入力する
                  ↓
③ コマンドに合わせて攻撃する
                  ↓
④ モンスターのHPを減らす
                  ↓
⑤ モンスターが残っていれば反撃する
                  ↓
⑥ どちらかのHPが0になるまでくり返す
                  ↓
⑦ 勝ち・負けを表示する
```

この作品は、Month1からMonth4までに学んだ内容を組み合わせて作ります。<br>

- 変数でHPを記録する
- `input`でコマンドを選ぶ
- `if / elif / else`で行動を変える
- `random`でダメージを決める
- `while`でバトルをくり返す
- 条件式でバトルの終了を判断する

# 前回の復習
前回は、正解するまで続く暗号解除ゲームを作りました。<br>

```python:demo.py
secret = 13
guess = 0

while guess != secret:
  guess = int(input("秘密の数字を入力してください: "))

  if guess == secret:
    print("暗号解除成功！")
  elif guess < secret:
    print("もっと大きい数字です")
  else:
    print("もっと小さい数字です")
```

`while`は、条件式が`True`の間、処理をくり返します。<br>
今回は、プレイヤーとモンスターの両方にHPが残っている間、バトルをくり返します。<br>

# バトルに必要な変数
ゲームの中で変化する数字は、変数に入れて管理します。<br>

```python:demo.py
# プレイヤーのHPを決める
player_hp = 30

# モンスターのHPを決める
monster_hp = 40

# 今のHPを表示する
print("あなたのHP: " + str(player_hp))
print("モンスターのHP: " + str(monster_hp))
```

`str()`を使うと、整数を文字列に変えて、ほかの文字と`+`でつなげられます。<br>

```text
player_hp = 30
        ↓ str()
文字列の"30"になる
        ↓
"あなたのHP: " + "30"
```

## Work1 HPを表示しよう
プレイヤーのHPを50、モンスターのHPを60にして、次のように表示してください。<br>

```text
あなたのHP: 50
モンスターのHP: 60
```

<details><summary>答え</summary>

```python:demo.py
player_hp = 50
monster_hp = 60

print("あなたのHP: " + str(player_hp))
print("モンスターのHP: " + str(monster_hp))
```

</details>

# STEP1 攻撃でHPを減らそう
プレイヤーが攻撃したら、モンスターのHPを減らします。<br>

```python:demo.py
# モンスターのHPを決める
monster_hp = 40

# 攻撃のダメージを決める
damage = 8

# モンスターのHPからダメージを引く
monster_hp = monster_hp - damage

# 残りHPを表示する
print("8ダメージ！")
print("モンスターのHP: " + str(monster_hp))
```

`monster_hp = monster_hp - damage`では、今のHPからダメージを引いた結果を、もう一度`monster_hp`に入れています。<br>

```text
最初のmonster_hpは40
damageは8
        ↓
40 - 8 = 32
        ↓
新しいmonster_hpは32
```

## Work2 プレイヤーのHPを減らそう
プレイヤーのHPを30、受けるダメージを5として、攻撃後のHPを表示してください。<br>

<details><summary>答え</summary>

```python:demo.py
player_hp = 30
damage = 5

player_hp = player_hp - damage

print("プレイヤーは5ダメージを受けた！")
print("あなたのHP: " + str(player_hp))
```

</details>

# STEP2 ダメージをランダムにしよう
いつも同じダメージでは、結果が毎回同じになります。<br>
`random.randint()`を使って、攻撃のダメージを変えましょう。<br>

```python:demo.py
# randomモジュールを使えるようにする
import random

# モンスターのHPを決める
monster_hp = 40

# 5から10までの攻撃ダメージを作る
damage = random.randint(5, 10)

# モンスターのHPを減らす
monster_hp = monster_hp - damage

# ダメージと残りHPを表示する
print("あなたの攻撃！" + str(damage) + "ダメージ！")
print("モンスターのHP: " + str(monster_hp))
```

何度か実行して、ダメージが変わることを確認してください。<br>

## Work3 ダメージの範囲を変えよう
攻撃のダメージが10から20までになるように変更してください。<br>

<details><summary>答え</summary>

```python:python
damage = random.randint(10, 20)
```

</details>

# STEP3 コマンドを選べるようにしよう
`input()`を使って、「こうげき」と「ひっさつ」を選べるようにします。<br>

```python:demo.py
command = input("行動を選んでください（こうげき・ひっさつ）: ")
```

入力されたコマンドを、`if / elif / else`で判定します。<br>

```python:demo.py
if command == "こうげき":
  # 通常攻撃は5から10ダメージ
  damage = random.randint(5, 10)
  print("あなたの攻撃！" + str(damage) + "ダメージ！")

elif command == "ひっさつ":
  # 必殺技は0から15ダメージ
  damage = random.randint(0, 15)
  print("必殺技！" + str(damage) + "ダメージ！")

else:
  # 知らないコマンドでは攻撃できない
  damage = 0
  print("そのコマンドは使えません")
```

通常攻撃は必ず5以上のダメージが出ます。<br>
必殺技は最大15ダメージですが、0ダメージになることもあります。<br>

コマンドを判定した後で、モンスターのHPを減らします。<br>

```python:python
monster_hp = monster_hp - damage
```

# STEP4 決着がつくまでくり返そう
1回の攻撃だけでは、バトルがすぐに終わってしまいます。<br>
どちらかのHPが0になるまで、`while`でバトルをくり返します。<br>

## andで2つの条件をつなげよう
バトルを続けるためには、次の2つを両方とも満たす必要があります。<br>

```text
プレイヤーのHPが0より大きい
            そして
モンスターのHPが0より大きい
```

2つの条件を両方とも満たしているか調べるときは、`and`を使います。<br>

```python:python
while player_hp > 0 and monster_hp > 0:
```

| プレイヤーHP | モンスターHP | バトルを続ける？ |
|---:|---:|---|
| 30 | 40 | 続ける |
| 10 | 0 | 終わる |
| 0 | 20 | 終わる |

攻撃のプログラムをwhileの中に入れます。<br>

```python:main.py
import random

player_hp = 30
monster_hp = 40

# 両方のHPが残っている間、バトルをくり返す
while player_hp > 0 and monster_hp > 0:
  # 今のHPを表示する
  print("あなたのHP: " + str(player_hp))
  print("モンスターのHP: " + str(monster_hp))

  # 行動を入力する
  command = input("行動を選んでください（こうげき・ひっさつ）: ")

  # 入力されたコマンドで攻撃方法を変える
  if command == "こうげき":
    damage = random.randint(5, 10)
    print("あなたの攻撃！" + str(damage) + "ダメージ！")
  elif command == "ひっさつ":
    damage = random.randint(0, 15)
    print("必殺技！" + str(damage) + "ダメージ！")
  else:
    damage = 0
    print("そのコマンドは使えません")

  # モンスターのHPを減らす
  monster_hp = monster_hp - damage
```

この段階ではモンスターが反撃しないので、プレイヤーは負けません。<br>
次のSTEPで反撃を追加します。<br>

# STEP5 モンスターの反撃を作ろう
プレイヤーが攻撃した後、モンスターが残っていれば反撃します。<br>

```python:python
# モンスターが残っていれば反撃する
if monster_hp > 0:
  enemy_damage = random.randint(3, 8)
  player_hp = player_hp - enemy_damage
  print("モンスターの攻撃！" + str(enemy_damage) + "ダメージ！")
```

`if monster_hp > 0:`が必要な理由を考えてみましょう。<br>
この条件がないと、HPが0になったモンスターも反撃してしまいます。<br>

## HPがマイナスにならないようにしよう
大きなダメージを受けると、HPがマイナスになることがあります。<br>
HPが0より小さくなったら、0に直します。<br>

```python:python
if monster_hp < 0:
  monster_hp = 0

if player_hp < 0:
  player_hp = 0
```

# STEP6 勝敗を表示しよう
whileが終わった後、どちらのHPが残っているか調べます。<br>

```python:python
if player_hp > 0:
  print("モンスターを倒した！あなたの勝ち！")
else:
  print("力尽きてしまった……")
```

whileが終わるのは、どちらかのHPが0になったときです。<br>
そのときプレイヤーのHPが残っていれば、モンスターのHPが0になっているため勝ちです。<br>

# Mission モンスターバトルを完成させよう
## ミッション内容
コマンドを入力して戦う、モンスターバトルゲームを完成させましょう。<br>

## 完成条件
- プレイヤーとモンスターのHPを変数に入れる<br>
- `input()`で「こうげき」と「ひっさつ」を選ぶ<br>
- `if / elif / else`で攻撃方法を変える<br>
- `random.randint()`でダメージを決める<br>
- `while`で、決着がつくまでバトルを続ける<br>
- モンスターが残っているときだけ反撃する<br>
- 最後に勝ち・負けを表示する<br>
- 処理の説明になるコメントを8つ以上書く<br>

## 完成例
```python:main.py
# randomモジュールを使えるようにする
import random

# ゲームのタイトルを表示する
print("=== モンスターバトル ===")
print("あばれドラゴンが現れた！")

# プレイヤーとモンスターのHPを決める
player_hp = 30
monster_hp = 40

# 両方のHPが残っている間、バトルをくり返す
while player_hp > 0 and monster_hp > 0:
  # 今のHPを表示する
  print("")
  print("あなたのHP: " + str(player_hp))
  print("モンスターのHP: " + str(monster_hp))

  # プレイヤーの行動を入力する
  command = input("行動を選んでください（こうげき・ひっさつ）: ")

  # 入力されたコマンドで攻撃方法を変える
  if command == "こうげき":
    # 通常攻撃のダメージを決める
    damage = random.randint(5, 10)
    print("あなたの攻撃！" + str(damage) + "ダメージ！")

  elif command == "ひっさつ":
    # 必殺技のダメージを決める
    damage = random.randint(0, 15)
    print("必殺技！" + str(damage) + "ダメージ！")

  else:
    # 知らないコマンドでは攻撃できない
    damage = 0
    print("そのコマンドは使えません")

  # モンスターのHPを減らす
  monster_hp = monster_hp - damage

  # モンスターのHPがマイナスなら0にする
  if monster_hp < 0:
    monster_hp = 0

  # モンスターが残っていれば反撃する
  if monster_hp > 0:
    # モンスターの攻撃ダメージを決める
    enemy_damage = random.randint(3, 8)
    player_hp = player_hp - enemy_damage
    print("モンスターの攻撃！" + str(enemy_damage) + "ダメージ！")

    # プレイヤーのHPがマイナスなら0にする
    if player_hp < 0:
      player_hp = 0

# 最後のHPを表示する
print("")
print("あなたのHP: " + str(player_hp))
print("モンスターのHP: " + str(monster_hp))

# プレイヤーのHPを調べて勝敗を表示する
if player_hp > 0:
  print("あばれドラゴンを倒した！あなたの勝ち！")
else:
  print("力尽きてしまった……")
```

# Ex1 オリジナルモンスターを作ろう
モンスターの名前、登場メッセージ、HPを変更してください。<br>

例：<br>

```text
あばれドラゴン → 宿題を食べるケシゴム
HP40 → HP50
```

名前を変数に入れると、いろいろな場所で同じ名前を使えます。<br>

<details><summary>答えの枠組み</summary>

```python:python
monster_name = "宿題を食べるケシゴム"
monster_hp = 50

print(monster_name + "が現れた！")
print(monster_name + "のHP: " + str(monster_hp))
```

</details>

# Ex2 回復コマンドを追加しよう
「かいふく」を入力すると、HPが回復するようにしてください。<br>
回復できるのは2回までにします。<br>

バトルの前に、回復できる回数を変数に入れます。<br>

```python:python
heal_count = 2
```

<details><summary>答えの枠組み</summary>

`elif command == "ひっさつ":`の後、`else:`の前に追加します。<br>

```python:python
elif command == "かいふく":
  if heal_count > 0:
    heal = random.randint(5, 10)
    player_hp = player_hp + heal
    heal_count = heal_count - 1
    damage = 0
    print("HPが" + str(heal) + "回復した！")
    print("あと" + str(heal_count) + "回回復できます")
  else:
    damage = 0
    print("もう回復できません")
```

</details>

# Ex3 クリティカル攻撃を作ろう
通常攻撃をしたとき、5分の1の確率でクリティカル攻撃が出るようにしてください。<br>

<details><summary>答えの枠組み</summary>

```python:python
if command == "こうげき":
  critical = random.randint(1, 5)

  if critical == 1:
    damage = random.randint(15, 20)
    print("クリティカル！" + str(damage) + "ダメージ！")
  else:
    damage = random.randint(5, 10)
    print("あなたの攻撃！" + str(damage) + "ダメージ！")
```

</details>

# Ex4 モンスターにも必殺技を追加しよう
モンスターの攻撃方法もランダムに変えてください。<br>

```text
1または2 → 普通の攻撃
3         → 必殺技
```

<details><summary>答えの枠組み</summary>

```python:python
enemy_command = random.randint(1, 3)

if enemy_command == 3:
  enemy_damage = random.randint(8, 12)
  print("モンスターの必殺技！" + str(enemy_damage) + "ダメージ！")
else:
  enemy_damage = random.randint(3, 8)
  print("モンスターの攻撃！" + str(enemy_damage) + "ダメージ！")

player_hp = player_hp - enemy_damage
```

</details>

# Ex5 for文でHPゲージを作ろう
数字だけでなく、`■`を並べてHPを表示してみましょう。<br>

`for`文で、HPの数だけ`■`を文字列につなげます。<br>

<details><summary>答えの枠組み</summary>

```python:python
player_bar = ""

for i in range(player_hp):
  player_bar = player_bar + "■"

print("あなたのHP: " + player_bar)
```

モンスター用のHPゲージも作ってみましょう。<br>

</details>

# まとめ
今日は、これまでに学んだPythonの命令を組み合わせて、モンスターバトルゲームを作りました。<br>

今回の大事なポイントは次のとおりです。<br>

- HPのように変化する数字は、変数で管理できる
- `変数 = 変数 - ダメージ`と書くと、HPを減らせる
- `input`と`if / elif / else`を組み合わせると、プレイヤーが行動を選べる
- `random.randint()`を使うと、毎回違う結果を作れる
- `while`を使うと、決着がつくまでゲームを続けられる
- `and`を使うと、2つの条件を両方満たしているか調べられる
- コメントを書いて処理を分けると、長いプログラムも整理しやすくなる

変数・条件式・条件分岐・くり返し・入力・randomを組み合わせると、いろいろなゲームを作れます。<br>
完成したプログラムの数字やメッセージを変更し、自分だけのゲームにしてください。<br>

# 参考文献
[1] https://www.python.org/<br>
[2] https://docs.python.org/ja/3/tutorial/controlflow.html<br>
[3] https://docs.python.org/ja/3/reference/compound_stmts.html#while<br>
[4] https://docs.python.org/ja/3/library/functions.html#input<br>
[5] https://docs.python.org/ja/3/library/random.html<br>

**Acknowledgement**  
This material was reviewed and refined with the assistance of ChatGPT (OpenAI).

