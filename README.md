- 👋 Hi, I’m @vineandrade
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
vineandrade/vineandrade is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define TOTAL_NUMEROS 60
#define NUMEROS_SORTEADOS 6

void sortear_numeros(int *numeros_sorteados, int total, int qtd) {
    int i, j, num;
    for (i = 0; i < qtd; ) {
        num = (rand() % total) + 1;
        // Verifica se o número já foi sorteado
        for (j = 0; j < i; j++) {
            if (numeros_sorteados[j] == num) {
                break;
            }
        }
        if (j == i) { // Se não foi sorteado, adiciona à lista
            numeros_sorteados[i] = num;
            i++;
        }
    }
}

int main() {
    int numeros_sorteados[NUMEROS_SORTEADOS];
    int i;

    // Inicializa a semente do gerador de números aleatórios
    srand(time(NULL));

    // Sorteia os números
    sortear_numeros(numeros_sorteados, TOTAL_NUMEROS, NUMEROS_SORTEADOS);

    // Exibe os números sorteados
    printf("Números sorteados: ");
    for (i = 0; i < NUMEROS_SORTEADOS; i++) {
        printf("%d ", numeros_sorteados[i]);
    }
    printf("\n");

    return 0;
}
