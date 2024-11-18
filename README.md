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

