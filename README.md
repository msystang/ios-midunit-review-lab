## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`

Answer:
```swift
var string = "Hello, there"
var stringUppercased = string.uppercased()
print(stringUppercased)
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`

Answer:
```swift
let string = "Hello, there"
let stringArray = Array(string)

var stringAlternating = ""

for (index, character) in stringArray.enumerated() {
if index % 2 == 0 {
stringAlternating.append(contentsOf: String(character.uppercased()))
} else {
stringAlternating.append(contentsOf: String(character))
}
}

print(stringAlternating)
```

3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

Answer:
```swift
let string = "Hello, there"

for character in string {
if character != "e" {
print(character, terminator: "")
}
}
```

## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

Answer:
```swift
let array = [1,5,2,4,1,4]
var largestNumber = 0

for num in array {
if num > largestNumber {
largestNumber = num
}
}
print(largestNumber)

//or

if let largestNumber2 = array.max() {
print(largestNumber2)
}
```

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`

Answer:
```swift
let array = [1,5,2,4,1,4]
var smallestNumber = 10

for num in array {
if num < smallestNumber {
smallestNumber = num
}
}
print(smallestNumber)

//or

if let smallestNumber2 = array.min() {
print(smallestNumber2)
}
```

3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`

Answer:
```swift
let array = [1,5,2,4,1,4]
var sum = 0

for num in array {
sum += num
}
print(sum)
```

4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

Answer:
```swift
let array = [3,4.5,7.5,2,1]
var sum = 0.0

for num in array {
sum += Double(num)
}

let average = sum/Double(array.count)
print(average)

```

5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

Answer:
```swift
var array = [3,4.5,7.5,2,1]
var num = 3
var sum = 0.0

func sumIfGreaterThanNum(_ array: [Double], num: Int) -> Int {
for i in array {
if i > Double(num) {
sum += i
}
}
return Int(sum)
}

let answer = sumIfGreaterThanNum(array, num: num)
print(answer)
```

6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`

Answer:
```swift
let array = [3,4.5,7.5,2,1]

func productOfAllElements(_ array: [Double]) -> Double {
var arrayDoubles = [Double]()
var product = 1.0

for num in array {
arrayDoubles.append(Double(num))
}

for num in arrayDoubles {
product *= num
}
return product
}

let answer = productOfAllElements(array)
print(answer)
```

7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`

Answer:
```swift
let array = [3,6,1,9,4,8]
var smallestValue = 1
var secondSmallestValue = 10

for num in array {
if num < smallestValue {
smallestValue = num
} else if num < secondSmallestValue && num > smallestValue {
secondSmallestValue = num
}
}
print(secondSmallestValue)
```

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`

Answer:
```swift
let array = [nil, "We", "come", nil, "in", "peace"]

func makeNoNilArray(_ array: [String?]) -> [String] {
var noNilArray = [String]()

for i in array {
if let iUnwrapped = i {
noNilArray.append(iUnwrapped)
}
}
return noNilArray
}

let answer = makeNoNilArray(array)
print(answer)
```

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`

Answer:
```swift
let array: [String?]? = nil

func removesNil(_ arr: [String?]?) -> [String] {
var noNilArray = [String]()
if let arrUnwrapped = arr {
for element in arrUnwrapped {
if let elementUnwrapped = element {
noNilArray.append(elementUnwrapped)
}
}
}
return noNilArray
}

let answer = removesNil(array)
print(answer)
```
3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`

Answer:
```swift
var array: [Int?] = [4, nil, 9, 5, nil]

func sumOfNoNil(_ arr: [Int?]) -> Int {
var noNilArray = [Int]()
for int in arr {
guard let intUnwrapped = int else {
continue
}
noNilArray.append(intUnwrapped)
}
let sum = noNilArray.reduce(0, +)
return sum
}

let answer = sumOfNoNil(array)
print(answer)
```
4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`


## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`


## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`


## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
}
```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
