# pre tag in PHP.
## meaning

    " <pre> " refers the text for output will be prefixed.
    
    That is to say, the format for text of output will NEVER be changed.
    
For example,

the original format of print_r() function looks like this.
    
    Array
    (
        [0] => 1
        [1] => 2
        [2] => 3
    )
    
 However, if you simply display it with print_r() function, it will display like this.
    
    Array ( [0] => 1 [1] => 2 [2] => 3 )
    
 To preserve the format when displaying, the function for display must be enclosed in pre tag.
 
 ## Examples.
 Consider these codes as examples.
 
 ### pre_tag_php_1.php
 #### Code
 <?php
$arr = array(1, 2, 3);

echo '<pre>';
print_r($arr);
echo '</pre>';

print_r($arr);
?>

#### Output
Array
(
    [0] => 1
    [1] => 2
    [2] => 3
)
Array ( [0] => 1 [1] => 2 [2] => 3 )
### pre_tag_php_2.php
#### Code

<?php
$arr = array(1, 2, 3);

echo $arr;

echo "<br>";

echo "<br>";

echo "<br>";

echo "<br>";

print_r($arr);
?>
</pre>
 
#### Output

Array



Array
(
    [0] => 1
    [1] => 2
    [2] => 3
)

#### pre_tag_php_3.php
#### Code
<?php
$arr = array(1, 2, 3);

echo $arr;

echo "<br>";

echo "<br>";

echo "<br>";

echo "<br>";

print_r($arr);
?>
#### Output
Array



Array ( [0] => 1 [1] => 2 [2] => 3 )
    
# Ref

The answers in stackoverflow.

https://stackoverflow.com/questions/4756842/what-does-php-echo-pre-echo-pre-mean

The examples in this PHP tutorial.

https://www.php.net/manual/en/function.print-r.php
