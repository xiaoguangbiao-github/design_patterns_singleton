# 软件设计模式-详细讲解（pdf文档说明和代码示例）

## 1、项目介绍
&emsp;&emsp;软件设计模式（Software Design Pattern），又称设计模式，是一套被反复使用、多数人知晓
的、经过分类编目的、代码设计经验的总结。它是解决特定问题的一系列套路，是前辈们的代码设计经验的总
结，具有一定的普遍性，可以反复使用。 

&emsp;&emsp;本项目是通过代码示例的方式，讲解：
- 2种饿汉模式的实现
- 4种懒汉模式实现
- 序列化和反射是如何破坏单例的
- 如何防止序列化和反射破坏单例  

&emsp;&emsp;本项目文字描述等资料在项目根目录的pdf文件夹下。


## 2、开发环境

- 语言：Java 8

- Eclipse/IDEA

- 依赖管理：Maven


## 3、项目目录
└─xiaoguangbiao  
&emsp;├─pattern  
&emsp;│  └─singleton &emsp;//单例模式  
&emsp;│   &emsp;├─demo1  &emsp;//饿汉式： 静态成员变量    
&emsp;│  &emsp;│&emsp;   Client.java    
&emsp;│  &emsp;│&emsp; Singleton.java    
&emsp;│  &emsp;│      
&emsp;│   &emsp;├─demo2  &emsp;//饿汉式：静态代码块   
&emsp;│  &emsp;│&emsp;  Client.java    
&emsp;│  &emsp;│&emsp; Singleton.java    
&emsp;│  &emsp;│      
&emsp;│  &emsp;├─demo3  &emsp;//懒汉式：synchronized同步方法    
&emsp;│  &emsp;│&emsp;  Client.java    
&emsp;│  &emsp;│&emsp;  Singleton.java    
&emsp;│  &emsp;│      
&emsp;│  &emsp;├─demo4  &emsp;//懒汉式：synchronized同步代码块 + volatile      
&emsp;│  &emsp;│&emsp;   Client.java    
&emsp;│  &emsp;│&emsp;  Singleton.java    
&emsp;│  &emsp;│      
&emsp;│   &emsp;├─demo5  &emsp;//懒汉式：静态内部类方式  
&emsp;│  &emsp;│&emsp;   Client.java   
&emsp;│  &emsp;│&emsp;  Singleton.java   
&emsp;│  &emsp;│      
&emsp;│   &emsp;├─demo6  &emsp;//懒汉式：枚举实现方式  
&emsp;│  &emsp;│&emsp;   Client.java    
&emsp;│  &emsp;│&emsp;  Singleton.java    
&emsp;│  &emsp;│      
&emsp;│  &emsp;├─demo7  &emsp;//使用序列化破坏单例模式及预防  
&emsp;│  &emsp;│&emsp;   Client.java    
&emsp;│  &emsp;│&emsp;  Singleton.java    
&emsp;│  &emsp;│      
&emsp;│   &emsp;├─demo8  &emsp;//使用反射破坏单例模式及预防  
&emsp;│  &emsp;│ &emsp;   Client.java   
&emsp;│  &emsp;│ &emsp;   Singleton.java   
&emsp;│  &emsp;│       
&emsp;│  &emsp;└─demo9   &emsp;//Runtime举例  
&emsp;│  &emsp;&emsp;&emsp; RuntimeDemo.java   
&emsp;│              
&emsp; └─principles   &emsp;//设计原则  
&emsp;&emsp;&emsp;├─demo1  &emsp;//开闭原则   
&emsp;&emsp;&emsp;│&emsp;&emsp;  Client.java   
&emsp;&emsp;&emsp;│&emsp;&emsp;  DefaultSkin.java   
&emsp;&emsp;&emsp;│&emsp;&emsp;  HeimaSkin.java   
&emsp;&emsp;&emsp;│&emsp;&emsp;  ougouInput.java   
&emsp;&emsp;&emsp;│      
&emsp;&emsp;&emsp;├─demo2  &emsp;//里氏代换原则   
&emsp;&emsp;&emsp;│&emsp;├─after  &emsp;//使用里氏代换原则示例  
&emsp;&emsp;&emsp;│&emsp;│&emsp;  Quadrilateral.java  
&emsp;&emsp;&emsp;│&emsp;│&emsp;   Rectangle.java  
&emsp;&emsp;&emsp;│&emsp;│&emsp;   RectangleDemo.java  
&emsp;&emsp;&emsp;│&emsp;│&emsp;   Square.java  
&emsp;&emsp;&emsp;│&emsp;│      
&emsp;&emsp;&emsp;│&emsp;└─before  &emsp;//不使用示例  
&emsp;&emsp;&emsp;│&emsp;│&emsp;  Rectangle.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;  RectangleDemo.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;   Square.java   
&emsp;&emsp;&emsp;│          
&emsp;&emsp;&emsp;├─demo3  &emsp;//依赖倒转原则  
&emsp;&emsp;&emsp;│&emsp;├─after   &emsp;//使用依赖倒转原则示例  
&emsp;&emsp;&emsp;│&emsp;│&emsp;  Computer.java  
&emsp;&emsp;&emsp;│&emsp;│&emsp; ComputerDemo.java  
&emsp;&emsp;&emsp;│&emsp;│&emsp;  Cpu.java  
&emsp;&emsp;&emsp;│&emsp;│&emsp;  HardDisk.java  
&emsp;&emsp;&emsp;│&emsp;│&emsp; IntelCpu.java  
&emsp;&emsp;&emsp;│&emsp;│&emsp;  KingstonMemory.java  
&emsp;&emsp;&emsp;│&emsp;│&emsp;  Memory.java  
&emsp;&emsp;&emsp;│&emsp;│&emsp;  XiJieHardDisk.java   
&emsp;&emsp;&emsp;│&emsp;│    
&emsp;&emsp;&emsp;│&emsp;└─before   &emsp;//不使用示例  
&emsp;&emsp;&emsp;│&emsp;│&emsp;   Computer.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;  ComputerDemo.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;   IntelCpu.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;   KingstonMemory.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;   XiJieHardDisk.java   
&emsp;&emsp;&emsp;│          
&emsp;&emsp;&emsp;├─demo4  &emsp;//接口隔离原则  
&emsp;&emsp;&emsp;│&emsp;├─after    &emsp;//使用接口隔离原则示例  
&emsp;&emsp;&emsp;│&emsp;│&emsp;   AntiTheft.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;    Client.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;   Fireproof.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;   HeiMaSafetyDoor.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;    ItcastSafetyDoor.java   
&emsp;&emsp;&emsp;│&emsp;│&emsp;   Waterproof.java   
&emsp;&emsp;&emsp;│&emsp;│      
&emsp;&emsp;&emsp;│&emsp;└─before    &emsp;//不使用示例   
&emsp;&emsp;&emsp;│&emsp;&emsp;&emsp;      Client.java   
&emsp;&emsp;&emsp;│&emsp;&emsp;&emsp;     HeimaSafetyDoor.java   
&emsp;&emsp;&emsp;│&emsp;&emsp;&emsp;   SafetyDoor.java   
&emsp;&emsp;&emsp;│           
&emsp;&emsp;&emsp;└─demo5  &emsp;//迪米特法则  
&emsp;&emsp;&emsp;&emsp;&emsp;   Agent.java   
&emsp;&emsp;&emsp;&emsp;&emsp;   Client.java   
&emsp;&emsp;&emsp;&emsp;&emsp;  Company.java   
&emsp;&emsp;&emsp;&emsp;&emsp;  Fans.java   
&emsp;&emsp;&emsp;&emsp;&emsp;  Star.java 


