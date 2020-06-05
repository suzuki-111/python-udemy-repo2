This is my first repo
# python-udemy-repo2

 lesson.py 

def say_something(): #関数の宣言、型はfunction
    print('hi')

say_something()      #()がないと実行できない

print("\n###########\n")

def say_something():
    s = 'hi'
    return s         #返り値

result = say_something()     #関数を実行した結果の値だけを渡す
print(result)

print("\n###########\n")

def what_is_this(color): #()内の値は引数と呼ばれる変数
    if color == 'red':
        return 'tomato'
    elif color =='green':
        return 'green pepper'
    else:
        return "I don't know"

result = what_is_this('red')
result = what_is_this('green')
result = what_is_this('yellow')

print(result)

#関数定義をしてやることで同じコードを何回も書かなくて済む

print("\n###########\n")
#############################

def menu(entree, drink, dessert): #引数は複数設定可能
#def menu(entree='beef', drink='wine', dessert='ice'): #このように最初から変数に値を入れてもできる「デフォルト引数」
    print('entree =', entree)
    print('drink =', drink)
    print('dessert =', dessert)

menu(entree='beef', dessert='ice', drink='beer') #入れ間違えそうな時はこのようにキーワードで紐付けすることが可能

print("\n###########\n")
#############################

#デフォルト引数で気をつけること
def test_func(x, l = []):
    l.append(x)
    return l

#y = [1, 2, 3]
#r = test_func(100, y)
#print(r)
#y = [1, 2, 3]
#r = test_func(200, y)
#print(r)
#上記のように毎回リストを与えてやれば問題ない

r = test_func(100)
print(r)
r = test_func(100)
print(r)
#しかし上記の場合、リストにどんどん更新されていき、想定したリストと違うものができやすくバグになりやすい
#引数には空のlist, dict はあまり使うべきでない。使う場合は以下のように関数内で空のリストを定義する

def test_func(x, l=None):
    if l is None:
        l = []
    l.append(x)
    return l

r = test_func(100)
print(r)
r = test_func(100)
print(r)