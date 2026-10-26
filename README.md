# Sistema-de-Ocupa-o-de-Poltronas-em-C
contagem de poltronas e cálculo da porcentagem de ocupação.



#include <stdio.h>

int main() {
    int mat[3][3];
    int i, j;
    int livres = 0;
    int ocupadas = 0;
    float porcentagem;

    // Preenchimento da matriz
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            do {
                printf("Digite a situacao da poltrona [%d][%d] (0 = Livre, 1 = Ocupada): ", i, j);
                scanf("%d", &mat[i][j]);

                if (mat[i][j] != 0 && mat[i][j] != 1) {
                    printf("Erro! Digite somente 0 ou 1.\n");
                }

            } while (mat[i][j] != 0 && mat[i][j] != 1);
        }
    }

    // Exibicao da sala
    printf("\nSituacao da sala:\n");

    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            if (mat[i][j] == 0) {
                printf("L  ");
            } else {
                printf("O  ");
            }
        }
        printf("\n");
    }

    // Contagem das poltronas
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            if (mat[i][j] == 0) {
                livres++;
            } else {
                ocupadas++;
            }
        }
    }

    // Calculo da porcentagem de ocupacao
    porcentagem = (ocupadas * 100.0) / 9;

    // Apresentacao dos resultados
    printf("\nPoltronas livres: %d\n", livres);
    printf("Poltronas ocupadas: %d\n", ocupadas);
    printf("Ocupacao da sala: %.2f%%\n", porcentagem);

    return 0;
}
