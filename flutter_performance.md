https://itnext.io/flutter-performance-tips-4580b2491da8
# Briefly Explanied — How Flutter framework optimizes widget rendering?

In Flutter docs it is explained build method can be called many times by framework and it is recomended that we should only return widgets through the build method. But even we return only widgets, isn't it causing some performance issues? If build method is called 20 times in a second, does not it mean widgets will be rendered 20 times and should not it be slow? If Flutter framework optimizes rendering widgets, how?

## Answer
 Flutter framework is trying to reuse the objects as much as it can. Even the Widget Tree is changed a lot over time, Element Tree is not changed a lot same as the Widget Tree and use the same element object if the widget type is not changed.

Widget Tree is hierarchy of widgets and includes all the widgets created. But since widgets are immutable and changed in the tree over time, there should be another tree called Element Tree which keeps the states and optimizes widget rendering.

Element Tree is the tree which Flutter uses to render widgets on the screen and is not changed a lot over time same as Widget Tree because whenever a widget is changed in the Widget Tree, if the new widget has the same type as before, element tree keeps the element for the corresponding widget. For example if you only change a Text widget's text in the widget tree, Widget Tree is going to be changed but Element Tree is going to stay same because Text widget still has the same runtimeType as before.

So that render optimization is mostly about reusability. Flutter framework is trying to reuse the objects as much as it can. Even the Widget Tree is changed a lot over time, Element Tree is not changed a lot same as the Widget Tree and use the same element object if the widget type is not changed.
=> Widget rebuild và sẽ dc map vào state element => performance nó tốt. 


https://www.youtube.com/watch?v=AqCMFXEmf3w
https://www.youtube.com/watch?v=996ZgFRENMs&feature=youtu.be
https://stackoverflow.com/questions/71189689/how-flutter-framework-optimizes-the-widget-rendering-if-build-method-can-be-call


https://stackoverflow.com/questions/53234825/what-is-the-difference-between-functions-and-classes-to-create-reusable-widgets

# Use const constructors whenever possible
``` js
class CustomWidget extends StatelessWidget {
  const CustomWidget();
  @override
  Widget build(BuildContext context) {
    ...
  }
}
```
Short Explanation
When building your own widgets, or using Flutter widgets. This helps Flutter to rebuild only widgets that should be updated.

# Use nil instead const Container()
// good
text != null ? Text(text) : const Container()
// Better
text != null ? Text(text) : const SizedBox()
// BEST
text != null ? Text(text) : nil
or
if (text != null) Text(text)
Short Explanation
It’s just a basic Element Widget that does and costs almost nothing. 
https://pub.dev/packages/nil


#. Use itemExtent in ListView for long Lists
Short Explanation
That helps Flutter to calculate ListView scroll position instead of calculating the height of every widget and make scroll animation much more performant

# 9. Accelerate Flutter performance with Keys
// FROM
return value
  ? const SizedBox()
  : const Placeholder(),
// TO
return value
  ? const SizedBox(key: ValueKey('SizedBox'))
  : const Placeholder(key: ValueKey('Placeholder')),
----------------------------------------------
// FROM
final inner = SizedBox();
return value ? SizedBox(child: inner) : inner,
// TO
final global = GlobalKey();
final inner = SizedBox(key: global);
return value ? SizedBox(child: inner) : inner,
Short Explanation
Flutter recognizes Widgets better when using keys. This gives us better performance up to 4x

Caution

ValueKey can make your code look a bit bloat
GlobalKey is a bit dangerous but sometimes it’s worth it.

# 10. Optimize memory when using image ListView
ListView.builder(
  ...
  addAutomaticKeepAlives: false (true by default)
  addRepaintBoundaries: false (true by default)
);
Short Explanation
ListView couldn’t kill its the children are not being visible to the screen. It causes consume a lot of memory if children have high-resolution images.

By doing these options false, could lead to use of more GPU and CPU work, but it could solve our memory issue and you will get a very performant view without noticeable issues.


# 11. [Ignore Rebuilding of Widget in AnimatedBuilder.](https://medium.com/@ashwinmali32/flutter-performance-optimization-tips-74cf76e0a505)
→ Animation is one of the most attractive features in any web or mobile application. It grabs the user’s attention, but at the same time, it decreases the performance of the application.

→ Developers generally use AnimationController. However, it rebuilds multiple widgets in AnimatedBuilder, and that’s the common reason behind the slow Flutter performance.

→ To avoid bad performance issues, you can use CounterWidget, which helps develop animation without rebuilding multiple widgets.

#12 [Load list items efficiently — and on-demand](https://medium.com/@ashwinmali32/flutter-performance-optimization-tips-74cf76e0a505)
→ When working with list items, developers generally use a combination of the widgets SingleChildScrollView and Column.

→ When working with large lists, things can get messy pretty quickly if you continue using this same set of widgets. This is because each item is attached to the list and then rendered on the screen, which increases the overall load on the system.

→ It is a good idea to use the ListView builder in such cases. This improves performance on a very high level. Let’s look at an example for a builder object:


```js

ListView.builder(
itemCount: items.length,
itemBuilder: (context, index) {
return ListTile(
title: Text('Row: ${items[index]}'),
);},);
```

#13 [obfuscate](https://medium.com/@ashwinmali32/flutter-performance-optimization-tips-74cf76e0a505)

→ The command to generate an app bundle is:

flutter build appbundle
→ To obfuscate the Dart language code, you need to use obfuscate and the — split-debug-info flag with the build command. The command looks like this:

flutter build apk - obfuscate - split-debug-info=/<project-name>/<directory>
The above command generates a symbol mapping file. This file is useful to de-obfuscate stack traces.

