This is my first repo
# python-udemy-repo2

 lesson.py 

#例外処理：エラーが出ても無視してプログラムを進める

l = [1, 2, 3]
i = 5

try:
    () + l              #タプル型とリスト型の足し算でエラー
except IndexError as ex:
    print("Don't worry: {}".format(ex))
except NameError as ex:
    print(ex)
except Exception as ex:         #exceptでエラーが出てもプログラムを止めずに別の指示を実行する
    print('other:{}'.format(ex))
print("last")

#上記の書き方の最後のotherでは全てのエラーを内包するので何がエラーかわかりにくくなるため避けるべき

print('##############')
#######################

l = [1, 2, 3]
i = 5

try:
    () + l
except IndexError as ex:
    print("Don't worry: {}".format(ex))
except NameError as ex:
    print(ex)
except Exception as ex:
    print('other:{}'.format(ex))
finally:                  #finallyがあるときはエラーがあっても止まる直前に必ず実行する
    print("clean up")

print('##############')
#######################

l = [1, 2, 3]
i = 5

try:
    l[0]
except IndexError as ex:
    print("Don't worry: {}".format(ex))
except NameError as ex:
    print(ex)
except Exception as ex:
    print('other:{}'.format(ex))
else:
    print('done')           #except文のときにエラーがなければelse文を実行する
finally:
    print("clean up")

print('########################################')
#################################################
#################################################
print('########################################')
#独自例外の作成：オリジナルのエラー文を作成できる

class UppercaseError(Exception):
    pass


def check():
    words = ['APPLE','orange', 'banana']
    for word in words:
        if word.isupper():
            raise UppercaseError

check()

#上記のように独自例外を作成できるが他の人間がコードを見たときになぜ独自例外を作成しているのかわかるような名前にしておくs