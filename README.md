This is my first repo
# python-udemy-repo2

 lesson.py 

#リスト内包表記
t = (1, 2, 3, 4, 5)
t2 = (5, 6, 7, 8, 9, 10)

r = []
for i in t:
    if i % 2 ==0:
        r.append(i)

print(r)

r = [i for i in t if i % 2 == 0] #上記のような複数行を一行にまとめてかける、rの中に直接for文を入れる
print(r)

r = []
for i in t:
    for j in t2:
        r.append(i * j)

print(r)

r = [i * j for i in t for j in t2]   #ただし内包表記が長くなるとわかりにくくバグに繋がりやすいコードになりがちなので注意

print(r)

print('###########')
####################
#辞書内包表記

w = ['mon', 'tue', 'wed']
f = ['coffee', 'milk', 'water']

d = {}
for x, y in zip(w, f):
    d[x] = y

print(d)

d = {x: y for x, y in zip(w, f)}
print(d)

print('###########')
###################
#集合内包表記
s = set()

for i in range(10):
    if i % 2 == 0:
        s.add(i)

print(s)

s = {i for i in range(10) if i % 2 == 0}
print(s)

print('############')
######################

def g():
    for i in range(10):
        yield i
g = g()

#g = tuple(i for i in range(10) if i % 2 == 0) #タプルにしたい時は左のようにtupleを付ける
#print(g)

g = (i for i in range(10) if i % 2 == 0)

for x in g:
    print(x)