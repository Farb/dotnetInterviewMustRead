# NonTechnology 非技术相关

## 你觉得读源码有什么好处？

1. 阅读源码可以知道底层的实现原理；
2. 即使底层出现bug，阅读源码后可以知道问题出在哪里，并予以纠正；
3. 绝大多数开源的代码还是非常优秀的人编写的，阅读他们的源码，就是跟着优秀的人学习，肯定能学到不少东西。
举例：比如WPF中的[DependencyProperty.Register(string name, Type propertyType, Type ownerType)方法](https://github.com/dotnet/wpf/blob/main/src/Microsoft.DotNet.Wpf/src/WindowsBase/System/Windows/DependencyProperty.cs)。通过源码可知，该底层的实现原理是首先创建一个DependencyProperty的实例，然后对name和ownerType这两个参数的HashCode进行异或运算，最后把异或结果作为key, DependencyProperty的实例作为value，存入一个全局变量PropertyFromName中的HashTable中。