
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

## AdobeHexagonalKit Framework

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



### RectangleKit written in Swift.

#### Function Defination 

```
//asynchronous call and run in background
public func rotatingRectangles(_ arrRects:[CGRect], _ completion:@escaping ([CGRect]) -> Void){
```

```
//synchronous call and run in same thread as caller 
public func rotatingRectangles(_ arrRects:[CGRect]) -> [CGRect] {
```

### Example: 

```
let arrInputRects = [CGRect.init(x: 0, y: 0, width: 20, height: 50),
                    CGRect.init(x: 20, y: 0, width: 30, height: 30),
                    CGRect.init(x: 50, y: 0, width: 20, height: 40)]
                    
let arrOutputRects = RectangleKit.shared.rotatingRectangles(arrInputRects)
                
RectangleKit.shared.rotatingRectangles(arrInputRects, {(arr) in
                self.arrOutputRects = arr
      print(arr)
})                
```

### Error Delegate

#### Error Delegate will call closure with error details in DEBUG MODE only 

#### Function Defination 

```
public func setDebugDelegate(_ completion: @escaping (Error) -> Void) {
```

### Example: 
```
RectangleKit.shared.setDebugDelegate({(error) in
            print(error)
        })
```        
        




# RectangleKitDemo Application 

##### Test application that uses RectangleKit. The application creates the input list (generated randomly), sends this list to RectangleKit to do the calculations, and then shows the output list of rectangle. The application should graphically display the input and output lists. The test application written in Swift, and use SwiftUI to display the list of rectangles graphically.


#### Two Navigation bar buttons for Dummy Data:
 
#### 1. "Random Input" button :  
##### => creates the input list of CGRect (generated randomly). Method name "HomeViewModel"->"randomRectsInput" 
##### => Method name "HomeViewModel"->"randomRectsInput" 
##### => Random Number of Rantangle 1..<15
##### => Random width 10..<50
##### => Random height 10..<150

#### 2. "Select Input" button :  
##### => Read the input list from the local dummy "mock.josn" file  
##### => Method name "HomeViewModel"->"fetchDummyData" 
##### => In Dummy Input from "mock.json" last Input is Invalid input to test Error Handler and will return empty output array.

  

# RectangleKit Code Files

```
# RectangleKit.swift:  Main file with public methods and Algorithm logic. 
    - Time Complecity O(n) - where n = Number of Rectangle in Input array
    - Space complecity O(n) in worst case, best case : O(1)
# RectangleKitStack.swift: Created custom stack for keep height and index of the rectangle. 
  used stack instead of Array for Push and Pop in O(1) time.    
# RectangleKitErrorType.swift : Defined different Error types. 

```

# RectangleKitDemo Code Files

```
# ContentView.swift:Main View File 
# HomeViewModel.swift: View Model class for Main View
# Rentangle.swift: Model file for Main View Dummy Data.
# "Utilities" Group for Defined different Error types. 
# "Network" Group for Network call, for now used for read mock.json dummy data file. 
   but we can easly change to server URL if needed in future. 
```

# Build and run the code 

```
# Open "RectangleKitDemo.xcodeproj" 
# Build and run the Demo App. and it will auto build RectangleKit framework. 
# RectangleKitDemo Application included RectangleKit Reference and In build dependency. 

```


# Make it universal framework

```
# Option 1 : Build XCFramework (universal) framework
# Option 2 : Add a “Run Script” which generates the Universal Framework.
Select Project Target → Edit Schema → Archive → Post-actions → Press “+” → New Run Script Action.

```


# Assumption:

```
# Assumed that output figure is included all ractangles and not only vertical rectangle.
# Base on given output figure#2 and figure#4, It's not clear that, 
it's drawn on top of Input figure or need to return all rectangles 
including small rectangles created after add vertical rectangles.

```
