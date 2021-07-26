
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

### Algorithm :
##### Time Complexity : O(n). Space Complexity : O(1). Iterate though grid and find first circle (will take O(n)). check all six adjacent circle and compare with Circle2 if match return true else return false. 

### Example: 

```
let isAdjacent = AdobeHexagonalKit.shared.isAdjacent(circle1,circle2)
print(isAdjacent)

```

### Write a method that procedurally generates a grid that has the above properties A and B. The method should output 19 numbers and should determine the way they are laid out. Can you efficiently generate a variety of results, in a way that guarantees there is only 1 circle left over?

#### findAdjacentCircles
```
func findAdjacentCircles(_ circles : [HexCircle]) -> [[HexCircle]]

```

### Input: 
##### findAdjacentCircles : array of circles.

### Output: 
##### findAdjacentCircles will return array of circles that has the above properties A and B.  

### Algorithm :
#### findAdjacentCircles 
##### Time Complexity : O(n^2). Space Complexity : O(n). 
##### For avoid O(n^3) keeping dictinary for all numbers in array(will allow constant time lookup) and Iterate for other two number product. will check if product exist in dictinary. if exist all three Circle will add in Output array. and set that particular index as visited = true to avoid reuse it.  

### Example: 

```
let tiles = AdobeHexagonalKit.shared.findAdjacentCircles(circles)

```

#### generateGrids

```
func generateGrids(_ tiles :  [[HexCircle]]) -> [[[HexCircle]]]
```


### Input: 
##### generateGrids : array of circles array(array of tiles)

### Output: 
##### generateGrids will return array of tiles that generate a variety of results, in a way that guarantees there is only 1 circle left over.

#### generateGrids 
##### Time Complexity : O(6^n). Space Complexity : O(1). 
##### Using DFS. for Each Circle there will be six option to put as adjacent circle(left, right, top-left,top-right, bottom-left, bottom-right). for generate a variety of results checking all possible combination and genrating new Grid. it will add to output array when there is no more tile in tiles array.   

### Example: 

```
let grids = AdobeHexagonalKit.shared.generateGrids(tiles)
```

### Error Handling

#### for now Errors are printed in log. we can update base on requirement and show to user as needed. 



### Assumption/Notes

#### Assumed that input with valid 19 Circles. that can can be divided into 6 tiles of 3 adjacent circles (with 1 circle left over).
#### If valid # of circles < 19, it will return empty tiles and empty grid.
#### if valid # of circles > 19, it will take valid 19 circles and return 6 tiles of 3 adjacent circles and 1 tile of 1 circle.
#### we can udpate this logic base on requirement after discussed with the team.


