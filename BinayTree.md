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