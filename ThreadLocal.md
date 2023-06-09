## 原理
![avatar](./ThreadLocal.png)

## ThreadLocalMap 中key为什么设计成 WeakReference（弱引用）类型？
当ThreadLocal引用消失后，ThreadLocal对象便不可能再被访问。key如果设计成强引用类型，ThreadLocal对象无法被回收，造成内存泄露。

## ThreadLocalMap 中value一直有强引用，不是会导致内存泄露？
key被回收后，value对象无法被访问，但一直被Entry强引用着，造成内存泄露。手动调用remove()方法可避免

## 参考资料
https://kstack.corp.kuaishou.com/article/3245  
https://juejin.cn/post/6932807532587810824
