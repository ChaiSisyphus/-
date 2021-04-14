### map方法
  map.getOrDefault(key， defaultValue)方法
  从map中根据键key获得对应的值，若没有键值对，则返回一个设置的默认值
![image](https://user-images.githubusercontent.com/60838780/112316131-c8d90f80-8ce5-11eb-8d04-5947dc2df2f0.png)这样的写法用处：以数值本身位键，以该数值出现的次数为值，对Map容器进行填充
*** 
### 数组
![image](https://user-images.githubusercontent.com/60838780/113825295-625af380-97b3-11eb-99a4-aa400b98b636.png)
【1】数组不是基本数据类型，里边存放一个地址。将数组带入方法时，实质上是将数组的起始地址带入方法，直接对该数组进行操作，操作结束后无需设置返回值，原地址上就是操作结束后的数组。  
【2】**数组打印输出**时，可采用Arrays.toString(数组名)的方法。
***
### 包装类与基本数据类型
![image](https://user-images.githubusercontent.com/60838780/113825553-b4037e00-97b3-11eb-98d6-5171ae594872.png)  
【1】基本数据类型转换为包装类的时候，其实内部调用的是Integer.valueOf(int index)方法  
![image](https://user-images.githubusercontent.com/60838780/113825691-e0b79580-97b3-11eb-9461-65a59c9dabd5.png)  
【2】包装类转换为基本数据类型的时候，调用的是index.intValur;  
```
Integer i4 = new Integer(40);
Integer i5 = new Integer(40);
Integer i6 = new Integer(0);
System.out.println(i4 == i5 + i6);   //true
```
【3】加减操作并不适合Integer对象，i5和i6进行自动拆箱操作，将包装类转化为int类型然后参加运算，所以上述式子就相当于：40 == 40 + 0；
***
### set集合和list集合
【1】set集合存储数据无序，但是不允许数据重复。主要包括HashSet，但是LinkedHashSet存储数据是有序的。  
【2】set集合不允许存储相同的数据元素，add()方法在存储相同的数据时返回false，因此可以对数组中是否存在相同的元素进行检测。  
【3】List集合存放数据有序，允许数据进行重复，其中主要包括LinkedList和ArrayList；
***
### String与字符串常量池
![image](https://user-images.githubusercontent.com/60838780/112316267-e6a67480-8ce5-11eb-9e93-88f22135c6cc.png)  
答案是只创建一次对象，因为String类型在java中被设定为一旦创建就不可改变类型，对String类型的改变，都是创建新的String类型。
既然String类型的量是不能改变的，因此可以在进行编译的时候就将其放入字符串常量池中。题目中，三个已经确定的字符串在进行编译的时候就被合并并放入了常量池中，因此只创建一个对象。
***
### 对引用数据类型进行初始化需要使用new关键字
![image](https://user-images.githubusercontent.com/60838780/112832262-a3724a00-90c7-11eb-937a-005040c8b6cf.png)  
【1】引用数据类型必须进行初始化才有值，不进行初始化就对其进行索引会报错。一旦适用构造方法对其进行初始化，就算构造方法内部没有对该对象进行赋值，java也会给这个对象赋予一个默认的值（基本数据类型和引用数据类型的初始默认值）  
![image](https://user-images.githubusercontent.com/60838780/113687141-9b835d00-96fa-11eb-839b-2958d0311ca9.png)  
【2】对于引用数据类型，对其进行初始化的方法就是使用new关键字，使用“=”进行赋值，才是对基本数据类型进行初始化的方法。
***
### 等号左右两边变量的叫法
![image](https://user-images.githubusercontent.com/60838780/113713734-40f9f900-971a-11eb-83a6-8375356e33c3.png)  
【1】这种多态的形式称为**父类引用指向子类对象**，通过引用类型直接定义的变量称为引用，new出来的都称为对象。
***
### 多态的方法调用规则
【1】优先检查调用的方法，父类中是否有，没有则报错；若有，优先执行子类中重写的父类方法，子类没有重写，则调用父类方法
***
### 多态的条件、好处，以及思想
![image](https://user-images.githubusercontent.com/60838780/113716401-25442200-971d-11eb-825e-b6d6c5505ef2.png)  
【1】多态的三个条件  （1）要有继承实现关系（2）要有方法的重写（3）父类引用指向子类对象.  
【2】多态的好处：我们不关心所创建的对象是什么，我们只关心对于不同的对象我们都能调用同一种父类中的方法。通过多态我们可以传递不同的对象，通过不同的对象来调用重写后的方法，这样就增加了程序的灵活性和可拓展性  
【3】图中我们通过调用showAnimalEat(new Cat());showAnimalEat(new Dog());就相当于调用了showCatEar();showDogEat();两个方法。
***
### 编程中使用队列的写法
![image](https://user-images.githubusercontent.com/60838780/113871005-04df9a80-97e5-11eb-9670-7227a4502ba2.png)  
【1】想使用队列的话一般就要使用多态形式，引用类型可选**Queue**，但是创建LinkedList的对象。  
【2】调用方法的时候，会优先调用LinkedList中重写Queue的方法，如果调用的不是Queue中的方法(LinkedList重写的方法)就会报错。
***
### Queue与Deque
Queue为单向队列，满足先入先出原则，一般在一段插入结点另一端删除结点；Deque读作“deck”，表示“double ended queue（双端队列），两端都可以进行插入和删除操作。
***
### 基本数据类型都是小写开头
![image](https://user-images.githubusercontent.com/60838780/113721159-dbaa0600-9721-11eb-8fe6-6df64337e942.png)  
【1】在java中基本数据类型都是小写开头，引用数据类型都是大写开头
***
### getClass() 属于Object类，类似的还有hashCode();equals();toString();方法
getClass()为Object类的所属方法，因此每个对象都可以调用getClass()方法，返回该对象的运行时类
***
### 希尔排序
【1】希尔排序与直接插入排序的区别在于：每单次排序时的跨越长度h不一样。直接插入排序跨越区间始终为1，而希尔排序h在不断减少，直至变为1.并且h的选择规则为：
``` 
h = 2 * h + 1 < array.length;  
```
注意只是排序的跨越区间发生了变化，而排序的起始点的变化其实还是1.  
【2】希尔排序子所以速度较快的原因在于：直接插入排序在大多数数值都已经排列整齐的条件下，效率特别高，可以直接采用break终止继续判断，因此刚开始使用较大跨度的插入排序，可以有效的提高被排列数组的整齐度，因此提高整个算法的效率。
***
### 归并排序
【1】对于归并排序来说，核心思想在于分治后的合并，每次将数组分为head ~ mid和 mid+1 ~ rear 两部分。最终分裂的终点时每个数组中仅剩两个元素  
【2】合并排序时，采用双指针的思想，同时获得两个数组中较小的元素。将其带入一个新开创的辅助数组，获得一个新的从大到小进行排列的整齐的数组。  
【3】快速排序与归并排序同样采用双指针形式进行排序。在快速排序中，左指针对应大于拆分依据的部分，右指针对应小于拆分依据的部分。因此，最后需要将右指针与拆分依据进行互换，保证左边统一小于返回的下一次数组的拆分依据。注意交换的对象是右指针，因为是将数据向左交换的，而右指针指向的就是小于拆分标准的值。
***
### 快速排序
![image](https://user-images.githubusercontent.com/60838780/114509497-24a11380-9c68-11eb-92d8-67c6917d8798.png)  
【1】当两个指针相遇后，必须要再次查找一次，找到下一个右指针定位的地方，然后将右指针与差分依据进行交换，因此使用
```
while(true){
    if(){
      break;
    }
   ```
的方式，判断条件放在循环之后，不满足条件时循环体多运行一次
***
### 递归
【1】对于递归来说，主要的关注点在于递归的开始和终止条件，以及可以通用的计算过程。其余的可以进行忽略。
***
![image](https://user-images.githubusercontent.com/60838780/114675802-3d2e2e00-9d3b-11eb-8abd-5008fc0c85a1.png)  
【1】递归的每次返回，值都会传递给上一次调用的方法，因此想获得上一次的返回值，必须将递归调用方法放在等号右边，获得返回值  
【2】二叉树遍历，左右子树都会有返回值，可分别获得进行比较，也可 count += 递归方法，对递归过程产生的数值进行加和  
***
### 栈与队列的顶与底，peek()函数的返回项
【1】栈与队列的顶与底在图形描述上刚好相反  
【2】栈与队列的顶都是下一个即将弹出的元素，因此也是peek()函数的返回对象。
***
### 类、对象与引用
我们看这段代码
```
Person person;
person = new Person("ZhangSan");
```
【1】Person是一个类，而person是由类定义的一个引用，“ZhangSan”为一个对象，所以称为person是指向“ZhangSan”对象的一个引用。  
【2】只有new出来的数据类型，才能称为对象。由类定义的数据类型，称为引用数据类型。  
【3】对象内存数据，引用内存地址。  
***
### long类型的写法注意
【1】long类型的数据一定要在数值后面加上一个L，否则会被作为整型解析
***
### 包装类的常量池
【1】Byte、Short、Integer、Long、Character、Boolean都实现了产量池技术  
【2】Folat、Double并没有实现常量池技术
***
### 递归思想
【1】每一次递归都会向着退出递归的条件逼近，就好像闭环控制系统向着稳定条件逼近一样  
【2】若递归有返回值，遵守谁调用，就将结果返回给谁的原则  
![image](https://user-images.githubusercontent.com/60838780/114255730-a6ced500-99e7-11eb-8428-cca922446145.png)  
每次递归调用时发生的值传递： x ——> x.right  
返回值返回上一次递归调用时，发生的值传递 x.right ——> x 
【3】递归内调用函数获得返回值后，会继续向下执行，直至执行结束，然后返回上一次递归调用。也要遵循if，switch，顺序等的执行结构  
【4】递归和循环完全可以等价，而递归的代码更加简洁，但是不容易理解  
【5】可以专门设立一个方法，该方法整体就是递归，在主函数中调用该方法即可。这和在主方法中写循环体等价    
【6】对递归函数进行推导的时候，从退出递归条件开始逆推，获得每次调用返回值，并将该返回值从赋值给上一次调用的递归函数，以此类推，直至逆推出调用递归时的初始状态  
***
### 泛型继承Comparable接口
![image](https://user-images.githubusercontent.com/60838780/114267574-0bf9e900-9a2f-11eb-8bdd-7fa7899ff9de.png)  
【1】如果需要泛型之间比较，一般来说就是键或者值进行比较，需要**继承**Comparable接口，注意是**继承**，而不是实现  
【2】继承Comparable接口之后，泛型就可以调用comparableTo()方法
***





