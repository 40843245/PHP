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
  ## Change or Insert an element with null key in array in PHP
  1 plus The largest number of all previous keys will be the current key if the key is specified like this.
  
    $array[] = 1;
  
 For more details, see Example 14.
 
 ## Multiple keys in same array
 The value in the previous elem will be overwritten if the key is store under previous key (i.e. the previous key can implicitly cast to the current or vice versa.)
 
 Or exactly to say, 
        
        If multiple elements in the array declaration use the same key, only the last one will be used as all others are overwritten.
 
 Such as
   
## Unpacking 
It is easy to unpack the array into many variables.
Just use [], such as
        
        $array= [1,2,3];
        [$x,$y,$z]=$array;
## Swapping
It is possible to swap two variables with packing and unpacking. It just hold one statement.

For more details, see Example 13.


 ## NOTICE
Here are several tips that we have to pay lots of attention on them. Although I mentioned most of them in other parts of this article, I want to tip them.

Some of tips are NOT mentioned in PHP docs.

1. The shorthand of new Array is [].
2. To change the value of key and insert a new key after declaration, just assign it.
3. To remove the key after declaration, use the unset function.
4. The array starts at index 0.
5. If the key is NOT specified at declaration, the key will be assumed to 1 plus the max number of previous keys.
6. If key at the index 0 is NOT specified, the key will be assumed to 0.
7. Notice about implicit cast for keys. Mentioned on above section.
8. PHP arrays can contain int and string keys at the same time as PHP does not distinguish between indexed and associative arrays.
9. If multiple elements in the array declaration use the same key, only the last one will be used as all others are overwritten.
10. The comma after the last array element is optional and can be omitted.
11. The spread operator (...) is not supported in assignments.
![image](https://github.com/40843245/PHP/assets/75050655/eb370460-d149-4fa6-82c7-40ee69204d85)

8. If no key is specified, the maximum of the existing int indices is taken, and the new key will be that maximum value plus 1 (but at least 0). If no int indices exist yet, the key will be 0 (zero).

9. The maximum integer key used for this need not currently exist in the array. It need only have existed in the array at some time since the last time the array was re-indexed. 

![image](https://github.com/40843245/PHP/assets/75050655/6de9223a-fec1-43cb-981f-3db8794106d7)


## NOTICE in different version
1. As of PHP 7.1.0, applying the empty index operator on a string throws a fatal error. Formerly, the string was silently converted to an array.

![image](https://github.com/40843245/PHP/assets/75050655/baa5de0a-673b-4747-b5c0-0bbd6b2232fb)

2. Prior to PHP 8.0.0, square brackets and curly braces could be used interchangeably for accessing array elements (e.g. $array[42] and $array{42} would both do the same thing in the example above). The curly brace syntax was deprecated as of PHP 7.4.0 and no longer supported as of PHP 8.0.0. Illustrated in the following figure.

![image](https://github.com/40843245/PHP/assets/75050655/1e31fed7-eca1-4e69-abd2-c81452ef31fc)

3. As of PHP 8.1.0, creating a new array from false value is deprecated. 
4. Creating a new array from null and undefined values is still allowed.
 
![image](https://github.com/40843245/PHP/assets/75050655/7c96d1f6-22f2-454d-b5fc-96e629f37dff)

5. After PHP 8.0.0, attempting to access an array key which has not been defined is the same as accessing any other undefined variable: an E_WARNING-level error message will be issued (Prior to PHP 8.0.0, E_NOTICE-level message will be issued) , and thus the result will be null.

![image](https://github.com/40843245/PHP/assets/75050655/112108ab-4c21-4df7-8753-84167dcf6b05)

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

        
#### Explanation of Example Code
The array contains 1 elems.

    0th elem: 1 is the key and the corresponding value is "d".
 
The output will be

    array(1) {
    [1]=>
    string(1) "d"
        }
        
 The reason why it is the value with the key "1" will be overwritten as "1" contain integer,  the value with the key 1.5 as 1.5 can be truncated to 1, and the value the key true will be overwritten as true can implicity cast to 1.
 
  ### Example 11
 #### Example Code     
    $array = array(
    "foo" => "bar",
    "bar" => "foo",
    100   => -100,
    -100  => 100,
);
        
#### Explanation of Example Code

Here is an example to illustrate the fact that
        
        PHP arrays can contain int and string keys at the same time as PHP does not distinguish between indexed and associative arrays.
The array contains 1 elems.

    0th elem: 1 is the key and the corresponding value is "d".
 
The output will be

    array(4) {
    ["foo"]=>
    string(3) "bar"
    ["bar"]=>
    string(3) "foo"
    [100]=>
    int(-100)
    [-100]=>
    int(100)
    }
        

var_dump($array); 
 ![image](https://github.com/40843245/PHP/assets/75050655/56495196-a11d-4fc1-bb71-b50e2d64db57)

### Example 12
 #### Example Code     
        $source_array = ['foo' => 1, 'bar' => 2, 'baz' => 3];
        ['baz' => $three] = $source_array;
        echo $three;   
        echo "\n";
        
        $source_array = ['foo', 'bar', 'baz'];
        [2 => $baz] = $source_array;
        echo $baz;
        echo "\n";
        
#### Explanation of Example Code

Here is an example to illustrate unpacking in array.
        
It should output (in Windows environment, slightly difference in Docker container)
    
        3 
        "baz"
        
 ### Example 13
 #### Example Code     
        $a = 1;
        $b = 2;

        echo "Before";  
        echo "\n";
        echo $a;   
        echo "\n";
        echo $b;  
        echo "\n";
        
        [$b, $a] = [$a, $b];

        echo "After";  
        echo "\n";
        echo $a;   
        echo "\n";
        echo $b;  
        echo "\n";
        
#### Explanation of Example Code

Here is an example to illustrate unpacking in array.
        
It should output (in Windows environment, slightly difference in Docker container)
    
        "Before"
        1
        2
        "After"
        2
        1
        
### Example 14
 #### Example Code     
    // Create a simple array.
    $array = array(1, 2, 3, 4, 5);
    print_r($array);

    // Now delete every item, but leave the array itself intact:
    foreach ($array as $i => $value) {
        unset($array[$i]);
    }
    print_r($array);

    // Append an item (note that the new key is 5, instead of 0).
    $array[] = 6;
    print_r($array);

    // Re-index:
    $array = array_values($array);
    $array[] = 7;
    print_r($array);
        
#### Explanation of Example Code
The output should be
    
     Array
    (
        [0] => 1
        [1] => 2
        [2] => 3
        [3] => 4
        [4] => 5
    )
    Array
    (
    )
    Array
    (
        [5] => 6
    )
    Array
    (
        [0] => 6
        [1] => 7
    )
    
        
        
## Ref
PHP official docs.
https://www.php.net/manual/en/language.types.array.php

## Advanced Reading

Get all instance of a class with array.

![image](https://github.com/40843245/PHP/assets/75050655/2f83df23-cfb7-4ef3-8dc6-a4c018f5a52d)


https://stackoverflow.com/questions/475569/get-all-instances-of-a-class-in-php
