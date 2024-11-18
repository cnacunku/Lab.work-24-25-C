#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <locale.h>
#include <stdlib.h>
#include <conio.h>
#include <math.h>

struct point {
	float x;
	float y;
	char name;
};

typedef struct point Point;

void put_point(Point b) {

	printf("point %c (%.1f,%.1f)", b.name, b.x, b.y);
}

float dist(Point z, Point w) {
	float dek = sqrt(pow(w.x - z.x, 2) + pow(w.y - z.y, 2));
}

float ser_otr(Point z, Point w) {
	Point m;
	m.name = 'M';
	m.x = ((z.x + w.x) / 2);
	m.y = ((z.y + w.y) / 2);
}

int main()
{
	setlocale(LC_CTYPE, "RUS");
	Point b, a, z, w, m;
	a = (Point){ 1.f,2.f,'A' };// Инизиализация структуры
	b.name = 'B'; b.x = 5, b.y = -3;// Инизиализация полей структуры
	z.name = 'Z'; z.x = 3, z.y = -4;
	w.name = 'W'; w.x = -5, w.y = -3;

	put_point(b);
	
	printf("\n\nДекартовое расстояние между точками %c и %c > %f", z.name, w.name, dist(z, w));

	ser_otr(z, w);
	put_point(m);
}


#define _CRT_SECURE_NO_WARNINGS
#define N 666
#include <stdio.h>
#include <locale.h>
#include <stdlib.h>
#include <conio.h>
#include <math.h>

double* full_elements(double* ptr_array, int n)
{
	srand((unsigned)time(NULL));
	for (int i = 0; i < n; i++)
		ptr_array[i] = -50 + rand() % 101 + rand() / (double)RAND_MAX;
	return ptr_array;
}

int put_elements(double* ptr_array, int n)
{
	for (int i = 0;i < n;i++)
		printf("\n a[%d]= %.1f", i, ptr_array[i]);
}

double* calc_elements(double* ptr_array, int n)
{
	for (int i = 0; i < n; i++)
	{
		ptr_array[i] = ceil(ptr_array[i]);
	}
	return ptr_array;
}

double sum_elements(double* ptr_array, int begin, int end)
{
	double summa = 0;
	for (int i = begin;i <= end;i++)
	{
		summa += ptr_array[i];
	}
	return summa;
}

int find_element(double* ptr_array, int n, double element)
{
	for (int i = 0; i < n; i++)
	{
		if (ptr_array[i] == element)
		{
			printf("Элемент был найден на %d индексе\n", i);
			return i; 
		}
	}
	printf("Элемент не найден\n");
	return -1;
}

double summa_chetnih_elementov_menishe_A(double* ptr_array, int n, double A)
{
	double summma = 0;
	for (int i = 0; i < n; i += 2) 
	{
		if (ptr_array[i] < A)
		{
			summma += ptr_array[i];
		}
	}
	return summma;
}

========================

int main()
{
	setlocale(LC_CTYPE, "RUS");
	
	double array[N], element,A,summa=0;
	int size,begin,end;

	printf("Введите размер массива > ");
	scanf("%d", &size);

	full_elements(array, size);
	
	put_elements(array, size);printf("\n");
	printf("Начальный массив\n");

	calc_elements(array, size);

	put_elements(array, size);printf("\n");
	printf("Обработанный массив\n");

	printf("\nНачальный индекс суммы: ");
	scanf("%d", &begin);
	printf("Конечный индекс суммы: ");
	scanf("%d", &end);
	sum_elements(array,begin,end);
	printf("Сумма от %d до %d индекса равна > %.f", begin, end, summa);
	
	printf("\n\nЭлемент, который нужно найти: ");
	scanf("%lf", &element);

	find_element(array, size, element);

	printf("\nЗначение A: ");
	scanf("%lf", &A);
	printf("Сумма значений меньше %.1f на четных позициях равна: %.1f\n", A, summa_chetnih_elementov_menishe_A(array, size, A));
}
