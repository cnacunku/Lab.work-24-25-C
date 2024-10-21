#define _CRT_SECURE_NO_WARNINGS
#define _USE_MATH_DEFINES
#include <stdio.h>
#include <locale.h>
#include <conio.h>
#include <math.h>
double fa(double x) 
{
	double y1;
	if (x <= 3) y1 = pow(x, 2) - 3 * x + 9;
	else y1 = 1 / (pow(x, 3) + 3);
	return y1;
}
double fb(double x)
{
	double y2;
	y2 = x * exp(sin(pow(x, 2)));
	return y2;
}
int fuk(int N)
{
	int fak = 1;
	for (int i = 1; i <= N; i++)
		fak *= i;
	return fak;
}
double sin_n(double x, int Ne)
{
	for (int i = 1; i <= Ne; i++)
	{
		for (int k = 1; k <= Ne; k++)
		{
			double sin_n = pow(-1, k - 1) * (pow(Ne, 2 * k + 1)) / fuk((2 * k - 1));
		}
	}
}
int main()
{
	setlocale(LC_CTYPE, "RUS");

	double x;
	printf("Введите значение x = ");
	scanf("%lf", &x);

	printf("fa(x)=%lf , fb(x)=%lf \n\n", fa(x), fb(x));
	printf("Произведение : %lf\nРазность квадратов : %lf\nУдвоенная сумма : %lf\n\n", fa(x) * fb(x),pow(fa(x),2)-pow(fb(x),2),(fa(x)+fb(x))*2);

	int Ne,k,fak=1;
	double sin;
	printf("Введите k — ");
	scanf("%d", &Ne);

	for (int k = 1; k <= Ne; k++)
	{
		printf("%d\n", sin_n(N));
	}
	
}
