## 记录编程的机会 经验 新学到的知识
# 记录新学会的java编程知识
  map.getOrDefault(key， defaultValue)方法
  从map中根据键key获得对应的值，若没有键值对，则返回一个设置的默认值
![image](https://user-images.githubusercontent.com/60838780/112316131-c8d90f80-8ce5-11eb-8d04-5947dc2df2f0.png)这样的写法用处：以数值本身位键，以该数值出现的次数为值，对Map容器进行填充

![image](https://user-images.githubusercontent.com/60838780/113687141-9b835d00-96fa-11eb-839b-2958d0311ca9.png)
对于引用数据类型，对其进行初始化的方法就是使用new关键字，使用“=”进行赋值，才是对基本数据类型进行初始化的方法。

![image](https://user-images.githubusercontent.com/60838780/112316267-e6a67480-8ce5-11eb-9e93-88f22135c6cc.png)
答案是只创建一次对象，因为String类型在java中被设定为一旦创建就不可改变类型，对String类型的改变，都是创建新的String类型。
既然String类型的量是不能改变的，因此可以在进行编译的时候就将其放入字符串常量池中。题目中，三个已经确定的字符串在进行编译的时候就被合并并放入了常量池中，因此只创建一个对象。

![image](https://user-images.githubusercontent.com/60838780/112832262-a3724a00-90c7-11eb-937a-005040c8b6cf.png)
【1】引用数据类型必须进行初始化才有值，不进行初始化就对其进行索引会报错。一旦适用构造方法对其进行初始化，就算构造方法内部没有对该对象进行赋值，java也会给这个对象赋予一个默认的值（基本数据类型和引用数据类型的初始默认值）

![image](https://user-images.githubusercontent.com/60838780/113713734-40f9f900-971a-11eb-83a6-8375356e33c3.png)【1】这种多态的形式称为**父类引用指向子类对象**，通过引用类型直接定义的变量称为引用，new出来的都称为对象。
