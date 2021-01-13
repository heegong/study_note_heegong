# 2021-01-13

```
class parent:
    def next1(self):
        self._1 += self._3
        if self._1 >= self._2:
            raise StopIteration


    
    def next2(self):
        self._1 += self._3
        if self._1 <= self._2:
            raise StopIteration



class my_range(parent):
    def __init__(self,*args):
        len_args = len(args)
        if len_args==1:
            self._1 = 0
            self._2 = args[0]
            self._3 = 1
        elif len_args==2:
            self._1 = args[0]
            self._2 = args[1]
            self._3 = 1
        else:
            self._1 = args[0]
            self._2 = args[1]
            self._3 = args[2]

        if self._3 > 0:
            self._1-=1



    def __iter__(self):
        return self


    def __next__(self):
        # self._1 += self._3
        if self._3 > 0 :
            # if self._1 >= self._2:
            #     raise StopIteration
            super().next1()
        else:
            # if self._1 <= self._2:
            #     raise StopIteration
            super().next2()
        return self._1



for i in my_range(3,0,-1):
    print(i)

```
range함수를 구핸했다.




# 2020-12-26
<br><br>
## __len__이 친구를 알았다.
<br><br>
```
ls = [1,2,3]
print(ls.__len__())

print(len(ls))
```

<br><br>
1번 print랑 2번 print랑 같은 역할을 한다
  
<br><br><br><br>

```
class A:
    def __len__(self):
        return 5

print(len(A()))
```
<br>
했을 때 5가 출력된다.



<br><br><br><br><br><br>



# 2020-12-28
<br><br>
파이썬 2같은 경우에는 
```
x = 'aaa'
dummy = [x for x in 'abc']          #리스트 컴프리헨션
print(x)
```
<br><br>
했을 때  c가 나온다.     이런식으로 메모리 누수가 난다.
하지만 파이썬3은 메모리 누수가 나지 않는다.


<br><br><br><br>

## 파이썬에도 array가 있다. 
<br><br>
```
import array

a = array.array('I',{1,2,3})
print(a.itemsize)
print(len(a))
print(a[0])
```
<br><br>
```
import array

a = array.array('u','12345')
print(a.itemsize)
print(len(a))
print(a[0])
```
<br><br>
이런식으로 사용이 가능하다.


<br><br><br><br><br>


```
t = (20,8)
divmod(*t)
```
함수에서 튜플을 쓸때 *를 붙여서 언패킹이 가능하다.

<br><br>
```
a,b, *rest = range(5)
print(a,b,rest)
```
언패킹을 응용할 수 있다.

결과값 : 0 1 [2, 3, 4]
