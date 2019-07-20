## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`


```var string = "Hello, there"

print(string.uppercased())
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`

```
var alternating = String()
var stringArray = Array(string)

for i in 0..<stringArray.count {
if i % 2 == 0{
alternating.append(stringArray[i].uppercased())
} else {
alternating.append(stringArray[i].lowercased())
}
}

print(alternating)
```


3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

```
var replaced = string.replacingOccurrences(of: "e", with: "")
print(replaced)

```


## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`
```
var arr: [Int] = [1,5,2,4,1,4]
let largest = arr.max()
print(largest!)

```
2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`
```
var arr = [1,5,2,4,1,4]
let smallest = arr.min()
print(smallest!)
```
3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`

```let arr = [1,5,2,4,1,4]
var sum = 0
for i in 0..<arr.count {
sum += i
}
print(sum)
```


4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

```
let arr = [3,4.5,7.5,2,1]

var average = (arr.reduce(0, +)) / Double(arr.count)
print(average)
```

5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`
```
let arr = [3,4.5,7.5,2,1]
let given: Double = 3

let sumOfNumGreater = arr.filter {$0 > given}.reduce(0, +)
print(sumsumOfNumGreater)
```

6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`
```
let arr = [3,4.5,7.5,2,1]
let productOfAll = arr.reduce(1,*)
print(productOfAll)
```
7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`
```
var input = [20,10,1,3,4,0]
var small = Int.max
var secondSmall = 0
for i in input {
if i < small {
secondSmall = small
small = i
}
}
print(secondSmall)
```

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`

```
var strArray: [String?] = [nil, "We", "come", nil, "in", "peace"]

var newArray: [String] = []

for i in strArray {
if i != nil {
(newArray.append(i!))
}
}

print(newArray)


```

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`
```
var nilArray: [String?]? = [nil] 
var emptyArray: [String] = []

if let nilArray = nilArray { 
for i in nilArray { 
if let i = i { 
emptyArray.append(i)
} 
}
} 
print(emptyArray)

```

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18'
```
var intArray: [Int?] = [4, nil, 9, 5, nil]
var sum = 0 
for i in intArray { 
guard let i = i else { 
continue } 
sum += i } 
print(sum)
```

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`
```
var nilArray
for i in nilArray { 
guard let i = i else 
{ continue } 
sum += i } 
print(sum)
```

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`
```
var intArray: [Int?] = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3, 1]

var optionalInt: Int? = 1

var sum = 0

for i in intArray {
if let i = i {
if let optionalInt = optionalInt {
if i != optionalInt { sum += i}

}
}
}

print(sum)

//here it is as a function with the given number as an argument

var sum = 0

func ifNotNilThenSum(a: [Int?],b : Int) -> Int {
for i in a{
if i != nil && i != b {
sum += i!
}
}
return(sum)
}

print(ifNotNilThenSum(a: intArray, b: 1 ))


```

## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`
```
var someDict = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]
var anoter = Set(someDict)
print(anoter)
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`
```
var input = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var dict = [Character:Int]()
var someLetter = "qwertyuiopasdfghjklzxcvbnm"
for i in input where someLetter.contains(i) {

if dict.keys.contains(i){
dict.updateValue(dict[i]!+1, forKey: i)
}
else {
dict[i] = 1
}
}
print(dict)
var mostFrequent = 0
var mostFrequentLetter = ""
for (k,v) in dict {
if v > mostFrequent{
mostFrequent = v
mostFrequentLetter = String(k)
}
}
print(mostFrequentLetter)
```

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
