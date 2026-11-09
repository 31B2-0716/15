# 15
```c
#include <stdio.h>
#include <locale.h>
#define _USE_MATH_DEFINES
#include <math.h>
#define W 80
#define H 24

int check(double x, double y) {
	int function = (y >= sin(x) && y <= 1.0 && x >= 0 && x <= M_PI);
	return function;
}
void paint() {
    double x_min = -1.0;
    double x_max = 4.0;
    double y_min = -1.5;
    double y_max = 1.5;
    for (int i = 0; i < H; i++) {
        for (int j = 0; j < W; j++) {
            double x = x_min + (x_max - x_min) * j / (W - 1);
            double y = y_max - (y_max - y_min) * i / (H - 1);
            double y_sin = sin(x);
            double y_line = 1.0;
            if (y >= y_sin && y <= y_line && x >= 0 && x <= M_PI) {
                printf("#");
            }
            else if (fabs(y - y_sin) < 0.08) {
                printf("*");
            }
            else if (fabs(y - y_line) < 0.08) {
                printf("=");
            }
            else if (fabs(x) < 0.1){
                printf("|");
            }
            else if (fabs(y) < 0.08) {
                printf("-");
            }
            else {
                printf(" ");
            }
        }
        printf("\n");
    }
}
int main() {
    setlocale(LC_CTYPE, ".UTF-8");
    double x, y;
    int num;
    printf("Введите 1, если хотите проверить, лежит ли точка в области\n"
        "Введите 2, если хотите посмотреть фигуру\n"
        "Введите 3, если хотите завершить работу программы\n");
    scanf("%d", &num);
    while (num != 0)
    {
        switch (num)
        {
        case 1:
            puts("Введи x y: ");
            scanf("%lf %lf", &x, &y);

while (num != 0) 
	{
		switch (num) 
		{
		case 1:
			puts("Введи x y: ");
			scanf("%lf %lf", &x, &y);

            int function = (y >= sin(x) && y <= 1.0 && x >= 0 && x <= M_PI);

			if (check(x, y) == 1) {
				printf("Точка (%.2lf, %.2lf) принадлежит области\n", x, y);
			}
			else {
				printf("Точка(% .2lf, % .2lf) не принадлежит области\n", x, y);
			}
			break;

		case 2:
			paint();
			break;

		default:
			puts("Введено неверное число\n");
		}

		puts("что дальше?\n");
		scanf("%d", &num);
	}

	return 0;
}
}
```
