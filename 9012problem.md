# Stack
### Language: CPP
### Problem

### Check Parenthesis String Using stack


```


#include <iostream>  
#include <stack>
#include <string>
using namespace std;

int main()
{

	int T;
	char temp;
	cin >> T;
	stack<char> *s_arr=new stack<char>[T];
	string *data_arr = new string[T];
	for (int i = 0; i < T; i++)
	{
		cin >> data_arr[i];
	}
	for (int i = 0; i < T; i++)
	{
		for (int j = 0; j < data_arr[i].length(); j++)
		{
			temp = data_arr[i].at(j);
			if (s_arr[i].empty() && temp == ')')
			{
				goto a;
			}
			if (temp == '(')
			{
				s_arr[i].push(temp);
			}
			else if (temp == ')')
			{
			
				if (s_arr[i].top() == '(')
				{
					s_arr[i].pop();
				}
				else
					continue;
			}	
		}
		if (!s_arr[i].empty())
		{
			a:
			cout << "NO"<<endl;
		}
		else if (s_arr[i].empty())
		{
			cout << "YES" << endl;
		}
	}

	

	return 0;
}
