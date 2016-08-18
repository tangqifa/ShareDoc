
# 常见的几种架构

- 架构之美
- MVC
- MVP
- MVVM
- RxJava驱动的新型架构
- 实践
  + 家长端（MVP）
  + 教师端（RxJava）
- 总结

---

## 架构之美
![center](http://img2.3lian.com/2014/f6/149/d/15.jpg)

---

## MVC

MVC（Model-View-Controller）是最常见的软件架构之一，业界有着广泛应用。它本身很容易理解,MVC模式的意思是，软件可以分成三个部分.

![center](http://image.beekka.com/blog/2015/bg2015020104.png)

- 视图（View）：用户界面。
- 控制器（Controller）：业务逻辑
- 模型（Model）：数据保存

---

## 通信方式

![center](http://image.beekka.com/blog/2015/bg2015020105.png)

*通信方式都是单向的*

1. View 传送指令到 Controller
2. Controller 完成业务逻辑后，要求 Model 改变状态
3. Model 将新的数据发送到 View，用户得到反馈


---

![center](http://ww4.sinaimg.cn/large/52eb2279jw1f2rx409pcnj2044048mx5.jpg)

---

## 例子
计算器
![center](http://pic14.nipic.com/20110509/581249_213922240000_2.jpg)

 ---
 
微波炉（进一步想象）
![center](http://img1.gtimg.com/tech/pics/19229/19229750.jpg)

---

商场（更进一步想象）
![center](http://www.xyz6688.com/UploadFiles/2012121914620609.jpg)

---

## 本质

如果我们扩大想想，其实很多程序都是这种模式：对外提供一组触发器（上面的按钮及开关），然后执行一些内部操作，最后返回结果。

---

## MVP
MVP 模式将 Controller 改名为 Presenter，同时改变了通信方向。

---

![center](https://pic1.zhimg.com/ffa885b9adc7f4dca8bfe674565e848c_b.jpg)
1. View 与 Model 不发生联系，都通过 Presenter 传递。
2. View 非常薄，不部署任何业务逻辑，称为"被动视图"（Passive View），即没有任何主动性，而 Presenter非常厚，所有逻辑都部署在那里
3. MVP定义了Presenter和View之间的接口，让一些可以根据已有的接口协议去各自分别独立开发，以此去解决界面需求变化频繁的问题

---

## MVVM

ViewModel大致上就是MVP的Presenter和MVC的Controller了，而View和ViewModel间没有了MVP的界面接口，而是直接交互，用数据“绑定”的形式让数据更新的事件不需要开发人员手动去编写特殊用例，而是自动地双向同步。数据绑定你可以认为是Observer模式或者是Publish/Subscribe模式
![center](https://pic4.zhimg.com/1d9336019baa5cabdf0e5e30b3effffb_b.jpg)

---

## RxJava驱动的新型架构

- 引子
```
int a = 4; 
int b = 5;
int c = a + b; 
System.out.println(c); // 9 
a = 6; 
System.out.println(c); // 9 again
```
当我们改变“a”和“b”的值时，“c”并没有改变。换句话说就是，“a”和“b”的改变并没有响应到“c”。
**总结起来就是：程序以流的形式，传递数据的改变。**

---

- 异步和回调
![center](http://img.mukewang.com/56404e190001b46a04870460.png)

---

- Everything is a stream（一切皆流）
![center](http://img.mukewang.com/56404e490001aee404220390.jpg)

---

- Don't break the chain（不要打断链式结构）
![center](http://img.mukewang.com/56404e690001493505330337.png)

---

## 实践
- 家长端架构
![center](/Users/tangqifa/Downloads/jiazhang.png)

---

- 教师端架构
![](/Users/tangqifa/Downloads/teacher-client.png)
---

## 总结
- 先实现，再重构
- 如果从零开始，用什么架构的问题都属于想得太多做得太少的问题
