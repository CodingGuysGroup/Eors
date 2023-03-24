## functools.reduce
- “여러 개의 데이터를 대상으로 주로 누적 집계를 내기 위해서 사용하는 함수”
- for loop를 간소화해서 사용할 수 있는 함수
- 초기값 세팅도 할 수 있어서 간편해 보임


### `Q. 리스트에 1부터 20까지의 정수가 담겼을 때, 해당 리스트의 모든 요소의 합을 출력하는 코드를 작성하시오.`


- 일반 적인 풀이법 
```python
def SumFunction(x, y):
    return x + y

target = list(range(1, 21))
result = 0
for value in target:
    result = SumFunction(result, value)
print(result) # 실행 결과: 210
```

```python
from functools import reduce
target = list(range(1, 21))
# sumfunction을 lamda 식
# target의 값을 x나 y에 주고 하나를 0으로 초기화 하는 듯
print(reduce(lambda x, y: x + y, target)) # 실행 결과: 210
