# 1-.-
#include <iostream>
#include <cmath>
using namespace std;
int main()
{
	setlocale(LC_ALL, "ru");
	double h = 0.2, b = 0.5, n = 10, x, y, min = 3, max = 0;
	double a[] = {-19.2,1.51,7};
	for (int i = 0;i < 3;i++)
	{
		if (a[i] >= 0)
		{
			for (int j = 1;j <= n;j++)
			{
				x = b + j * h;
				y = x * cos(a[i] - x + 1);
				if (abs(y) > abs(max)) { max = y; }
				if (abs(y) < abs(min)) { min = y; }
				cout << y << " ";
			}
		}
		else
		{
			for (int j = 1;j <= n;j++)
			{
				x = b + j * h;
				y = 2*cos(a[i]+x);
				if (abs(y) > abs(max)) { max = y; }
				if (abs(y) < abs(min)) { min = y; }
				cout << y << " ";
			}
		}
	}
	cout << "phi is " << min << " psi is " << max;
	return 0;
	system("pause");
}
