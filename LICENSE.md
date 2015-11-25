#include <stdio.h>
#include <stdlib.h>

FILE *inn = fopen("OPTION.TXT", "r");
FILE *out = fopen("MAP.TXT", "w");

int Y, X, N;
bool m[200][200];

int main(){
	int i, u, y, x;

	fscanf(inn, "%d%d%d", &Y, &X, &N);

	while (N){
		y = rand() % Y, x = rand() % X;
		if (!m[y][x]) m[y][x] = true, N--;
	}

	fprintf(out, "%d %d %d\n", Y, X, N);

	for (i = 0; i < Y; i++){
		for (u = 0; u < X; u++) fprintf(out, "%c", ((m[i][u]) ? '*' : '.'));
		fprintf(out, "\n");
	}

	return 0;
}
