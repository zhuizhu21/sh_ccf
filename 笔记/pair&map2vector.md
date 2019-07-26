### 1、pair

```c++
pair  <first,second>//map里面的元素就是pair
```

#### 声明

```c++
pair<int,int> p;
make_pair<xxx,xxx>
```
#### 使用
```c++
int main()
{
    pair<int,int> p;
    p=make_pair(1,2);
    cout<<p.first<<" "<<p.second<<endl;
    return 0;
}

```

```c++
int main()
{
    vector<pair<int,int> > v;
    v.push_back(make_pair(1,2));
    v.push_back(make_pair(2,3));
    for(int i=0;i<v.size();i++){
        cout<<v[i].first<<" "<<v[i].second<<endl;
    }
    return 0;
}

```

### 2、map转vector
#### map转pair
```c++ 
通过pair类型做为中间人
vector<pair<int,int> > v(m.begin(),m.end())
```
#### 含有pair类型的vector容器使用sort排序

```c++
函数原型sort 两个 --first->last   --first->last:function(cmp)
可以根据自定义的cmp规则函数对数据进行排序
```

