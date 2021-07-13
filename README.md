# binary_search
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
