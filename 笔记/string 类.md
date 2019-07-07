---
C++自带string类的常用方法
  1 #include<iostream>
  2 #include<string>
  3 using namespace std;
  4 
  5 int main()
  6 {
  7     string str1 = "hello";
  8     string* str2 = new string("hello");
  9     string str3 = "world";
 10 
 11     //获取字符串长度
 12     int length = str1.length();
 13     cout << "调用str.length()函数获取字符串长度：" << length << endl;
 14     cout << endl;
 15 
 16 
 17     //字符串连接
 18     string str4 = str1 + str3;
 19     cout << "字符串连接结果：" << str4 << endl;
 20     cout << endl;
 21 
 22 
 23     //字符串比较
 24     if (str1 < str3)
 25         cout << "字符串比较：" << "str1<str2" << endl;
 26     cout << endl;
 27 
 28 
 29     //获取字符串的第一个字符
 30     string::const_iterator it = str1.begin();
 31     cout << *it << endl;
 32     cout << endl;
 33 
 34 
 35     //获取字符串的最后一个字符
 36     it = str1.end();//end是指向最后一个字符后面的元素，而且不能输出,所以cout << *it << endl;这样输出会报错
 37     it--;
 38     cout << *it << endl;
 39     cout << endl;
 40 
 41 
 42     //倒置串
 43     reverse(str1.begin(), str1.end());
 44     cout << "倒置串：" << str1 << endl;
 45     cout << endl;
 46 
 47     //字符串转字符数组
 48     //不推荐的用法，但是需要了解
 49     string a = "abc123";
 50     const char *b;//这里必须为const char *，不能用char *,不然下一句会报错
 51     b = a.c_str();
 52     cout << "a:" << a << endl;
 53     cout << "b:" << b << endl;
 54     a = "asd456";
 55     cout << "a:" << a << endl;
 56     cout << "b:" << b << endl;
 57     //推荐用法
 58     string c = "abc123";
 59     char *d = new char[20];
 60     strcpy(d, c.c_str());//因为这里没有直接赋值，所以指针类型可以不用const char *
 61     cout << "c:" << c << endl;
 62     cout << "d:" << d << endl;
 63     c = "asd456";
 64     cout << "c:" << c << endl;
 65     cout << "d:" << d << endl;
 66     cout << endl;
 67 
 68 
 69     //查找串
 70     //find-从指定位置起向后查找，直到串尾
 71     string st1("babbabab");
 72     cout << st1.find('a') << endl;//1,默认从位置0（即第1个字符）开始查找
 73     cout << st1.find('a', 2) << endl;//4   在st1中，从位置2（b，包括位置2）开始，查找a，返回首次匹配的位置
 74     cout << (st1.find('c', 0) == -1) << endl;//1 
 75     cout << (st1.find('c', 0) == 4294967295) << endl;//1   两句均输出1，原因是计算机中-1和4294967295都表示为32个1（二进制）
 76     string st2("aabcbcabcbabcc");
 77     str1 = "abc";
 78     cout << st2.find(str1, 2) << endl;//6,从st2的位置2（b）开始匹配，返回第一次成功匹配时匹配的串（abc）的首字符在st2中的位置，失败返回-1
 79     cout << st2.find("abcdefg", 2, 3) << endl;//6   取abcdefg得前3个字符（abc）参与匹配，相当于st2.find("abc", 2)
 80 
 81     //rfind-从指定位置起向前查找，直到串首
 82     cout << st1.rfind('a', 7) << endl;//6
 83 
 84     //find_first_of-在源串中从位置pos起往后查找，只要在源串中遇到一个字符，该字符与目标串中任意一个字符相同，就停止查找，返回该字符在源串中的位置；若匹配失败，返回-1
 85     string str6("bcgjhikl");
 86     string str7("kghlj");
 87     cout << str6.find_first_of(str7, 0) << endl;//2,从str1的第0个字符b开始找，g与str2中的g匹配，停止查找，返回g在str1中的位置2
 88     
 89     //find_last_of-与find_first_of函数相似，只不过查找顺序是从指定位置向前
 90     string str("abcdecg");
 91     cout << str.find_last_of("hjlywkcipn", 6) << endl;//5,从str的位置6(g)开始向前找，g不匹配，再找c，c匹配，停止查找，返回c在str中的位置5
 92 
 93     //find_first_not_of-在源串中从位置pos开始往后查找，只要在源串遇到一个字符，与目标串中的任意字符都不相同，就停止查找，返回该字符在源串中的位置；若遍历完整个源串，都找不到满足条件的字符，则返回-1
 94     cout << str.find_first_not_of("kiajbvehfgmlc", 0) << endl;//3   从源串str的位置0(a)开始查找，目标串中有a，匹配，..,找d，目标串中没有d（不匹配），停止查找，返回d在str中的位置3
 95 
 96     //find_last_not_of-与find_first_not_of相似，只不过查找顺序是从指定位置向前
 97     cout << str.find_last_not_of("kiajbvehfgmlc", 6) << endl;//3
 98 
 99     system("pause");
100     return 0;
101 
102 }
---



#### string 类

1.声明

string s;

2.特点

相当于变长的字符串数组，类似于vector<char>

```
    string s;//class
    string s1;
    s="wsh";
    s1="520";
    s=s+s1;
    cout<<s<<endl;
    return 0;
```

