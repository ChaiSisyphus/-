![image](https://user-images.githubusercontent.com/60838780/113682878-30378c00-96f6-11eb-91b9-b6fb7a5ffa67.png)
这就是自己重写数据结构，为其添加遍历方法的写法，分为几下几步
【1】类名中实现Iterator接口，重写返回Iterator类的方法
【2】重写返回类的方法中，new一个新的类，在新new的类中重写hasNext()和next()两个方法
【3】定义个指针指向链表起始，这个指针用n表示:Node n = sentinel，hasNext方法中使用n.next != null;表示，next()方法中用Node node = n.next;n = n.next;return node.item;三个语句移动指针的同时，返回结点的内容。
