#include <stdio.h>
#include <string.h>
#include <ctype.h>

// Função para identificar a bandeira do cartão
const char* identificarBandeira(const char *numero) {
    int tamanho = strlen(numero);
    if (tamanho < 13 || tamanho > 19) return "Invalido";

    // Converte os primeiros dígitos para comparação
    int primeiroDigito = numero[0] - '0';
    int primeirosDois = (numero[0] - '0') * 10 + (numero[1] - '0');

    // Regras para identificação das bandeiras
    if (primeiroDigito == 4 && (tamanho == 13 || tamanho == 16)) {
        return "Visa";
    } else if ((primeirosDois >= 51 && primeirosDois <= 55) && tamanho == 16) {
        return "MasterCard";
    } else if ((primeirosDois == 34 || primeirosDois == 37) && tamanho == 15) {
        return "American Express";
    } else if ((primeirosDois == 60 || primeirosDois == 65) && tamanho == 16) {
        return "Discover";
    } else {
        return "Bandeira Desconhecida";
    }
}

int main() {
    char numero[20]; // Buffer para o número do cartão (máximo 19 dígitos + null)

    printf("Digite o numero do cartao de credito (sem espacos): ");
    scanf("%s", numero);

    // Verifica se todos os caracteres são dígitos
    int tamanho = strlen(numero);
    for (int i = 0; i < tamanho; i++) {
        if (!isdigit(numero[i])) {
            printf("Erro: Insira apenas digitos.\n");
            return 1;
        }
    }

    // Identifica a bandeira
    const char *bandeira = identificarBandeira(numero);
    printf("Bandeira: %s\n", bandeira);

    return 0;
}
