
# import functionls
## `functools.cmp_to_key(func)`

functools.cmp_to_key(func)는 sorted()와 같은 정렬 함수의 key 매개변수에 함수(func)를 전달할 때 사용하는 함수이다. 단, func() 함수는 두 개의 인수를 입력하여 첫 번째 인수를 기준으로 그 둘을 비교하고 작으면 음수, 같으면 0, 크면 양수를 반환하는 비교 함수이어야 한다.

```python
import functools

def xy_compare(n1, n2):
    if n1[1] > n2[1]:         # y 좌표가 크면
        return 1
    elif n1[1] == n2[1]:      # y 좌표가 같으면
        if n1[0] > n2[0]:     # x 좌표가 크면
            return 1
        elif n1[0] == n2[0]:  # x 좌표가 같으면
            return 0
        else:                 # x 좌표가 작으면
            return -1
    else:                     # y 좌표가 작으면
        return -1

src = [(0, 4), (1, 2), (1, -1), (2, 2), (3, 3)]
result = sorted(src, key=functools.cmp_to_key(xy_compare))
print(result)
```
출력결과는 다음과 같다.


            [(1, -1), (1, 2), (2, 2), (3, 3), (0, 4)]


## `join`


### 사용 모양
` ''.join(리스트)`

`'구분자'.join(리스트)`

```python
a = ['a', 'b', 'c', 'd', '1', '2', '3']
print(a)
print()
 
# 리스트를 문자열로 : join 이용
result1 = "".join(a)
print(result1)
 
 
# 리스트를 문자열로 : 하나하나 문자열을 더해서.
result2 = ''
for v in a:
    result2 += v
 
print(result2)
```

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbkjHhy%2FbtqQpsE9V8D%2FtnB5J82VttqKkQa1FBjAA0%2Fimg.png)