## `Problem explain`

There are n children standing in a line. Each child is assigned a rating value given in the integer array ratings.

You are giving candies to these children subjected to the following requirements:

- Each child must have at least one candy.
- Children with a higher rating get more candies than their neighbors.
Return the minimum number of candies you need to have to distribute the candies to the children.

## `Example`
            Input: ratings = [1,0,2]
            Output: 5
            Explanation: You can allocate to the first, second and third child with 2, 1, 2 candies respectively.
            
            
            
 ---
 
 ##  `ANS`
 ```python3
 class Solution(object):
    def candy(self,ratings):
        n = len(ratings)
        if n == 1:
            return n

        # 좌우 나눔  
        arr_1 = [1] * n
        arr_2 = [1] * n

        # 왼쪽에서 오른쪽으로 진행하면서 필요한 경우 사탕을 더 줌
        for i in range(1, n):
            if ratings[i] > ratings[i-1]:
                arr_1[i] = arr_1[i-1] + 1
        # 반대로 
        for i in range(n-2, -1, -1):
            if ratings[i] > ratings[i+1]:
                arr_2[i] = arr_2[i+1] + 1

        ans = 0

        for i in range(n):
            ans += max(arr_1[i], arr_2[i])

        return ans
        ```
 ![image](https://github.com/CodingGuysGroup/Eors/assets/86946575/2dcf2c78-c9ac-4105-a25d-6ca7ff403130)

 
