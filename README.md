
# Hexagonal Grid

## Requirement : 

```
Here is a screenshot from an iOS app. There is an arrangement of 19 circles in a hexagonal grid, and each circle contains a number. The screenshot contains example numbers with the following properties:
A. The grid can be divided into 6 tiles of 3 adjacent circles (with 1 circle left over).
B. Each tile of 3 circles contains the 3 numbers x, y, and z (in any order), where x times y equals z.
1. Design data structures to represent the grid. (You do not necessarily have to encode how 3 circles are linked into a tile, or write a general algorithm that calculates it, but your design needs to be enough to support the two methods below.)
2. Write a method that determines whether two circles are adjacent. Two circles are adjacent if they appear immediately next to each other in the hexagonal grid. The circles do not need to be part of the same tile to be considered adjacent. (How you identify a particular circle is up to you and your design.)
3. Write a method that procedurally generates a grid that has the above properties A and B. The method should output 19 numbers and should determine the way they are laid out. Can you efficiently generate a variety of results, in a way that guarantees there is only 1 circle left over?
4. Please comment your code. Your code comments should include a description the process you followed, which reference sources you used, if any, and how much time you spent on the exercise. Note that clarity, maintainability, and testability will be considered when evaluating your solution.
```
### Language/Tools: Swift,SwiftUI 

## AdobeHexagonalKit Framework
##### Note: currenlty added in same code base as a seprate module but if needed we can move this to Framework/Library for reuse in different Application. also added  @objc for use this framework in Objective-C Code.


### Write a method that determines whether two circles are adjacent. Two circles are adjacent if they appear immediately next to each other in the hexagonal grid. The circles do not need to be part of the same tile to be considered adjacent. (How you identify a particular circle is up to you and your design.)
```
 func isAdjacent(_ circel1:HexCircle, _ circel2:HexCircle, _ grid:[[HexCircle]]) -> Bool
```

### Input: 
##### Two circles 

### Output: 
##### return true if two circles are adjacent if they appear immediately next to each other in the hexagonal grid. The circles do not need to be part of the same tile to be considered adjacent. 

###Algorithm :
##### Time Complexity : O(n). Space Complexity : O(1). Iterate though grid and find first circle (will take O(n)). check all six adjacent circle and compare with Circle2 if match return true else return false. 

### Example: 

```
let isAdjacent = AdobeHexagonalKit.shared.isAdjacent(circle1,circle2)
print(isAdjacent)

```

### Write a method that procedurally generates a grid that has the above properties A and B. The method should output 19 numbers and should determine the way they are laid out. Can you efficiently generate a variety of results, in a way that guarantees there is only 1 circle left over?
```
func findAdjacentCircles(_ circles : [HexCircle]) -> [[HexCircle]]
func generateGrids(_ tiles :  [[HexCircle]]) -> [[[HexCircle]]]
```

### Input: 
##### findAdjacentCircles : array of circles. generateGrids : array of circles array(array of tiles)

### Output: 
##### findAdjacentCircles will return array of circles that has the above properties A and B.  generateGrids will return array of tiles that generate a variety of results, in a way that guarantees there is only 1 circle left over.

###Algorithm :
#### findAdjacentCircles 
##### Time Complexity : O(n^2). Space Complexity : O(n). 

### Example: 

```
let isAdjacent = AdobeHexagonalKit.shared.isAdjacent(circle1,circle2)
print(isAdjacent)

```
