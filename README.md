This is my first repo
# python-udemy-repo2

 lesson.py 

#モジュールとパッケージ
#lesson_packageディレクトリをパッケージ、utilsファイルをモジュールとして作成

#import  lesson_package.utils
#from lesson_package import utils
#from lesson_package.utils import say_twice #一番上のコードを下二つのように書き換えることができる
#しかし3行目のように省略したpassではどこから引っ張ってきたのかわからなくなるのでせいぜい2行目の省略にとどめておく

#r = say_twice('hello')

#print(r)

print('#########')
##################

#from lesson_package import utils as u

#r = u.say_twice('hello')
#print(r)
#asを使うことでutilsの名前を変えることができるかそれも他の人からわかりにくくなるので非推奨

print('############')
#####################
#絶対パスと相対パス

from lesson_package.talk import human

print(human.sing())
print(human.cry())


#他のファイルを使用するところなのでわからないところは動画 or ネットで調べた方が良いのでここでストップ