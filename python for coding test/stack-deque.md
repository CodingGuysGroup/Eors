## `deque`
### `deque.rotate()를 사용해서 리스트 회전`

> collections는 유용한 자료구조를 제공하는 python의 표준 라이브러리입니다</br>

            >>> from collections import deque
            >>> test = [1, 2, 3, 4, 5, 6, 7, 8, 9]
            >>> test = deque(test)
            >>> test.rotate(2) 
            >>> result = list(test)
            >>> result
            [8, 9, 1, 2, 3, 4, 5, 6, 7]

> 위 결과를 보게되면 rotate(2)를 함으로 오른쪽으로 2만큼 회전한것을 볼 수 있다

### `deque.popleft()는 제일 끝 요소가 아니라 제일 앞의 요소가 삭제`

            >>> a = deque([1, 2, 3, 4, 5])
            >>> a.popleft()
            >>> print(a)
            deque([2, 3, 4, 5])
