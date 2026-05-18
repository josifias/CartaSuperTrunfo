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

## 📝 Licença

Este projeto é de uso livre para fins acadêmicos e de estudo.
# CartaSuperTrunfo
