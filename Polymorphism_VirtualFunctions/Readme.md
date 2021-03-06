# Polymorphism and virtual functions
The word polymorphism means having many forms. Typically, polymorphism occurs when there is a hierarchy of classes and they are related by inheritance

C++ polymorphism means that a call to a member function will cause a different function to be executed depending on the type of object that invokes the function
```C
main()
{
Shape *shape;  parent class<br>
Rectangle rec(10,7); inherited class<br>
Triangle  tri(10,5);  inherited class<br>
   // store the address of Rectangle<br>
   shape = &rec;<br>	
   // call rectangle area.<br>
   shape->area();<br>
}
```
Here instead of  calling rectangle area , the call goes to parent shape class, this is due to STATIC/EARLY binding which is done by the compiler

To avoid such behavior we add VIRTUAL keyword before the function telling compiler to DYNAMICALLY bind that function.
```C
virtual area()
{
code
}
```
**When above function is declared in base class the selection of the function call in main, is based on kind of object called here. In this case instead of shape class(static)  goes to rectangle class area function**

A virtual function is a function in a base class that is declared using the keyword virtual. Defining in a base class a virtual function, with another version in a derived class, signals to the compiler that we don't want static linkage for this function.

