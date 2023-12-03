# basics of flutter

```dart
void main(){
    runApp(MyApp());
}
```

The above snippet represents where the code is going to start. The `runApp()` function takes a widget as an argument. In this case, the widget is `MyApp()`. The `MyApp()` widget is a class that extends the `StatelessWidget` class. The `StatelessWidget` class is a class that is used to create widgets that do not change. The `MyApp()` widget is the root widget of the application. The `MyApp()` widget is the parent of all the other widgets in the application. The `MyApp()` widget is the widget that is passed to the `runApp()` function.

```dart
class MyApp extends StatelessWidget{
    @override
    Widget build(BuildContext context){
        return MaterialApp( title: 'MyApp',
            home: Scaffold(),
        );
    }
}
```

# WIDGETS
- __Scaffold()__.
***

The scaffold widget is a skeleton, it s a blank canvas and will hold the other components.
In the scaffold , we can change the background color:

```dart
Scaffold(
    backgroundColor: Colors.blueGrey,
)
```

- __Container()__.
***
Its a flexible widget.

```dart
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        body: Container(
          height: 400,
          width: 400,
          color: Colors.white,
        )
      ),
    );
  }
```

The Container widget above will create a white shape of the specified length and width.
It can also be wrapped in another container called __center__, it center it.

```dart
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        body: Center(
          child: Container(
            height: 400,
            width: 400,
            color: Colors.white,
          ),
        ),
      ),
    );
  }
```

- __Padding()__.
***
The padding widget is used to add padding to the widget it wraps.

```dart
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        body: Center(
          child: Container(
            height: 400,
            width: 400,
            color: Colors.white,
            child: Padding(
              padding: EdgeInsets.all(20),
              child: Text('Hello'),
            ),
          ),
        ),
      ),
    );
  }
```
Here padding is apllied all around the text. You can specify padding on one direction, for example, `padding: EdgeInsets.only(left: 20),` will add padding to the left of the text only.

```dart
decoration: BoxDecoration(),
```
### Bold text and padding
```dart
padding: const EdgeInsets.all(25),
            child: const Text(
              'Hello World, this is mankindjnr',
              style: TextStyle(
                color: Colors.white,
                fontSize: 28,
                fontWeight: FontWeight.bold,
              ),
```

### Adding an icon
I cons in flutter are built in, the home icon, love icon are there by default.

```dart
padding: EdgeInsets.all(25),
child: Icon(
  Icons.home,
  color: Colors.white,
  size: 64,
)
```

```dart
padding: EdgeInsets.all(25),
child: Icon(
  Icons.favorite,
  color: Colors.red,
  size: 64,
)
```

```dart
padding: EdgeInsets.all(25),
child: Icon(
  Icons.favorite,
  color: Colors.red,
  size: 64,
)
```

All this time we had been using the body of the scaffold, we can also use the appBar.
## SCAFFOLD | BODY

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        body: Center(
          child: Container(
            height: 300,
            width: 300,
            decoration: BoxDecoration(
              color: Colors.red,
              borderRadius: BorderRadius.circular(20),
            ),
            padding: const EdgeInsets.all(25),
            child: const Icon(
              Icons.favorite,
              color: Colors.white,
              size: 64,
            ),
          ),
        ),
      ),
    );
  }
}
```
### Icons
![icons](./output/bodyicons.png)

## SCAFFOLD | APPBAR

The `AppBar` comes on top of the scaffold, it is the topmost widget.

```dart
appBar: AppBar(
  title: Text('I am the appbar'),
),
body: Center(),
```

```dart
        backgroundColor: Colors.blueGrey,
        appBar: AppBar(
          title: const Text("mankindjnr alias"),
          backgroundColor: Colors.blueGrey[900],
          elevation: 0.0,
          leading: const Icon(Icons.menu),
          actions: [
            IconButton(
              onPressed: () {},
            icon: const Icon(Icons.search),
            //icon: const Icon(Icons.logout),
            ),
          ],
        ),
```
### AppBar
![appBar](./output/appbaricon.png)

### Column | Body
```dart
body: Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: [
    const Text(
      'Hello World, this is mankindjnr',
      style: TextStyle(
        color: Colors.white,
        fontSize: 28,
        fontWeight: FontWeight.bold,
      ),
    ),
    const SizedBox(height: 20),
    const Icon(
      Icons.favorite,
      color: Colors.red,
      size: 64,
    ),
  ],
),
```

