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


