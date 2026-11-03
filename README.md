#  Desafio de Monitoramento de Temperatura

**Aluno:** Rafael Eliaquim Ramos Lima  
**Disciplina:** Algoritmos e Pensamento Computacional  
**Professora:** Karla Sartin  
**Título do projeto:** Monitoramento de Temperatura

---

##  1. Objetivo

Desenvolver, em linguagem C, um programa simples para monitorar leituras de temperatura.

O sistema permite definir um limite de temperatura e realizar várias leituras, verificando quando os valores ultrapassam o limite estabelecido.

O monitoramento é encerrado automaticamente quando são registradas três temperaturas consecutivas acima desse valor.

Ao final, o programa apresenta um relatório contendo a média, a maior e a menor temperatura, além da quantidade de leituras acima do limite.

##  2. Funcionamento do programa

### Limite de temperatura

No início do programa, o usuário informa o limite de temperatura desejado.

O valor precisa ser numérico. Caso seja digitada uma letra, símbolo ou outra entrada inválida, o programa apresenta uma mensagem de erro e solicita novamente o valor.

### Leituras de temperatura

Após definir o limite, o programa começa a solicitar as temperaturas do sensor.

As leituras são realizadas continuamente enquanto não ocorrerem três temperaturas consecutivas acima do limite.

Cada temperatura válida é utilizada para calcular a média, identificar a maior e a menor temperatura e verificar se o valor ultrapassou o limite.

### Tratamento de valores inválidos

O programa verifica o retorno da função `scanf()`.

Caso seja digitada uma entrada não numérica, o sistema exibe uma mensagem de erro e solicita um novo valor.

As entradas inválidas não são consideradas nos cálculos.

### Temperaturas acima do limite

Após cada leitura válida, o programa compara a temperatura informada com o limite definido, utilizando a condição:

```c
if (temperatura > limite)
```

Quando a temperatura ultrapassa o limite, o programa aumenta a quantidade de temperaturas acima do limite e o contador de temperaturas consecutivas.

### Contagem de temperaturas consecutivas

A variável `consecutivas` controla quantas temperaturas acima do limite ocorreram em sequência.

- Quando a temperatura ultrapassa o limite, o contador aumenta em 1.
- Quando a temperatura está dentro ou abaixo do limite, a contagem volta para zero.

### Encerramento do monitoramento

O programa encerra automaticamente quando são registradas três temperaturas consecutivas acima do limite.

Após o encerramento, é apresentado um relatório com:

- Quantidade total de leituras;
- Média das temperaturas;
- Maior temperatura registrada;
- Menor temperatura registrada;
- Quantidade de temperaturas acima do limite.

## 3. Estruturas de repetição utilizadas

Foram utilizadas as estruturas `do...while` e `while`.

- **do...while:** utilizado para solicitar e validar o limite de temperatura, garantindo que essa etapa aconteça pelo menos uma vez.
- **while:** utilizado para manter o monitoramento ativo enquanto não ocorrerem três temperaturas consecutivas acima do limite.
- **while:** também utilizado para limpar entradas inválidas digitadas pelo usuário.

##  4. Como executar o programa

O programa foi desenvolvido e testado utilizando o compilador online OnlineGDB.

### Executando pelo OnlineGDB

1. Acesse o [OnlineGDB](https://www.onlinegdb.com/).
2. Selecione a linguagem C.
3. Cole o conteúdo do arquivo `monitoramento.c`.
4. Clique em **Run** para compilar e executar.

### Executando localmente com GCC

Também é possível compilar e executar o programa utilizando o GCC:

```bash
gcc monitoramento.c -o monitoramento
./monitoramento
```

##  5. Testes realizados

### Teste 1 — Validação de entradas inválidas

Foram inseridas entradas não numéricas tanto na definição do limite quanto durante as leituras de temperatura.

**Entradas utilizadas:** `abc` e `teste`.

**Resultado:** o programa identificou as entradas inválidas, exibiu uma mensagem de erro e solicitou novos valores sem interromper a execução.

### Teste 2 — Temperaturas acima do limite, porém não consecutivas

Foi definido o limite de 80 graus.

Foram informadas temperaturas acima e abaixo desse valor.

**Resultado:** o programa identificou as temperaturas acima do limite, mas não encerrou o monitoramento porque elas não ocorreram três vezes consecutivas.

### Teste 3 — Três temperaturas consecutivas acima do limite

Foi definido o limite de 80 graus.

Foram informadas três temperaturas consecutivas acima desse valor.

**Resultado:** o contador chegou a três leituras consecutivas acima do limite. O programa exibiu o alerta, apresentou o relatório final e encerrou automaticamente.

## 6. Evidências

As evidências dos testes realizados estão disponíveis na pasta `evidencias` do repositório:

- `teste01.png` — Validação de entradas inválidas.
- `teste02.png` — Temperaturas acima do limite, porém não consecutivas.
- `teste03.png` — Três temperaturas consecutivas acima do limite.

## 7. Arquivo .gitignore

O projeto utiliza um arquivo `.gitignore` para evitar o envio de arquivos executáveis, temporários e de compilação desnecessários ao GitHub.

O código-fonte `monitoramento.c` e a pasta `evidencias`, contendo os registros dos três testes realizados, são mantidos no repositório para documentação da atividade.

##  8. Questão final de reflexão

Utilizei o `do...while` para validar o limite, porque essa etapa precisa acontecer pelo menos uma vez.

O `while` foi usado no monitoramento, pois verifica antes se ainda não ocorreram três temperaturas consecutivas acima do limite.

A diferença foi importante porque o `do...while` testa a condição depois da execução, enquanto o `while` testa antes.

---

⭐ **Projeto desenvolvido em linguagem C para praticar estruturas de repetição, validação de dados, condicionais e operações matemáticas.**
