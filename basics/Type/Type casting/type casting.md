# type casting
## Cast to string
There are two ways.

### method 1:
         $s= (string) $foo;
### method 2:
         $s = "$foo";

## NOTE
1. About alias of type.

         (integer) is an alias of the (int) cast. 
         (boolean) is an alias of the (bool) cast. 
         (binary) is an alias of the (string) cast. 
         (double) and (real) are aliases of the (float) cast. 

         These casts do not use the canonical type name and are not recommended.
## Waring
1. The (real) cast alias has been deprecated as of PHP 8.0.0.

2. The (unset) cast has been deprecated as of PHP 7.2.0. 

Note that the (unset) cast is the same as assigning the value NULL to the variable or call. 

3. The (unset) cast is removed as of PHP 8.0.0.
## Caution
1. The (binary) cast and b prefix exists for forward support. 

Currently (binary) and (string) are identical, however this may change and should not be relied upon.

## Ref

### Comparison of type casting.
https://www.php.net/manual/en/types.comparisons.php
