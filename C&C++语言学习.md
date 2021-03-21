# C/C++语言学习
## 运算符重载
(set与multiset，差别在于是否允许重复)
<https://www.cnblogs.com/1hua1ye/p/3959850.html>

~~~c++
struct node
{
    int x;
    int y;
};
//在 set 里面进行重载，和优先队列一样
bool operator<(const node &a, const node &b)
{
    if (a.x == b.x)
        return a.y < b.y;
    return a.x < b.x;
}
void run_case()
{
    set<node> s;
    s.insert(node{1, 1});
    s.insert(node{1, 1});
    s.insert(node{1, 2});
    s.insert(node{1, 3});
    s.insert(node{2, 2});
    s.insert(node{2, 3});
    for (auto t : s)
    {
        cout << t.x << " " << t.y << "\n";
    }
}

struct node
{
	int elem;
	bool operator==(const point b) const
	{
		return this->elem == b.elem;
	}
	bool operator!=(const point b) const
	{
		return this->elem != b.elem;
	}
	bool operator<=(const point b) const
	{
		return this->elem <= b.elem;
	}
	bool operator<(const point b) const
	{
		return this->elem < b.elem;
	}
	bool operator>=(const point b) const
	{
		return this->elem >= b.elem;
	}
	bool operator>(const point b) const
	{
		return this->elem > b.elem;
	}
};

~~~

## Class类

<https://www.cnblogs.com/weekbo/p/8184141.html>i