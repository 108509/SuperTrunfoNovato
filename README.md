# SuperTrunfoNovato
Jogo de Super Trunfo - Novato - 1o semestre

#include <stdio.h>

#define MAX_CIDADES 2
#define TAM_CODIGO 5
#define TAM_NOME_CIDADE 50

// Estrutura para armazenar os dados de uma carta
typedef struct {
    char estado;                // Estado (A-H)
    char codigo[TAM_CODIGO];    // Código da carta (ex: A01)
    char nomeCidade[TAM_NOME_CIDADE]; // Nome da cidade
    int populacao;             // População da cidade
    float area;                // Área da cidade em km²
    float pib;                 // PIB da cidade
    int pontosTuristicos;      // Número de pontos turísticos
} Carta;

void lerDadosCarta(Carta *carta, int numero) {
    printf("Digite os dados da Carta %d:\n", numero);
    
    // Leitura do estado
    printf("Estado (A-H): ");
    scanf(" %c", &carta->estado);
    
    // Leitura do código da carta
    printf("Código da Carta (ex: A01): ");
    scanf("%s", carta->codigo);
    
    // Leitura do nome da cidade
    printf("Nome da Cidade: ");
    scanf(" %[^\n]", carta->nomeCidade); // Lê até a nova linha
    
    // Leitura da população
    printf("População: ");
    scanf("%d", &carta->populacao);
    
    // Leitura da área
    printf("Área (em km²): ");
    scanf("%f", &carta->area);
    
    // Leitura do PIB
    printf("PIB (em bilhões de reais): ");
    scanf("%f", &carta->pib);
    
    // Leitura do número de pontos turísticos
    printf("Número de Pontos Turísticos: ");
    scanf("%d", &carta->pontosTuristicos);
    
    printf("\n");
}

void exibirDadosCarta(Carta carta, int numero) {
    printf("Carta %d:\n", numero);
    printf("Estado: %c\n", carta.estado);
    printf("Código: %s\n", carta.codigo);
    printf("Nome da Cidade: %s\n", carta.nomeCidade);
    printf("População: %d\n", carta.populacao);
    printf("Área: %.2f km²\n", carta.area);
    printf("PIB: %.2f bilhões de reais\n", carta.pib);
    printf("Número de Pontos Turísticos: %d\n", carta.pontosTuristicos);
    printf("\n");
}

int main() {
    Carta cartas[MAX_CIDADES]; // Array para armazenar as cartas

    // Leitura dos dados das cartas
    for (int i = 0; i < MAX_CIDADES; i++) {
        lerDadosCarta(&cartas[i], i + 1);
    }

    // Exibição dos dados das cartas
    for (int i = 0; i < MAX_CIDADES; i++) {
        exibirDadosCarta(cartas[i], i + 1);
    }

    return 0;
}

