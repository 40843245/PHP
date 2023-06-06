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
        
        just specify the value, NOT specify the key and the key will be assumed.
        
  or 
        
        specify the key and value together.
 
 If the key is NOT specified, then the key is assumed to 1 plus the maximum number of the previous keys (including the keys that are assumed). 
 
 For more details, see Example 4 to 6.
 
 If the key in 0th elem is NOT specified then it will assumed to 0 (here NO any previous keys can be referenced.).
 
 Like array in C++, it starts at the index 0.
 
 For more details, see Example 4 to 6.
 
 For more understanding, see the example and its explanation in Example section.
  
 ## Type of key
 
 The key of array in PHP is special than in C++.
 
 In PHP, a key of an array can be one of the following:
 
        1. number (integer,float number, double number, decimal number etc).
        
        2. string (Does it occur in PHP? Yes.)
        
        3. boolean (Does it occur in PHP? Yes.)
        
        4. null (Does it occur in PHP? Yes.)
 
 However, the key will be implicitly casted in special case. See the below section.
 
 
 In PHP, a key of an array can NOT be one of the following:
 
        1. array
        
        2. class
  
  ## Key with implicit cast.
  
  1. boolean : 
            
            value of true will actually implictly cast to 1.
            
            value of false will actually implictly cast to 0.
  
  2. float :
  
            The float will implictly cast to int (i.e. the float will be truncated.).
            
  3. string : 
  
            The string that can only contain valid decimal integer. (i.e. a number converts to the string.). The string will be parsed to a number.
            Such as 
            $array['1']
            ,
            $array['1.5']
            or
            $array['-1']
            
4. null :

            The null will implicitly casted to empty string.
            i.e.
            They are equivalent.
            $x = null; $array[$x] = 2 ;
            and 
            $y = ''; $array[$y] = 2; 

  ![image](https://github.com/40843245/PHP/assets/75050655/3d4c2fe2-80cc-4100-8db9-4aadf7ca8444)

 ## Change or Insert an element in array in PHP
 
 In PHP, it is easy to change or insert an element in array.
 
 Just assign it like a variable. Such as
    
    $array['123'] 
 
 ## Multiple keys in same array
 The value in the previous elem will be overwritten if the key is store under previous key (i.e. the previous key can implicitly cast to the current or vice versa.)
 
 Or exactly to say, 
        
        If multiple elements in the array declaration use the same key, only the last one will be used as all others are overwritten.
 
 Such as
    
 
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
The array contains 4 elems.

    0th elem: 1 is the key and the corresponding value is 1.
    1th elem: 2 is the key and the corresponding value is -1.
    2th elem: 3 is the key and the corresponding value is 3.
    3th elem: 4 is the key and the corresponding value is -6.
    
 ### Example 3
 #### Example Code
    
        new Array(
            1 => 1,
            2 => -1,
            3 => 3,
                 6
        );
#### Explanation of Example Code
The array contains 4 elems.

    0th elem: 1 is the key and the corresponding value is 1.
    1th elem: 2 is the key and the corresponding value is -1.
    2th elem: 3 is the key and the corresponding value is 3.
    3th elem: 4 is the key and the corresponding value is -6.
  
 ### Example 4
 #### Example Code
    
        new Array(
            1 =>  1,
            2 => -1,
                  3,
            15 => 6,
                   7
        );
#### Explanation of Example Code
The array contains 5 elems.

    0th elem: 1 is the key and the corresponding value is 1.
    1th elem: 2 is the key and the corresponding value is -1.
    2th elem: 3 is the key and the corresponding value is 3.
    3th elem: 15 is the key and the corresponding value is 6.
    4th elem: 16 is the key and the corresponding value is 7.
    
 ### Example 5
 #### Example Code
    
        new Array(
                  1,
                 -1,
                  3,
            15 => 6,
                   7
        );
#### Explanation of Example Code
The array contains 5 elems.

    0th elem: 0 is the key and the corresponding value is 1.
    1th elem: 1 is the key and the corresponding value is -1.
    2th elem: 2 is the key and the corresponding value is 3.
    3th elem: 15 is the key and the corresponding value is 6.
    4th elem: 16 is the key and the corresponding value is 7.

 
 ### Example 6
 #### Example Code
    
        new Array(
                   1,
                   -1,
                  3,
                  6,
                   7
        );
#### Explanation of Example Code
The array contains 5 elems.

    0th elem: 0 is the key and the corresponding value is 1.
    1th elem: 1 is the key and the corresponding value is -1.
    2th elem: 2 is the key and the corresponding value is 3.
    3th elem: 3 is the key and the corresponding value is 6.
    4th elem: 4 is the key and the corresponding value is 7.
    
    
 ### Example 7
 #### Example Code
    
        $array = new Array(
                   1,
                   -1,
                  3,
                  6,
                   7
        );
        $array[10]='v1';
        $array['k1']='v2';
        
#### Explanation of Example Code
The array contains 7 elems.

    0th elem: 0 is the key and the corresponding value is 1.
    1th elem: 1 is the key and the corresponding value is -1.
    2th elem: 2 is the key and the corresponding value is 3.
    3th elem: 3 is the key and the corresponding value is 6.
    4th elem: 4 is the key and the corresponding value is 7.
    5th elem: 10 is the key and the corresponding value is 'v1'.
    6th elem: 'k1' is the key and the corresponding value is 'v2'.
    
    
 ### Example 8
 #### Example Code
    
        $array = new Array(
                   1,
                   -1,
                  3,
                  6,
                   7
        );
        $array[]='v1';
        $array[]='v2';
        
#### Explanation of Example Code
The array contains 7 elems.

    0th elem: 0 is the key and the corresponding value is 1.
    1th elem: 1 is the key and the corresponding value is -1.
    2th elem: 2 is the key and the corresponding value is 3.
    3th elem: 3 is the key and the corresponding value is 6.
    4th elem: 4 is the key and the corresponding value is 7.
    5th elem: 5 is the key and the corresponding value is 'v1'.
    6th elem: 6 is the key and the corresponding value is 'v2'.
    
### Example 9
 #### Example Code
    
        $array = new Array(
                   1,
                   -1,
                  3,
                  6,
                   7
        );
        $array[]='v1';
        $array[100]='v2'
        $array[]='v3';
        
#### Explanation of Example Code
The array contains 8 elems.

    0th elem: 0 is the key and the corresponding value is 1.
    1th elem: 1 is the key and the corresponding value is -1.
    2th elem: 2 is the key and the corresponding value is 3.
    3th elem: 3 is the key and the corresponding value is 6.
    4th elem: 4 is the key and the corresponding value is 7.
    5th elem: 5 is the key and the corresponding value is 'v1'.
    6th elem: 100 is the key and the corresponding value is 'v2'.
    7th elem: 101 is the key and the corresponding value is 'v3'.

### Example 9
 #### Example Code
    
        $array = new Array(
                   1,
                   -1,
                  3,
                  6,
                   7
        );
        $array[]='v1';
        $array[100]='v2'
        $array[]='v3';
        
#### Explanation of Example Code
The array contains 8 elems.

    0th elem: 0 is the key and the corresponding value is 1.
    1th elem: 1 is the key and the corresponding value is -1.
    2th elem: 2 is the key and the corresponding value is 3.
    3th elem: 3 is the key and the corresponding value is 6.
    4th elem: 4 is the key and the corresponding value is 7.
    5th elem: 5 is the key and the corresponding value is 'v1'.
    6th elem: 100 is the key and the corresponding value is 'v2'.
    7th elem: 101 is the key and the corresponding value is 'v3'.
    
    
 ### Example 10
 #### Example Code
    
       
    $array = array(
    1    => "a",
    "1"  => "b",
    1.5  => "c",
    true => "d",
        );
        var_dump($array);
?>
        
#### Explanation of Example Code
The array contains 1 elems.

    0th elem: 1 is the key and the corresponding value is "d".
 
The output will be

    array(1) {
    [1]=>
    string(1) "d"
        }
        
 The reason why it is the value with the key "1" will be overwritten as "1" contain integer,  the value with the key 1.5 as 1.5 can be truncated to 1, and the value the key true will be overwritten as true can implicity cast to 1.
 
 
 ![image](https://github.com/40843245/PHP/assets/75050655/56495196-a11d-4fc1-bb71-b50e2d64db57)

