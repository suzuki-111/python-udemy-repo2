This is my first repo
# python-udemy-repo2

 lesson.py 

#名前空間とスコープ

animal = 'cat'  #グローバル変数

def f():
   # print(animal)   #関数内でanimalをローカル変数として次の行で宣言、宣言前にprintを実行しようとしているためエラーが出る
    animal = 'dog'  #ローカル変数
    print('after:', animal)

f()                 #上記ではprint文がなければエラーは出ない

print('###########')
####################

animal = 'cat'  # グローバル変数


def f():
    global animal   # グローバル変数
    animal = 'dog'  # ローカル変数
    print('local:', animal)

    print(locals()) #関数内にあるローカル変数を確認したい時locals()

f()
print('global:', animal)

print('##############')
########################

print(globals())  #コード内にあるグローバル変数を確認したい時globals()
