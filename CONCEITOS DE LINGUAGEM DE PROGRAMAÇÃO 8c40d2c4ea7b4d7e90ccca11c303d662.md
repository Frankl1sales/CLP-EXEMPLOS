# CONCEITOS DE LINGUAGEM DE PROGRAMAÇÃO

Owner: Franklin Sales de Oliveira
Tags: Guides and Processes
Last edited time: February 8, 2024 12:31 PM

## Correção Questão 6

Em relação aos conceitos de verificação e tipos de uma linguagem de programação, considere as afirmativas a seguir e marque V ou F (Verdadeiro ou Falso).

(XXX) A verificação de tipos é a atividade de assegurar que os operandos de um operador sejam de tipos compatíveis. Um tipo compatível é aquele válido para o operador ou com permissão, nas regras da linguagem, para ser convertido pelo código gerado pelo compilador para um tipo válido.

**RESPOSTA:  V**

<aside>
📌 A verificação de tipos é a execução de testes para detectar erros de tipos em um programa, tanto por parte do compilador quanto durante a execução de um programa. Ela é um fator importante na confiabilidade de uma linguagem.

</aside>

Sebesta, Robert. *Conceitos de linguagens de programação*. Disponível em: Minha Biblioteca, (11th edição). Grupo A, 2018 (p. 14).

```c
#include <stdio.h>

int main() {
    int numeroInteiro = 5;
    float numeroDecimal = 3.14;

    // Conversão de tipo antes da adição
    float numeroInteiroConvertido = (float)numeroInteiro;
    float resultadoAdicao = numeroInteiroConvertido + numeroDecimal;

    // Subtração de dois operandos de tipos compatíveis
    float resultadoSubtracao = numeroDecimal - numeroInteiroConvertido;

    // Saída dos resultados
    printf("Resultado da Adição: %f\n", resultadoAdicao);
    printf("Resultado da Subtração: %f\n", resultadoSubtracao);

    return 0;
}
```

(XXX) É melhor detectar erros durante a execução do que na compilação de um programa, pois no processo de compilação de um algoritmo deve-se dar prioridade a questões mais complexas da análise semântica do programa.

**RESPOSTA: F**

<aside>
📌 Como a verificação de tipos em tempo de execução é dispendiosa, a verificação em tempo de compilação é mais desejável. Além disso, quanto mais cedo os erros nos programas forem detectados, mais barato será fazer todos os reparos necessários

</aside>

Sebesta, Robert. *Conceitos de linguagens de programação*. Disponível em: Minha Biblioteca, (11th edição). Grupo A, 2018 (p. 14).

(XXX) Se todas as vinculações de variáveis a tipos forem estáticas em uma linguagem, a verificação de tipos quase sempre poderá ser feita estaticamente. A vinculação dinâmica de tipos requer a verificação destes em tempo de execução, o que é chamado de verificação dinâmica de tipos.

**RESPOSTA:  V**

`Vinculação Estática`

```c
#include <stdio.h>

int globalVar = 10;  // Variável global

int main() {
    int localVar = 5;  // Variável local
    printf("Global variable: %d\n", globalVar);
    printf("Local variable: %d\n", localVar);
    return 0;
}
```

Neste exemplo, a vinculação estática ocorre durante a compilação, associando **`globalVar`** e **`localVar`** a endereços de memória específicos. Essa vinculação permanece constante durante toda a execução do programa.

`Vinculação Dinâmica`

```c
#include <stdio.h>

int main() {
    int *dynamicVar = malloc(sizeof(int));  // Alocação dinâmica de memória
    *dynamicVar = 7;
    printf("Dynamic variable: %d\n", *dynamicVar);
    free(dynamicVar);  // Liberação de memória alocada dinamicamente
    return 0;
}
```

Neste exemplo, a vinculação dinâmica ocorre quando a memória é alocada dinamicamente para **`dynamicVar`** durante a execução do programa. O endereço de **`dynamicVar`** não é conhecido durante a compilação, sendo resolvido apenas durante a execução.

<aside>
✂️ Talvez a principal desvantagem da vinculação de tipos dinâmica seja o custo. O custo de implementar **a vinculação de atributos dinâmica é considerável, principalmente em tempo de execução. A verificação de tipos deve ser feita em tempo de execução.**

</aside>

Sebesta, Robert. *Conceitos de linguagens de programação*. Disponível em: Minha Biblioteca, (11th edição). Grupo A, 2018. (p. 207)

(XXX) Quando uma linguagem permite que uma dada célula de memória armazene valores de diferentes tipos em diversos momentos durante a execução, a verificação de tipos torna-se desnecessária, pois não há como realizar um controle de tipos em iterações diferentes do algoritmo.

**RESPOSTA: F**

<aside>
✂️ Em linguagens orientadas a objetos puras – por exemplo, **Ruby –, todas as variáveis são referências e não possuem tipos**; todos os dados são objetos e qualquer variável pode referenciar qualquer objeto. De certo modo, nessas linguagens as variáveis são todas do mesmo tipo – elas são referências. No entanto, ao contrário das referências em Java, que estão restritas a referenciar um tipo de valor específico, **em Ruby as variáveis podem referenciar qualquer objeto.**

</aside>

Sebesta, Robert. *Conceitos de linguagens de programação*. Disponível em: Minha Biblioteca, (11th edição). Grupo A, 2018. (p. 206)

**No entanto, mesmo em linguagens como Ruby, onde as variáveis podem referenciar qualquer objeto, ainda ocorre uma forma de verificação de tipos em tempo de execução para garantir que as operações realizadas com essas variáveis sejam seguras e consistentes.**