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

``` js
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

# Don’t create a lambda when a tear-off will do
If we have a function that invokes a method with the same arguments as are passed to it, you don’t need to manually wrap the call in a lambda.

``` js 
List<String> names=[]
  
// Don’t
names.forEach((name) {
  print(name);
});


// Do
names.forEach(print);
```

# Use ListView.builder for a long list
When working with infinite lists or very large lists, it’s usually advisable to use a ListView builder in order to improve performance.

Default ListView constructor builds the whole list at once. ListView.builder creates a lazy list and when the user is scrolling down the list, Flutter builds widgets on-demand.


