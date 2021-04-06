![image](https://user-images.githubusercontent.com/60838780/113682878-30378c00-96f6-11eb-91b9-b6fb7a5ffa67.png)  

这就是自己重写数据结构，为其添加遍历方法的写法，分为几下几步
【1】类名中实现Iterator接口，重写返回Iterator类的方法
【2】重写返回类的方法中，new一个新的类，在新new的类中重写hasNext()和next()两个方法
【3】定义个指针指向链表起始，这个指针用n表示:Node n = sentinel，hasNext方法中使用n.next != null;表示，next()方法中用Node node = n.next;n = n.next;return node.item;三个语句移动指针的同时，返回结点的内容。
——————

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
【1】链表的结点在等号左边和右边代表的意思是不相同：node.next = 在等号左边，**表示为node寻找一个指向的对象**，使node指向下一个结点；= node.next 在等号右边**表示一个结点本体**，将此结点本体赋值给等号左边的地址；
【2】若相从链表中删除一个结点，需要同时两个标记curr和prev：prev.next = curr.next 这样就删除了curr结点；如果相加入一个结点需要一个标记就可以了：newNode.next = pointer.next; pointer.next = newNode;这样就在pointer结点之后插入了一个newNode结点；
【3】如果想要适用一个结点标记删除节点比如说：node.next = node.next.next 这样就删除了node.next这个节点，但是在对链表进行遍历时，就要同时保证： node != null && node.next != null 这样结果就是会直接跳过链表最后一个节点，需要在遍历结束后对node进行 if(node != null){}的判断，然后将上边执行的程序再运行一遍。
