# quiz_day5

## 1.

### 두 값 중 큰 값을 구하는 함수(max2)를 작성하시오. 같으면 '같음'을 리턴하시오.


```
def max2(a,b):
    if a == b:
        return print('같음')
    elif a > b:
        return print(a)
    else:
        return print(b)
```

## 2.

### n개의 인자를 받아 가장 큰 값을 구하는 함수를 작성하시오.

```
def maxN(*args):
    list_max=[*args]
    len_list_max=len(list_max)-1
    for a in range(len_list_max):
        for b in range(a,len_list_max-a):
            if list_max[b+1] > list_max[b]:
                list_max[a],list_max[b] = list_max[b],list_max[a]

        print(list_max[-1])
```
> bubble sort 형식으로 풀어보았다.

```
def amaxN(*args):
    max_=0
    for arg in args:
        if arg>max_:
            max_=arg

    return arg
```
> 이렇게 간단하게도 할 수 있다.