#深入理解Proxy代理

## 代理模式 Proxy, 别名：surrogate
    GOF： 代理模式是指为其他对象提供一种代理，以控制对这个对象的访问。
    代理模式包括三个角色： Subject 、RealSubject 、Proxy。
    
    在需要用比较通用和复杂的对象指针代替简单的指针的时候，使用代理模式。
    
    代理模式分为
        Remote Proxy
        Virtual Proxy
        Protection Proxy
        Smart Regerrence

## 代理的实现方式
### 静态代理
    违犯了开闭原则， 可扩展性差，可维护性差。
### 动态代理
    包括JDK原生动态代理和CGLIB动态代理。
    动态代理使用反射和字节码技术，在运行期创建指定接口或者类的子类（动态代理）以及其实例对象的技术，
    通过这个技术可以无侵入性的为代码进行增强。
    
## Java动态搭理技术的主要实现
### JDK原生动态代理
    Proxy：
        Proxy是所有动态代理的父类。它提供了一个静态方法类创建动态代理的Class对象和实例。
    InvocationHandler：
        每个动态代理实例都有一个关联的InvocationHandler，在代理实例上调用方法时，
        方法调用将被转发到InvocationHandler的invoke方法。
    
### CGLIB动态代理
    Code Generation Library. 是一个基于ASM的自己吗生成库，它允许我们在运行时对自己吗进行修改和动态生成。
    CGLIB是通过继承方式实现代理。
    Enhancer：
        来指定要代理的目标对象，实际处理代理逻辑的对象，最终通过调用create方法得到代理对象，
        对这个对象的所有非final方法的调用都会转发给MethodInterceptor。
    MethodInterceptor:
        动态代理对象的方法调用都会转发到intercept方法进行增强。
        
        
    
    
    


