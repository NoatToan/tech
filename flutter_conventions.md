# Avoid using as instead, use is operator
Usually, The as cast operator throws an exception if the cast is not possible. To avoid an exception being thrown, one can use is.

``` flutter
//Don't
(item as Animal).name = 'Lion';


//Do
if (item is Animal)
  item.name = 'Lion';
```
