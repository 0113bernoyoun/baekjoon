# 10828Problem
### Language : CPP

```
Problem : Stack basic 
```

~~~
#include <iostream>
#include <stack>
#include <string>

using namespace std;

int main() {
	stack<int> order_stack;
	string order;
	int N=0;
	int max = 0;
	int data = 0;
    
    cin >> N;
	cin.ignore(256, '\n');
    
	while (max < N)
	{
		getline(cin, order);
		string str;
		if (order[2]=='s')
		{
			for (int i = 5; i < order.size(); i++)
			{
				str += order[i];
			}
			data = atoi(str.c_str());
			order_stack.push(data);
		}
		else if (order == "top")
		{
			if (order_stack.empty() == 1)
			{
				cout << -1<<"\n";
			}
			else
			{
				cout << order_stack.top()<<"\n";
            }
		}
		else if (order == "size")
		{
			cout<<order_stack.size()<<"\n";
		}
		else if (order == "pop")
		{
		
			if (order_stack.empty() == 1)
			{
				cout << -1<<"\n";
			}
			else
			{
				cout << order_stack.top() << "\n";
				order_stack.pop();
			}
		}
		else if (order == "empty")
		{
			cout << order_stack.empty()<<"\n";
		}
		max++;
	}
	return 0;
}
~~~
