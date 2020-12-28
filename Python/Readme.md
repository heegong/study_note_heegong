# 2020-12-26

## __len__이 친구를 알았다.

```ls = [1,2,3]
print(ls.__len__())

print(len(ls))
```

<br><br><br><br>
1번 print랑 2번 print랑 같은 역할을 한다
  

'''class A:
    def __len__(self):
        return 5

print(len(A()))
'''

했을 때 5가 출력된다.







# 2020-12-28

파이썬 2같은 경우에는 
```x = 'aaa'
dummy = [x for x in 'abc']          #리스트 컴프리헨션
print(x)
```

했을 때  c가 나온다.     이런식으로 메모리 누수가 난다.
하지만 파이썬3은 메모리 누수가 나지 않는다.




## 파이썬에도 array가 있다. 
```
import array

a = array.array('I',{1,2,3})
print(a.itemsize)
print(len(a))
print(a[0])
```

```
import array

a = array.array('u','12345')
print(a.itemsize)
print(len(a))
print(a[0])
```

이런식으로 사용이 가능하다.





```
t = (20,8)
divmod(*t)
```
함수에서 튜플을 쓸때 *를 붙여서 언패킹이 가능하다.


```
a,b, *rest = range(5)
print(a,b,rest)
```
언패킹을 응용할 수 있다.

결과값 : 0 1 [2, 3, 4]
