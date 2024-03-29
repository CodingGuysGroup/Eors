## `Hash`
> key -value 의태형태
>> string 기반 정보 기록,관리 시 hash 사

- 해쉬(Hash) : 임의 값을 고정 길이로 변환하는 것
- 해쉬 테이블(Hash Table) : 키값의 연산에 의해 직접 접근이 가능한 데이터 구조
- 해싱 함수(Hashing Function) : Key에 대해 산술 연산을 이용해 데이터 위치를 찾을 수 있는 함수
- 해쉬 값(Hash Value) 또는 해쉬 주소(Hash Address) : Key를 해싱 함수로 연산해서 해쉬 값을 알아내고, 이를 기반으로 해쉬 테이블에서 해당 Key에 대한 데이터 위치를 일관성 있게 찾을 수 있음
- 슬롯(Slot) : 한 개의 데이터를 저장할 수 있는 공간
저장할 데이터에 대해 Key를 추출할 수 있는 별도 함수도 존재할 수 있음

### `생성`
- `장점`
    - 데이터 저장/읽기 속도가 빠름(검색 속도가 빠름)
    - 해쉬는 키에 대한 데이터가 있는지(중복) 확인이 쉬움
- `단점`
    - 일반적으로 저장공간이 좀 더 많이 필요함
    - 여러 키에 해당하는 주소가 동일할 경우, 충동을 해결하기 위한 별도 자료구조가 핊요함
- `주요 용도`
    - 검색이 많이 필요한 경우
    - 저장, 삭제, 읽기가 빈번한 겨웅
    - 캐쉬 구현시(중복 확인이 쉽기 때문)

```python

hashmap={}
# a라는 키에 true라는 값을 넣다
bool test=hashmap.put("a",true)
#a라는 key의 값을 찾아 fine에 저
boo fine=hash.get("a")

# a라는 키가 없다면 false retrun
hash. getOrDifault("a",false)
```
### `zip`
> zip() 함수는 여러 개의 순회 가능한(iterable) 객체를 인자로 받고, 각 객체가 담고 있는 원소를 `튜플`의 형태로 차례로 접근할 수 있는 반복자(iterator)를 반환


            >>> numbers = [1, 2, 3]
            >>> letters = ["A", "B", "C"]
            >>> for pair in zip(numbers, letters):
            ...     print(pair)
            ...
            (1, 'A')
            (2, 'B')
            (3, 'C')

> zip() 함수를 활용하면 여러 그룹의 데이터를 루프를 한 번만 돌면서 처리할 수 있는데요. 가변 인자를 받기 때문에 2개 이상의 인자를 넘겨서 병렬 처리를 할 수 있습니다.
> > 예를 들어, 아래 코드는 3개의 문자열 내의 글자를 하니씩 병렬해서 출력하고 있습니다.

            >>> for number, upper, lower in zip("12345", "ABCDE", "abcde"):
            ...     print(number, upper, lower)
            ...
            1 A a
            2 B b
            3 C c
            4 D d
            5 E e
