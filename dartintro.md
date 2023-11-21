# DART
```dart
import 'dart:io';

void main(){
    print("Hello cross platform");
}
```

## Variables
use camelcase to name your variables.

### Declare Variables
```dart
var name = "John";
String name = "John";

int x = 21;
var x = 32;

// dynamic varaibles are used when you not sure of the data type
dynamic firstName = "Tim"

const String fullName = "Amos Njoroge";
final String nickName = "mankindjnr";

//decalre and not use
var myname;

//assign later
myname = "njoroge";
```
When it comes to declaring variables, you can use the __var__ keyword or use the data type of the variable to declare it.

__final/const__
If you know what it will be at runtime use a __final__
if you know what it will be at compile time use a __const__

## Data types
```dart
String
int
double
bool
dynamic
Lists
Maps
```

```dart
String firstName = "Amos";
print("String: $firstName")

```

### LISTS
```dart
void main(){
    List mylist = [1,2,3,4];
    print(mylist);
    print(mylist[0]);

    //change an item
    mylist[0] = 43;

    //create an empty list
    var emptylist = [];
    print(emptylist);

    //add to an empty list
    emptylist.add(41);

    //add multiple elements to an empty lists
    emptylists.addAll(1,2,3);

    //insert to a specific position
    //mylist.insert(index, value)
    mylist.insert(3, 900);

    //insert many
    //mylist.insertAll(pos, [items to insert])
    mylist.insertAll(1, [99, 89, 89]);

    //Mixed data types list
    var mixedList = [1, 2, 3, "John", "Njoro"];

    // remove from list
    mixedList.remove("John"); //removes all johns

    // remove from specific location
    mixedList.removeAt(1)

}
```

### MAPS
```dart
void main(){
    // creating a map
    var toppings = {
        "Amos": "Cheese",
        "Njoro": "Peperoni"
    };
    print(toppings);
    print(toppings["Njoro"]);

    // print only the values of a map
    print(toppings.values);

    // show the keys of the map
    print(toppings.keys);

    // show length
    print(toppings.length);

    //add items
    toppings["mankindjnr"] = "sausage";
    print(toppings);

    // add mnany items
    toppings.addAll({"Tina":"Bacon", "Steve":"Supreme"});

    // remove item
    toppings.remove("steve");

    //remove every item
    toppings.clear();
}
```

## LOOPS
```dart
void main(){
    // for loop
    int num = 5;
    for (int i = num; i >= 1; i--){
        print(i);
    }

    // for in loop
    List names = ["John", "Tina", "Steve"];
    for (String name in names){
        print(name);
    }

    //while loop
    while (num >= 1){
        print(num);
        num--
    }
}
```

## LOGIC
```dart
void main(){
    int num = 5;
    if (num == 5){
        print("The number is 5");
    }
    else if(num == 3){
        print("num is 3")
    } else {
        print("The numbe is not 5, its $num")
    }
}
```

## Functions
```dart
void main(){
    myfunction(){
        return ("first function");
    }

    print(myfunction());

    var funcVaraible = myfunction()
}
```

```dart
void main(){
    myfunction(String fistname, secondname){
        return "Hello $firstname $secondname";
    }

    var function = myfuntion("Amos", "Njoroge")
    print(function)
}
```

### optional postional parameter
```dart
void main(){
    myfunction(String firstname, [secondname]){
        return "Hello $firstname $secondname";
    }
    var function = myfunction("Amos");
}
```
Here the __[secondname]__ is an optional postional parameter, when called without a value passed to it, it is assigned NULL.

### optional named parameters
```dart
void main(){
    myfunction(String firstname, {secondname}){
        return "Hello $firstname $secondname";
    }

    var function = myfunction("Amos", secondname:"Njoroge");
}
```
if no value is passed to the named parameter then it is assigned null.

### Default Parameter
```dart
void main(){
    myfunction(String firstname, {secondname:"Njoroge"}){
        return "Hello $firstname $secondname";
    }
    var function = myfunction("Amos");
}
```

When there is no value passed then the default value is used, but when the value is passed then that value is used instead of the default.

## USER INPUT
```dart
import 'dart:io';

void main(){
    print("Enter your nickname:" );
    var name = stdin.readLineSync();

    print("Hello $name");
}
```

## DATA TYPE CONVERSION
```dart
void main(){

    // string to int
    var a,b,c;

    a= 40;
    b = "1";
    c = a + int.parse(b);

    print("$a + $b = $c");

    //string to double
    d = "0.1";
    double_d = double.parse(d);

    //int to string
    g = 40;
    string_g = g.tostring()
}
```

## USER INPUT CONVERSION
```dart
import 'dart:io';

void main(){
    print("Enter a number: ")
    var num_input = stdin.readLineSync();

    var input2 = int.parse(num_input ?? '0')// this will allow the input to be converted since if the input is numm it is replaced with 0

}
```

## CLASSES
```dart
class Person{
    String? name, sex;
    int? age;

    //constructor
    Person(String name, sex, int age){
        this.name = name;
        this.sex = sex;
        this.age = age;
    }

    //methods
    void showData(){
        print("Name = $name");
        print("Sex = $sex");
        print("Age = $age");

    }
}
void main(){
    //create a person class
    Person one = Person("Amos", "Man", 23);
    one.showData();
    print(one.name);

    Person two = Person("Kikie", "Female", 22);
    two.showData()
}
```

### how to declare the object without initializing and the assign later
We will do away with the constructor and replace it with an addData method

```dart
class Person{
    String? name, sex;
    int? age;


    //methods
    void addData(String name, sex, int age){
        this.name = name;
        this.sex = sex;
        this.age = age;
    }

    void showData(){
        print("Name = $name");
        print("Sex = $sex");
        print("Age = $age");

    }
}

void main(){
    //create a person class
    Person one = Person();
    one.addData("Amos", "man", 43);
    one.showData();

    // assign a single item
    Person two = Person();
    two.name = "kikie";
    two.showData();
}
```