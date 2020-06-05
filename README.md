This is my first repo
# python-udemy-repo2

 lesson.py 

#複数の引数を使いたい時
def say_something(word, word2, word3):
    print(word)
    print(word2)
    print(word3)

say_something('Hi', 'Mike', 'Nance')
#上記のようにするとめんどくさい。タプル型で以下のように表現すべき
#変数の前に＊をつけることで引数がタプルになる
def say_something(word, *args):
    print('word =', word)
    for arg in args:
        print(arg)

say_something('Hi!', 'Mike', 'Nance')

#下記のような表現もできる
#t = ('Mike', 'Nancy')
#say_something('Hi!', #t)

print('##########')
###################

#キーワード引数の辞書化

#def menu(entree='beef', drink='wine'):
#    print(entree, drink)

#menu(entree='beef', drink='cofee')
#上記のようなキーワードをまとめて記述できる

def menu(**kwargs):
    print(kwargs)
    for k, v in kwargs.items():
        print(k, v)

#menu(entree='beef', drink='cofee')

#辞書を別で定義してやることも可能
d = {
    'entree': 'beef',
    'drink': 'ice cofee',
    'dessert': 'ice'
}
menu(**d)

#引数の表現をいままでの全てを同時にやることも可能
#ただしargsとkwargsの順番は下記でないといけない
def menu(food, *args, **kwargs):
    print(food)
    print(args)
    print(kwargs)

menu('banana', 'apple', 'orange', entree='beef', drink='cofee')