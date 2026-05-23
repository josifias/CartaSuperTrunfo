# 🃏 Super Trunfo - Cadastro de Cartas em C

Este é um programa simples escrito em linguagem C desenvolvido como parte do desafio do curso da **Faculdade Estácio** / **MateCheck**. O objetivo principal é consolidar os conceitos fundamentais de programação, como entrada e saída de dados, manipulação de strings e gerenciamento do buffer do teclado.

## 🚀 Funcionalidades

*   **Cadastro Duplo:** Permite a inserção de dados para duas cartas distintas consecutivamente.
*   **Captura Avançada de Texto:** Utiliza `fgets` para permitir que o usuário digite nomes de cidades com espaços (ex: "Rio de Janeiro").
*   **Limpeza de Buffer:** Implementação de técnicas para evitar o pulo de leituras no teclado.
*   **Exibição Formatada:** Apresenta um relatório limpo e organizado de todas as propriedades cadastradas ao final da execução.

## 📊 Dados Cadastrados por Carta

Cada carta do jogo possui os seguintes atributos:

1.  **Estado:** Uma letra de 'A' a 'H'.
2.  **Código da Carta:** Uma combinação da letra do estado com um número (ex: `A01`, `B02`).
3.  **Nome da Cidade:** O nome completo da cidade correspondente.
4.  **População:** Número de habitantes (inteiro).
5.  **Área:** Área total da cidade em quilômetros quadrados (ponto flutuante).
6.  **PIB:** Produto Interno Bruto da cidade (ponto flutuante).
7.  **Pontos Turísticos:** Quantidade de locais turísticos disponíveis na região (inteiro).

## 🛠️ Como Executar o Projeto

Para compilar e rodar este programa, você precisará de um compilador C instalado em sua máquina (como o `gcc`).

1. **Clone ou baixe o código fonte.**
2. **Abra o terminal** na pasta onde o arquivo está salvo.
3. **Compile o código** com o seguinte comando:
   ```bash
   gcc -o super_trunfo principal.c
   ```
4. **Execute o programa:**
   ```bash
   ./super_trunfo
   ```

## 🧠 Aprendizados Técnicos Aplicados

*   **Tratamento do Buffer (`stdin`):** Uso do `scanf(" ")` antes do `fgets` para consumir quebras de linha remanescentes no buffer, garantindo que o nome da cidade não seja pulado.
*   **Formatação de Saída:** Uso de especificadores como `%.2f` para limitar as casas decimais de valores como PIB e Área, tornando a leitura visualmente agradável.


```markdown
# Super Trunfo: Cadastro de Cartas de Cidades 🃏

Este projeto é um sistema em linguagem C para cadastrar e exibir os dados de duas cartas de cidades para um jogo estilo "Super Trunfo". O programa calcula automaticamente a **Densidade Populacional** e o **PIB per Capita** de cada cidade com base nos dados fornecidos pelo usuário.

---

## 🛑 O Grande Aprendizado: Ordem de Execução (A Regra de Ouro)

O principal marco no desenvolvimento deste código foi entender como o computador processa as linhas de comando e ajustar a **posição dos cálculos matemáticos**. 

### Como foi feito na primeira tentativa (O Erro):
No início, os cálculos da densidade populacional e do PIB per capita foram colocados logo no topo do programa, logo após a criação das variáveis. 
* **O problema:** Como o C lê o código de forma sequencial (de cima para baixo), o programa tentava dividir a população pela área antes mesmo de o usuário digitar os valores. Como as variáveis ainda estavam vazias, o resultado dava sempre errado ou aparecia como `0.00` na tela.

### Como ficou após a correção (O Acerto):
Ao entender o problema, os blocos de cálculo foram movidos para **depois de todos os comandos de entrada (`scanf` e `fgets`)**.
* **O resultado:** Dessa forma, o programa só faz as divisões quando as variáveis já estão preenchidas com os números reais digitados pelo usuário, gerando os resultados perfeitos.

> 💡 **Regra para a vida em C:** Primeiro o programa coleta os dados, depois faz as contas, e só no final mostra o resultado na tela.

---

## 🛠️ Outras Evoluções no Código

Durante o desenvolvimento, o código também foi otimizado para corrigir pequenos travamentos na leitura dos dados:

1. **Ajuste na Entrada dos Dados:**
   - Foi corrigido o formato de leitura dos pontos turísticos para garantir que o programa reconhecesse corretamente o número digitado como um valor inteiro.
   
2. **Correção do Bug de Pular Perguntas:**
   - Na primeira tentativa, o programa pulava a digitação do "Nome da Cidade". Isso foi corrigido adicionando uma limpeza no buffer do teclado (`while (getchar() != '\n');`) logo antes do comando `fgets`. Isso apaga o "Enter" da memória e impede que o programa pule linhas.

3. **Formatação Visual:**
   - A exibição da População foi ajustada para não mostrar casas decimais (já que não existem "meias" pessoas), deixando o relatório final muito mais limpo e bonito.

---

## 🧮 Fórmulas Aplicadas

* **Densidade Populacional:** Mede quantos habitantes vivem por quilômetro quadrado.
  $$\text{Densidade Populacional} = \frac{\text{População}}{\text{Área}}$$

* **PIB per Capita:** Mede a riqueza média de cada cidadão daquela cidade.
  $$\text{PIB per Capita} = \frac{\text{PIB}}{\text{População}}$$

```
# 🃏 Super Trunfo: Países e Cidades (Em C)

Este é um jogo interativo baseado no clássico **Super Trunfo**, desenvolvido em linguagem C. O programa permite o cadastro de duas cartas representando diferentes cidades brasileiras ou globais, calcula indicadores socioeconômicos importantes e realiza o confronto direto de atributos para determinar a carta vencedora.

## 🚀 Funcionalidades

- **Cadastro Dinâmico:** Entrada de dados via console para duas cartas distintas.
- **Cálculo de Indicadores:** O sistema gera automaticamente:
  - **Densidade Populacional:** Razão de habitantes por quilômetro quadrado ($hab/km²$).
  - **PIB per Capita:** Divisão do PIB total pelo número de habitantes da região.
  - **Super Poder:** Uma pontuação global unificada que mede a força total da carta.
- **Sistema de Confronto:** Comparação direta de todos os dados cadastrados indicando o vencedor de cada rodada.

---

## 🏆 Regras de Comparação e o "Super Poder"

As regras seguem a lógica matemática ideal para cada tipo de estatística regional:

1. **Atributos Convencionais (Maior Vence):** Para *População, Área, PIB, Pontos Turísticos* e *PIB per Capita*, a carta com o **maior valor** ganha a disputa.
2. **Densidade Populacional (Menor Vence):** Cidades menos saturadas demograficamente ganham o ponto. Portanto, o **menor valor** vence.
3. **O Super Poder:** É a força total da carta. Para balancear o fato de que uma densidade populacional menor é mais benéfica, o cálculo inverte esse peso matematicamente:

$$Super Poder = População + Área + PIB + Pontos Turísticos + PIB\ per\ Capita + \left(\frac{1}{Densidade}\right)$$

---

## 💻 Estrutura de Entrada de Dados

Para cada carta, o usuário deverá preencher os seguintes dados no terminal:
* **Estado:** Uma letra de `A` a `H`.
* **Código da Carta:** Uma letra seguida de dois algarismos (Ex: `A01`, `B02`).
* **Nome da Cidade:** Permite nomes compostos com espaços (Ex: `São Paulo`).
* **População:** Quantidade total de habitantes (utiliza inteiros longos para grandes metrópoles).
* **Área:** Extensão territorial em $km²$.
* **PIB:** Produto Interno Bruto em bilhões de reais.
* **Pontos Turísticos:** Quantidade de locais de interesse.

---

## 🛠️ Detalhes Técnicos de Implementação

* **Tratamento de Buffer (`scanf`):** O código utiliza filtros avançados como `scanf(" %[^\n]s", ...)` que limpam automaticamente quebras de linha anteriores residuais e permitem a captura de nomes de cidades compostos sem que o programa pule etapas.
* **Casting de Tipos:** Conversões explícitas de tipo `(float)` são feitas dinamicamente nas operações de divisão, impedindo que o compilador C descarte as casas decimais ao dividir variáveis inteiras de população (`unsigned long int`).
Este projeto é de uso livre para fins acadêmicos e de estudo.
# CartaSuperTrunfo
# 🃏 Jogo Super Trunfo - Países e Cidades (Em C)

Este é um jogo interativo baseado no clássico **Super Trunfo**, desenvolvido na linguagem C para rodar diretamente no terminal. O projeto simula o cadastro de duas cartas com propriedades geográficas/econômicas de cidades e permite que o jogador dispute uma rodada contra o computador escolhendo qual atributo comparar.

## 📋 Funcionalidades do Projeto

*   **Cadastro de Cartas Dinâmico:** O usuário insere dados detalhados para duas cartas (Estado, Código, Nome da Cidade, População, Área, PIB e Pontos Turísticos).
*   **Cálculos Automáticos (Métricas Avançadas):**
    *   **Densidade Populacional:** $\text{População} \div \text{Área}$.
    *   **PIB per Capita:** $\text{PIB} \div \text{População}$.
    *   **Super Poder:** Soma de todas as propriedades da carta (com a densidade populacional invertida para manter o equilíbrio).
*   **Escolha Inteligente de Cartas:** O jogador escolhe qual carta deseja usar para representá-lo no duelo.
*   **Menu Interativo de Atributos:** Permite ao jogador selecionar o atributo que definirá o vencedor da partida.
*   **Lógica Customizada de Vitória:** O sistema processa automaticamente empates e regras especiais onde o "menor valor vence".

## ⚖️ Regras de Comparação

O jogo adota regras matemáticas distintas dependendo do atributo escolhido no menu:
1.  **Atributos Padrão (Maior Vence):** Para *População*, *Área*, *PIB*, *Pontos Turísticos* e *PIB per Capita*, a carta que tiver o **maior valor numérico** vence o duelo.
2.  **Densidade Populacional (Menor Vence):** Seguindo a lógica do mundo real, no caso da densidade populacional, a cidade menos congestionada (com o **menor valor numérico**) é declarada a vencedora.

## 🛠️ Como Executar o Projeto

Você precisará de um compilador C (como o `gcc`) configurado em seu ambiente de desenvolvimento.

### Passo a Passo no Terminal

1.  Salve o código do jogo em um arquivo chamado `super_trunfo.c`.
2.  Abra o terminal na pasta onde salvou o arquivo e faça a compilação:
```bash
    gcc super_trunfo.c -o super_trunfo
    ```
3.  Execute o programa:
    *   **Linux/macOS:**
```bash
        ./super_trunfo
        ```
*   **Windows (CMD/PowerShell):**
```cmd
        super_trunfo.exe
        ```

## 💻 Estrutura Técnica do Código

O código foi otimizado para evitar repetições desnecessárias de exibição na tela. Ele utiliza:
*   `scanf(" %[^\n]s", ...)` para permitir a leitura correta de nomes de cidades compostos (com espaços).
*   `unsigned long int` com a formatação `%lu` para garantir o armazenamento adequado de populações de grandes metrópoles.
*   Estruturas condicionais (`switch` e `if-else`) acopladas a operadores lógicos (`&&` e `||`) para avaliar as condições de vitória do jogador e do computador em blocos limpos e de fácil manutenção.

## 🚀 Próximas Atualizações (Ideias de Melhorias)

*   **Implementar o Super Poder:** Adicionar o caso `case 7` dentro do menu de escolhas de atributos para habilitar o duelo usando a variável calculada `super_poder`.
*   **Loop de Jogo (`do-while`):** Permitir que o usuário jogue múltiplas partidas ou cadastre novas cartas sem que o terminal feche automaticamente ao final.
*   **Inteligência Artificial (IA) para o Rival:** Fazer com que o computador escolha o próprio atributo quando for o turno dele de jogar.
