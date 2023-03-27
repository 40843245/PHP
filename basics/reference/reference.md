# Reference 
## Intro
What is reference?

Reference of a variable refers a variable.

## Examples
Consider these codes as examples.

### Code
<?php
$foo = 'Bob';              // Assign the value 'Bob' to $foo
$bar = &$foo;              // Reference $foo via $bar.

echo $bar;
echo "<br>";
echo $foo;                 // $foo is altered too.
echo "<br>";

$bar = "My name is $bar";  // Alter $bar...
echo "After changing.";
echo "<br>";

echo $bar;
echo "<br>";
echo $foo;                 // $foo is altered too.
echo "<br>";
?>

### Output
Bob
Bob
After changing.
My name is Bob
My name is Bob
