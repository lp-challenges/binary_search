# Binary Search
#### The Big O notation for Binary Search is O(log N). In contrast to O(N) which takes an additional step for each data element, O(log N) means that the algorithm takes an additional step each time the data doubles. 

`let numbers = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]` <br>
`let value = 13`

```
func binarySearch(in numbers: [Int], for value: Int) -> Int? {
  var left = 0
  var right = numbers.count - 1
  
  while left <= right {
    let middle = Int(floor(Double(left + right) / 2.0))
    print("Looking for \(value) in \(numbers[left...right])")
    print("Middle index is \(middle), value is \(numbers[middle])")
    
    if numbers[middle] < value {
      print("\(numbers[middle]) is smaller than \(value), choosing right half of array")
      left = middle + 1
      print("left = \(left)")
    } else if numbers[middle] > value {
      print("\(numbers[middle]) is bigger than \(value), choosing left half of array")
      right = middle - 1
      print("right = \(right)")
    } else {
        return middle
    }
  }
  return nil
}
```
## Finding the missing number usinng hashing technique

An array A consisting of N different integers is given. The array contains integers in the range [1..(N + 1)], which means that exactly one element is missing.
```
public func solution(_ A : inout [Int]) -> Int {
    var missingNumber = A.first ?? 0 
    var tempArray = [Int](repeating: 0, count: A.count + 2)
    for element in A {
        tempArray[element] = 1
    }
    for (index, tempElement) in tempArray.enumerated() {
        if index == 0 {
            continue
        }
        if tempElement == 0 {
            missingNumber = index
            break
        }
    }
    return missingNumber
}
```
