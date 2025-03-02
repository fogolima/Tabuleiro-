#include <stdio.h>

#define TAMANHO_TABULEIRO 10
#define TAMANHO_NAVIO 3

// Função para inicializar o tabuleiro com 0s (água)
void inicializarTabuleiro(int tabuleiro[TAMANHO_TABULEIRO][TAMANHO_TABULEIRO]) {
    for (int i = 0; i < TAMANHO_TABULEIRO; i++) {
        for (int j = 0; j < TAMANHO_TABULEIRO; j++) {
            tabuleiro[i][j] = 0; // Preenche com 0 (água)
        }
    }
}

// Função para exibir o tabuleiro
void exibirTabuleiro(int tabuleiro[TAMANHO_TABULEIRO][TAMANHO_TABULEIRO]) {
    printf("Tabuleiro:\n");
    for (int i = 0; i < TAMANHO_TABULEIRO; i++) {
        for (int j = 0; j < TAMANHO_TABULEIRO; j++) {
            printf("%d ", tabuleiro[i][j]); // Exibe cada célula do tabuleiro
        }
        printf("\n"); // Nova linha após cada linha do tabuleiro
    }
}

// Função para posicionar um navio horizontalmente
void posicionarNavioHorizontal(int tabuleiro[TAMANHO_TABULEIRO][TAMANHO_TABULEIRO], int linha, int coluna) {
    for (int i = 0; i < TAMANHO_NAVIO; i++) {
        tabuleiro[linha][coluna + i] = 3; // Preenche com 3 (parte do navio)
    }
}

// Função para posicionar um navio verticalmente
void posicionarNavioVertical(int tabuleiro[TAMANHO_TABULEIRO][TAMANHO_TABULEIRO], int linha, int coluna) {
    for (int i = 0; i < TAMANHO_NAVIO; i++) {
        tabuleiro[linha + i][coluna] = 3; // Preenche com 3 (parte do navio)
    }
}

int main() {
    int tabuleiro[TAMANHO_TABULEIRO][TAMANHO_TABULEIRO];

    // Inicializa o tabuleiro com 0s (água)
    inicializarTabuleiro(tabuleiro);

    // Posiciona um navio horizontalmente
    int linha_horizontal = 2; // Linha inicial do navio horizontal
    int coluna_horizontal = 3; // Coluna inicial do navio horizontal
    posicionarNavioHorizontal(tabuleiro, linha_horizontal, coluna_horizontal);

    // Posiciona um navio verticalmente
    int linha_vertical = 5; // Linha inicial do navio vertical
    int coluna_vertical = 7; // Coluna inicial do navio vertical
    posicionarNavioVertical(tabuleiro, linha_vertical, coluna_vertical);

    // Exibe o tabuleiro com os navios posicionados
    exibirTabuleiro(tabuleiro);

    return 0;
}
