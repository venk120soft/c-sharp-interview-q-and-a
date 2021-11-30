Resources:
- https://stackify.com/dependency-injection-c-sharp/
- https://docs.microsoft.com/en-us/dotnet/core/extensions/dependency-injection
- [For SOLID Principles](https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)
- [Explanation of DI by Microsoft](https://docs.microsoft.com/en-us/shows/Visual-Studio-Toolbox/Dependency-Injection) | [Source code](https://github.com/miguelcastro67/DI-Webcast)

Testability and Resolving the dependencies by decouple through DI container or IoC(Inversion of control) container

A DI Container is a framework to create dependencies and inject them automatically when required. 
It automatically creates objects based on the request and injects them when required. 
DI Container helps us to manage dependencies within the application in a simple and easy way.[more info](https://www.dotnettricks.com/learn/dependencyinjection/what-is-ioc-container-or-di-container)

Dependency Injection is a software design pattern which enables the development of loosely coupled code.
Through DI, you can decrease tight coupling between software components. 
It is also known as Inversion-of-Control, which makes unit testing convenient.

1) Constructor Injection
2) Setter Injection
3) Method Injection

Constructor Injection is most commonly used Dependecy Injection Pattern

With this we will inject the dependencies throw the constructor
```javascript
Class A{
  private void Add(){
  }
}

Class B{
  private void Add(){
  }
}

Class C{
  private object _obj;

  C(Object obj){
      _obj=obj;
  }
  _obj.Add();
}

Class Program{
  Public static void Main(){
      A objA= new A();
      B objB= new B();
      C objC= new C(objA);
  }
}
```
Instead, we can move methods into Interface and implementing them in all the dependent classes then pass that interface in Class C.
```javascript
Public Interface IgetObject{
  public void Add();
}

Class A:IgetObject{
// we must implement Add metod here
}

Class B:IgetObject{
// we must implement Add metod here
}

Class C{
  private object _obj;
  C(IgetObject obj){
    this._obj= obj;
  }
  this._obj.Add();
}

Class Program{
  Public static void Main(){
      IgetObject= new A();
      C obj= new C(IgetObject);
  }
}
```
