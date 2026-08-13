# B-L-006-题解
日期：2026.08.13
## 题目大意
- 前面的输入循环跟以往一样
- 这道题目首先要对数组进行一个预先的处理，先对数组元素进行排序，方便后续将不重复元素输入另一数组中
- 预处理完数组后就是对元素进行“去重”的处理步骤，需要进行重复判断数组元素前后是否相同（这时因为我们已经排好序，如果前后不重复，就没有机会重复）
- 将并不重复的元素加入进新数组中（注意判断前后一定要输入一个重复元素，不是全部移除）
- 最后再计算数组中元素个数并输出个数和数组内的升序元素

## 代码
```C++
#include <bits/stdc++.h>
#include <algorithm>
using namespace std;
int main(){
    int n;
    cin >>n;
    int v[n];
    for (int i=0;i<n;i++){
        cin>> v[i];
    }
    sort(v,v+n);
    vector<int> v1;
    for (int i=1;i<n;i++){
        if (v[i-1]!=v[i]){
            v1.push_back(v[i-1]);
            // 使用vector容器进行快速输入，使用数组本身进行操作也可以
        }
    }
    // 对相同元素的清除，只留下一个，输出没有重复元素的新数组
    if (v[n-1]!=v[n-2]) {
        v1.push_back(v[n-1]);
    }
    // 确保最后一个没有被忘记
    int size=v1.size();
    cout << size << endl;
    for (int i=0;i<size;i++)
    cout << v1[i] << " ";
    return 0 ;
}
```
