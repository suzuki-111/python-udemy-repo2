This is my first repo
# python-udemy-repo2

 lesson.py 

#クロージャー
def circle_area_func(pi):
    def circle_area(radius):
        return  pi * radius * radius

    return circle_area

ca1 = circle_area_func(3.14)
ca2 = circle_area_func(3.141592)       #同じ関数でも引数を変えることで別の使い方ができる

print(ca1(10))
print(ca2(10))

print('###########')
####################

#デコレーター：関数の間に別の命令を挟んだりするときに使う

def print_more(func):
    def wrapper(*args, **kwargs):
        print('func:', func.__name__)
        print('args:', args)
        print('kwargs:', kwargs)
        result = func(*args, **kwargs)          #挟み込む関数の位置
        print('result:', result)
        return result
    return wrapper

def print_info(func):
    def wrapper(*args, **kwargs):
        print('start')
        result = func(*args, **kwargs)
        print('end')
        return result
    return wrapper

@print_info                                     #一番目に挟み込む関数
@print_more                                     #二番目に挟み込む関数
def add_num(a, b):                              #挟み込む関数
    return  a + b

r = add_num(10, 20)
print(r)

print('###########')
####################

#ラムダ
l = ['Mon', 'tue', 'Wed', 'Thu', 'fri', 'sat', 'Sun']

def change_words(words, func):
    for word in words:
        print(func(word))

#def sample_func(word):
#    return word.capitalize()

# sample_func = lambda word: word.capitalize()

change_words(l, lambda  word: word.capitalize())   #ラムダを使えば上記のような簡単な関数を一行にまとめて書くことができる

print('##########')
###################
#ジェネレーター
#ジェネレーターはfor文とは異なり連続の処理ではなく一回ごとに止めて状態を保持する
#一個ずつ呼び出したり、重い処理を複数回にわけることで軽くするときなどに使われる

def counter(num=10):
    for _ in range(num):
        yield 'run'

def greeting():
    yield 'Good morining'
    yield 'Good afternoon'
    yield 'Good night'

g = greeting()
c = counter()

print(next(g))

print(next(c))
print(next(c))
print(next(c))
print(next(c))
print(next(c))

print(next(g))

print(next(c))
print(next(c))
print(next(c))
print(next(c))
print(next(c))

print(next(g))
