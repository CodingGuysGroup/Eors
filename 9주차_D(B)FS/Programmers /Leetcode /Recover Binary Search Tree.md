### `문제 설명`
#### English

You are given the root of a binary search tree (BST), where the values of exactly two nodes of the tree were swapped by mistake. Recover the tree without changing its structure.


![image](https://github.com/CodingGuysGroup/Eors/assets/86946575/bcb1fab2-5871-4bf4-b0e7-676c618c3b53)
![image](https://github.com/CodingGuysGroup/Eors/assets/86946575/30bfbe81-4905-4903-8fca-cdeb96040cd3)

### `Constraints`

The number of nodes in the tree is in the range [2, 1000].

-231 <= Node.val <= 231 - 1


---

```python

class Solution:
    def recoverTree(self, root: Optional[TreeNode]) -> None:
        # 이 리스트에는 노드와 그 노드의 값이 튜플 형태로 저장
        nodes_values = []

        # 이 함수는 트리를 중위 순회
        def inorder(root):
            if not root:
                return
            inorder(root.left)
            # 노드와 그 노드의 값을 튜플로 만들어 리스트에 저장
            nodes_values.append((root, root.val))
            inorder(root.right)

        # 중위 순회를 수행하여 nodes_values를 채움
        inorder(root)

        # nodes_values라는 리스트 안의 튜플들에서 노드의 값을 가져와서 정렬(노드 값만)
        sorted_values = sorted(map(lambda x: x[1], nodes_values))

        # 정렬된 값들을 각 노드에 할당
        for i in range(len(nodes_values)):
            nodes_values[i][0].val = sorted_values[i]

        return root 

    ```
  ![image](https://github.com/CodingGuysGroup/Eors/assets/86946575/588af3bf-0ff3-486f-b990-34f3c3a82641)

