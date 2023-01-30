# Day 16
## Object Oriented Programmin

> 用語
- クラス：オブジェクトの「ひな形」
- インスタンス：クラスから作られたオブジェクト
- インスタンス変数：インスタンスが持つ内部情報
- メソッド：クラス内に定義された関数

> オブジェクトの作り方

- クラスベース(Python)
  - オブジェクトのひな型(クラス)からオブジェクトを作る
- プロトタイプベース(JavaScript)
  - 既存のオブジェクトをコピーして作る

> クラスの例

クラス名を関数のように呼び出すとそのクラスのインスタンスが作られる
```python
c = Counter()
```
クラスの中で定義された関数を呼び出せる
```python
c.count() #=> 1
```
頭に「__」がついた変数は参照できない(カプセル化)
```python
print(c.__num)
# AttributeError: 'counter' object has no attribute '__num'
```





> クラスの定義
```python
class namename:
  def __init__(self):
    something_init
  def namemethod(self):
    do_something
```

- クラスはclassで定義する
- 初期化は```__init__```という特別な関数内で行う
- クラス内の関数と変数をまとめて属性(Attribute)と呼ぶ
- クラス内の関数をメソッド(method)と呼ぶ
- インスタンスごとに保持する関数をインスタンス変数と呼ぶ
- クラス全体で共通する変数をクラス変数と呼ぶ
