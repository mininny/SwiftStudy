## Function Calls
> How are functions called?

### Objective-c
In objc, everything is an object; including the class itself(metaclass). 

The "object of the class" has a list of the methods that the class contains. This list contains necessary information about the function, as `selector`.

When a function is called, a message is sent to the object using the name of the function and the instance: this calls `objc_msgSend`.

This is called `dynamic dispatch`, where the function is located during the runtime and called through this message. This makes it possible that the function calls become invalid, hence the error `unrecognized selector sent to ...`. Because the program has to find the function from the instance and the dispatch table, Objective-C's way of calling method is significantly slower than static/virtual dispatch or inlining. 

### Swift
As a more modern language, Swift compiler optimizes function calls by choosing between static dispatch, virtual dispatch, dynamic dispatch, as well as inlining. 

Because static/virtual dispatch is faster than dynamic dispatch, it is the default behavior for swift unless specified to use dynamic dispatch. 
> Can be specified with `dynamic` or `@objc`

While dynamic dispatch is slower, it offers more flexibility and usability, such as: 
- method swizzling
- KVO






- how swift? why no header and cc?
objective c- everything is object, including the class itself. no static/virtual dispatch or inlining
- Every object has list of methods.
- When a function is called, the objective sends a message to the object using the name of the function

swift- swift compiler optimizes function uses to choose between static/virtual dispatch or inlining.
- when specified or under certain circumstances, it uses dynamic dispatch, using objc's object
- dynamic dispatch is slower, but more flexible in usage. i.e. method swizzling.

methods and such as organized under a class and the object itself, so header and cc is not required. 
The compiler and linker links the things automatically .

- method link? how does xcode find autocomplete?