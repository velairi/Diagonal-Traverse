# Diagonal Traverse

Leetcode #498
Diagonal Traverse 
https://leetcode.com/problems/diagonal-traverse/


```
func diagonalTraverse(_ matrix: [[Int]]) -> [[Int]] {
    var i = 0, j = 0
    var diagonalArr = [[Int]]()
    //looping through the rows
    for k in 0..<matrix.count {
        i = k
        j = 0
        var arr = [Int]()
        while i >= 0 && j < matrix[0].count {
            arr.append(matrix[i][j])
            i -= 1
            j += 1
        }
        if k % 2 != 0 {
            arr.reverse()
        }
        diagonalArr.append(arr)
    }
    //looping through the bottom row elements
    let lastRow = matrix.count - 1
    for k in 1..<matrix[lastRow].count {
        i = matrix.count - 1
        j = k
        var arr = [Int]()
        while j <= matrix[lastRow].count - 1 {
            arr.append(matrix[i][j])
            i -= 1
            j += 1
        }
        if k % 2 != 0 {
            arr.reversed()
        }
        diagonalArr.append(arr)
    }
    return diagonalArr
}
```



