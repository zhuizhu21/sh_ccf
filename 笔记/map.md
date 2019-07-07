### map//底层实现是红黑树

 map<int,int>m;//初始化一个map m

可以是int string char longlong等类型

存储key-value

根据key来自动排序，默认升序

通过迭代器iterator mit(自定义迭代器名称)来访问 mit->first 访问key  mit->second访问value

```c++
for(mit=m.begin();mit!=m.end();mit++){
  cout<<"key="<<mit->first<<"  value="<<mit->second<<endl;
}
```

或者直接m[key]访问value

```c++
        m[temp]++;
        cout<<m[temp]<<" ";
```

map的基本操作函数：

​      C++ Maps是一种关联式容器，包含“关键字/值”对

​      begin()          返回指向map头部的迭代器

​      clear(）         删除所有元素

​      count() /* m[元素] */       返回指定元素出现的次数

​      empty()          如果map为空则返回true

​      end()            返回指向map末尾的迭代器

​      equal_range()    返回特殊条目的迭代器对

​      erase()          删除一个元素

​      find()    ==0？存在不存在       查找一个元素

​      get_allocator()  返回map的配置器

​      insert()         插入元素

​      key_comp()       返回比较元素key的函数

​      lower_bound()    返回键值>=给定元素的第一个位置

​      max_size()       返回可以容纳的最大元素个数

​      rbegin()         返回一个指向map尾部的逆向迭代器

​      rend()           返回一个指向map头部的逆向迭代器

​      size()           返回map中元素的个数

​      swap()            交换两个map

​      upper_bound()     返回键值>给定元素的第一个位置

​      value_comp()      返回比较元素value的函数