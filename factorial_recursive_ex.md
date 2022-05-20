19 lines (13 sloc)  410 Bytes
   
## 재귀함수에 대한 정리


**1. 개요**

컴퓨터 내부 재귀 함수의 수행은 기본적으로 stack 자료 구조를 이용한다.  
함수를 재귀적으로 호출 시 가장 마지막에 호출 된 한수가 먼저 수행을 끝내야 그 앞의 함수 호출이 종료된다.  
```python
def recursive_function_ex(i):
    if i == 100: # a
        return

    print(f'{i}번째 재귀 함수에서 {i}+1 번쨰 재귀함수 호출') # b
    recursive_function_2(i + 1) # c
    print(f'{i}번째 재귀 함수 종료') # d
```
위의 코드의 흐름도  
메인 함수 호출 -> b -> c (재귀적 호출) -> b -> c -> ... -> if 문 만족 시 -> return -> d (가장 마지막에 있던 i 값부터 print)  
  

**2. 재귀적 팩토리얼 함수 구현**

```python
def factorial_recursive(n): # n = 5
    
    if n <= 1:
        return 1

    return n * factorial_recursive(n-1)
```

```
120
```

함수의 흐름은 하단 <그림1.> 및 <그림2.> 참조

![흐름도](https://user-images.githubusercontent.com/84132135/169472662-7c6ff011-1f60-4355-8c64-eec3723b4c66.jpg)
![반환도](https://user-images.githubusercontent.com/84132135/169472672-f926c815-449a-4518-b668-43ba4444871c.jpg)

