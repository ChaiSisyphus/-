### 二叉树同时进行多种形式的遍历
![image](https://user-images.githubusercontent.com/60838780/114524604-f0cdea00-9c77-11eb-8d2b-bd09292960e7.png)  
【1】二叉树的递归遍历，完全可以同时传入两个参数，同时进行遍历  
【2】对于布尔型的递归，返回值中有&&运算时，只要返回一次false，值就永远就是false  
***
### 二叉树的前中后序遍历，以及返回层数
![image](https://user-images.githubusercontent.com/60838780/114271322-55ecca00-9a43-11eb-82ff-ff61f0632af7.png)  
【1】对于二叉树来说，最好的办法就是采用递归的方法  
【2】如图所示代码，就可以先当于对二叉树的所有结点进行遍历
![image](https://user-images.githubusercontent.com/60838780/114271370-93515780-9a43-11eb-94fd-66285b621a69.png)  
【3】如图所示代码，是二叉树递归有返回值的情况，返回值可以自己定义。若返回值为结点，就与链表的操作类似。  
![image](https://user-images.githubusercontent.com/60838780/114271409-c5fb5000-9a43-11eb-8442-87c879e41c92.png)  
【4】如果所示，返回值为层数，便可以计算二叉树的最大深度 
***
![image](https://user-images.githubusercontent.com/60838780/114993299-426fb200-9ece-11eb-9ab2-0269b252bea8.png)  
【1】用这种方式可以快速创建一个满二叉树，并且二叉树的左子节点和右子节点都不一样  
【2】以左子节点向下遍历的时候，可以传递参数，该参数只属于当前结点的左子节点，可进行赋值，计算或者创建一个新的左子结点，右子节点同理  
***
![image](https://user-images.githubusercontent.com/60838780/115196670-c4581900-a122-11eb-8896-3d14bf76ce8c.png)  
【1】不在传入curr.left或者curr.right而是每次生成新的root的左右结点，而返回给root  
【2】此方法只有在所有结点在一个数组中同时出现的时候才能使用  
![image](https://user-images.githubusercontent.com/60838780/115353357-ff258400-a1ea-11eb-9de2-6cd0042543ec.png)  
【1】通过递归判断改数是否为二叉排序树  
【2】每一次递归都是在缩小下一次递归的判断范围，如果下一次递归数值不在范围之中，则返回false  
【3】所谓的二叉查找树成立的条件是，随着树的延伸，结点的范围越来越小  
