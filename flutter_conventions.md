# Avoid using as instead, use is operator
Usually, The as cast operator throws an exception if the cast is not possible. To avoid an exception being thrown, one can use is.

``` js
//Don't
(item as Animal).name = 'Lion';


//Do
if (item is Animal)
  item.name = 'Lion';
```

# Use Cascades Operator
If we want to perform a sequence of operations on the same object then we should use the Cascades(..) operator.
```
// Don't
var path = Path();
path.lineTo(0, size.height);
path.lineTo(size.width, size.height);
path.lineTo(size.width, 0);
path.close();  


// Do
var path = Path()
..lineTo(0, size.height)
..lineTo(size.width, size.height)
..lineTo(size.width, 0)
..close(); 

```
