
## `input`
> 일반적으로 사용 `a = input()`


        하지만 실행 속도: sys.stdin.readline() > input()  


> 다음과 같은 격자형 입력값이 있으면 

        5
        0 1 0 1 0
        1 0 0 0 0
        1 1 1 0 0
        0 1 0 1 0
        0 0 1 0 0   

        >>> import sys
        >>> n = int(sys.stdin.readline())
        >>> datas = []
        >>> while n:
            n -= 1
            line = sys.stdin.readline().rstrip()
            datas.append(line)

        print(datas) # ['0 1 0 1 0', '1 0 0 0 0', '1 1 1 0 0', '0 1 0 1 0', '0 0 1 0 0']

> `rstrip()`을 사용하여 오른쪽에 있는 공백을 지웠다. 여기서 rstrip()을 안쓰면 다음과 같이 개행문자가 남아있게 된다

        ['0 1 0 1 0\n', '1 0 0 0 0\n', '1 1 1 0 0\n', '0 1 0 1 0\n', '0 0 1 0 0\n']


> 2차원 배열처럼 입력받을때 

        >>> import sys
        >>> n = int(sys.stdin.readline())
        >>> datas = []
        >>> while n:
            n -= 1
            line = sys.stdin.readline().rstrip().split()
            datas.append(line)

        >>> print(datas)

        [['0', '1', '0', '1', '0'], ['1', '0', '0', '0', '0'], ['1', '1', '1', '0', '0'], ['0', '1', '0', '1', '0'], ['0', '0', '1', '0', '0']]


### `sys.stdin.readline() 사용법`
> sys.stdin.readline()은 한줄 단위로 입력받기 때문에, 개행문자가 같이 입력 받아집니다.
만약 3을 입력했다면, 3\n 이 저장되기 때문에, 개행문자를 제거해야 합니다.</br>
또한, 변수 타입이 문자열 형태(str)로 저장되기 때문에, 정수로 사용하기 위해서 형변환을 거쳐야 합니다.

        >>> import sys
        >>> a = int(sys.stdin.readline())

### `입력값에 대해 각각 매칭`
>`split()` 나누기 <br>
>map()은 반복 가능한 객체(리스트 등)에 대해 각각의 요소들을 지정된 함수로 처리해주는 함수입니다.</br>
아래와 같이 사용한다면 a,b,c에 대해 각각 int형으로 형변환을 할 수 있습니다.

        >>> import sys
        >>> a,b,c = map(int,sys.stdin.readline().split())

### `문자열 n줄을 입력받아 리스트에 저장할 때`
> `strip()`은 문자열 맨 앞과 맨 끝의 공백문자를 제거합니다.
            >>> import sys
            >>> n = int(sys.stdin.readline())
            >>> data = [sys.stdin.readline().strip() for i in range(n)]

            # 입력
            3
            안녕안녕
            나는 지수야
            헬륨가스 마셨더니 이렇게됐지

            # 출력
            ['안녕안녕', '나는 지수야', '헬륨가스 마셨더니 이렇게됐지']