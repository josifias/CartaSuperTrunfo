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
Este projeto é de uso livre para fins acadêmicos e de estudo.
# CartaSuperTrunfo
