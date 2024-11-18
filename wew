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

	printf("\n\npoint %c (%.1f,%.1f)", b.name, b.x, b.y);
}

float dist(Point z, Point w) {
	float dek = sqrt(pow(w.x - z.x, 2) + pow(w.y - z.y, 2));
		return dek;
}

Point ser_otr(Point z, Point w) {
	Point m;
	m.name = 'M';
	m.x = ((z.x + w.x) / 2);
	m.y = ((z.y + w.y) / 2);
	return m;
}

int plosk(Point w) {
	if (w.x > 0 && w.y > 0)
		return 1;
	else if (w.x < 0 && w.y > 0)
		return 2;
	else if (w.x < 0 && w.y < 0)
		return 3;
	else if (w.x > 0 && w.y < 0)
		return 4;
}

struct tm {
	int tm_sec;     /* секунды - [0,59] */
	int tm_min;     /* минуты - [0,59] */
	int tm_hour;    /* часы - [0,23] */
	int tm_mday;    /* день - [1,31] */
	int tm_mon;     /* месяц - [0,11] */
	int tm_year;    /* год от 1900 */
	int tm_wday;    /* день недели с воскресенья - [0,6] */
	int tm_yday;    /* номер дня с 1 января - [0,365] */
	int tm_isdst;   /* флаг летнего времени устанавливается >0, если <=0, то информация недоступна*/
};

int main()
{
	setlocale(LC_CTYPE, "RUS");
	Point b, a, z, w;
	a = (Point){ 1.f,2.f,'A' };// Инизиализация структуры
	b.name = 'B'; b.x = 5, b.y = -3;// Инизиализация полей структуры
	z.name = 'Z'; z.x = 3, z.y = -4;
	w.name = 'W'; w.x = -5, w.y = -3;

	put_point(b);

	printf("\n\nДекартовое расстояние между точками %c и %c > %f", z.name, w.name, dist(z, w));

	Point m = ser_otr(z, w);
	put_point(m);

	printf("\n\nТочка %c находится в %d плоскости", w.name, plosk(w));

	
	struct tm* mytime;
	time_t t;
	t = time(NULL);
	mytime = localtime(&t);
	printf("Московское время %02d:%02d:%02d \n", mytime->tm_hour, mytime->tm_min, mytime->tm_sec);
}
