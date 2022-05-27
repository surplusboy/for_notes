# 람다함수 (익명함수)

함수객체를 변수에 선언
```python
def 함수명(매개변수):
  return 표현식
```

람다 표현식
```
lambda 매개변수 : 표현식
```

특징
1. 불필요한 메모리 사용 방지
2. 코드의 간결함
3. 함수명 선언을 하지 않기 때문에 재사용 불가

사용될 수 있는 곳

함수를 매개변수로 받는 map, filter, reduce 등과 사용하면 코드가 간결해진다

```
map(function, iterable)  
filter(function, iterable)  
reduce(function, iterable, initializer=None)
```



```python

test_list = [0,0,0,1,2,3,0,4]

filtet_list = list(filter(lambda x: test_list[x] == 0, range(len(test_list))))
>>> [0, 1, 2, 6]

```


선언과 동시에 사용될 수 있다.
```
(lambda x, y: x +y)(30,20)
>>> 50
```

###초기 정리, 추후 재정리###
