# array 
## Objective
1. Quick to review basic concepts of array.
2. Learn some basic usage of array in PHP.

## Declaration
Array in PHP can be declared in either way:

    new Array
or    
      
    []

The shorthand of new Array is
    
    [] 
    
 ## Key Value pair 
 
 At declaration, to put the key and value in PHP, one can either 
        
        just assign the value,
        
  or 
        
        assign the key and value together.
   
  For more understanding, see the example and its explanation in Example section.
  
 ## Example
 ### Example 1
 #### Example Code
    
        new Array(
            'a1' => 1,
            'a2' => 2,
            'a3' => 3
        );
#### Explanation of Example Code
The array contains 3 elems.

    0th elem: 'a1' is the key and the corresponding value is 1.
    1th elem: 'a2' is the key and the corresponding value is 2.
    2th elem: 'a3' is the key and the corresponding value is 3.
    
 ### Example 2   
 #### Example Code
    
        new Array(
            1 => 1,
            2 => -1,
            3 => 3,
            4 => 6
        );
#### Explanation of Example Code
The array contains 3 elems.

    0th elem: 1 is the key and the corresponding value is 1.
    1th elem: 2 is the key and the corresponding value is -1.
    2th elem: 3 is the key and the corresponding value is 3.
    3th elem: 4 is the key and the corresponding value is -6.

 
 
