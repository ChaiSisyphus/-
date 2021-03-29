## 记录编程的机会 经验 新学到的知识
# 记录新学会的java编程知识
  map.getOrDefault(key， defaultValue)方法
  从map中根据键key获得对应的值，若没有键值对，则返回一个设置的默认值
![image](https://user-images.githubusercontent.com/60838780/112316131-c8d90f80-8ce5-11eb-8d04-5947dc2df2f0.png)
# 刷题获得的知识
![image](https://user-images.githubusercontent.com/60838780/112316267-e6a67480-8ce5-11eb-9e93-88f22135c6cc.png)
答案是只创建一次对象，因为String类型在java中被设定为一旦创建就不可改变类型，对String类型的改变，都是创建新的String类型。
既然String类型的量是不能改变的，因此可以在进行编译的时候就将其放入字符串常量池中。题目中，三个已经确定的字符串在进行编译的时候就被合并并放入了常量池中，因此只创建一个对象。

![image](https://user-images.githubusercontent.com/60838780/112832262-a3724a00-90c7-11eb-937a-005040c8b6cf.png)
【1】引用数据类型必须进行初始化才有值，不进行初始化就对其进行索引会报错。一旦适用构造方法对其进行初始化，就算构造方法内部没有对该对象进行赋值，java也会给这个对象赋予一个默认的值（基本数据类型和引用数据类型的初始默认值）

# 有关链表操作心得
![image](https://user-images.githubusercontent.com/60838780/112478795-53d20c80-8daf-11eb-9c19-16e91ce91a7e.png)
【1】对链表进行遍历的时候，一定要保证所有结点的next属性之前的对象不为空，对多个链表进行遍历在判断条件中一定是“&&”符号。
【2】引用数据类型内部存的是地址，将一个引用数据类型赋值给另一个的时候，被赋值的引用数据类型，就指向之前的地址所代表的内容。因此这两个类型完全相同，修改一个地址对对应内容的同时另一个也会随之修改。
【3】建立链表时一般需要建立一个头节点，该头节点内部只存储下一个结点的地址，不存储数据

![image](https://user-images.githubusercontent.com/60838780/112632805-90ffd280-8e73-11eb-9e5a-ad3e7f6d2fd8.png)
【1】聊表的头节点指的是链表中的第一个结点元素
【2】如果要返回一个链表最好创建新的结点（起始结点）指向链表的头节点，返回时返回该结点的下一个结点
【3】在链表中删除结点时，一般需要定义两个指针prev与curr，prev.next = curr.next 即可，需要注意：这样的操作后prev不再需要移动，而curr需要向后移动一个结点
【4】prev.next = curr.next 指令执行之后，此时有还有一个结点指向curr，只是这个结点没有了其他结点指向，因此需要再次执行一次curr = curr.next,将链表继续遍历下去

![image](https://user-images.githubusercontent.com/60838780/112707223-c690d400-8ee4-11eb-988e-1d360d12e13e.png)
【1】链表的结点在等号左边和右边代表的意思是不相同：node.next = 在等号左边，**表示为node寻找一个指向的对象**，使node指向下一个结点；= node.next 在等号右边**表示一个结点本体**，将此结点本体赋值给等号左边的地址；【2】若相从链表中删除一个结点，需要同时两个标记curr和prev：prev.next = curr.next 这样就删除了curr结点；如果相加入一个结点需要一个标记就可以了：newNode.next = pointer.next; pointer.next = newNode;这样就在pointer结点之后插入了一个newNode结点；【3】如果想要适用一个结点标记删除节点比如说：node.next = node.next.next 这样就删除了node.next这个节点，但是在对链表进行遍历时，就要同时保证： node != null && node.next != null 这样结果就是会直接跳过链表最后一个节点，需要在遍历结束后对node进行 if(node != null){}的判断，然后将上边执行的程序再运行一遍。

![image](https://user-images.githubusercontent.com/60838780/112832961-a15cbb00-90c8-11eb-87a5-30e3f435c442.png)
【1】当我们自己新建一个链表的时候，一定要给最后一个结点的执行地址赋值为为null： lastNode.next = null; 这是因为最后一个结点可能会指向其他结点，从而造成该链表不能正确结束。
【2】对链表进行操作时，等号左边出现node.next 属性时，就涉及到对链表本身的属性进行修改，若左边只出现一个变量的时候，该变量可以看作一个指针，读取链表中的结点，却并不会对链表本身的属性进行修改。
