# ERROS IDENTIFICADOS:
* Ocorre um pequeno erro ao tentar compilar o projeto devido a falta de uma biblioteca a string.h, para resolve-lo, basta incluir a biblioteca;

* Existe um erro ao utilizar da opção de atualizar o cliente (opção 5), o erro ocorre quando digitarmos uma string e não um número, seria interessante fazer a validação de inputs para evitar que o mesmo aconteça. Ao digitar uma string como input o sistema entra em loop infinito resultando no erro; 

* Ao registrar mais de 10 clientes no sistema ocorre um erro, este erro ocorre pois na função insere_cliente() existe uma condição que verifica se existe mais de 10 clientes registrados "if (total_clientes >= 10)", nesta condição, ao ser executada, ocorre um return indicando que a função não efetuara novos registros de clientes, e informa o usuário que a lista de clientes está cheia. Ao realizar esse return ocorre um problema no loop principal do código, para resolver este problema o indicado é modificar a lógica da condição, fazendo com que somente é feito o registro de clientes se a lista for menor que 10; Abaixo se encontra o código da função:
```
void insere_cliente() {
    if (total_clientes < 10) {
        printf("Insira um cliente:\n");
        scanf("%s", clientes[total_clientes]);
        total_clientes++;
    }
}
else {
        printf("A lista está cheia, não será feito o registro de um novo cliente\n");
}
```
* O mesmo erro de return ocorre na função insere_produto, as mesmas modificações feitas na função insere_cliente resolve o problema. Aqui está a função modificada:
```
void insere_produto() {
    if (total_produtos < 10) {
        printf("Insira um produto:\n");
        scanf("%s", produtos[total_produtos]);
        total_produtos++;
    }
    else {
        printf("A lista de produtos esta cheia, não é possível registrar novos produtos\n");
    }
}
```

# MELHORIAS A SEREM PROPOSTAS:
* Seria interessante adicionar a possibilidade de listar os produtos cadastrados para poder verificar a existência dos mesmos, bem como, a possibilidade de atualização dos mesmos;

* Fazer a validação de inputs, impedindo que em entradas de strings não é digitados números, e vice-versa;

* Seria interessante ao realizar a operação de atualizar o cliente, verificase se existe clientes na lista, caso não existir o sistema informa que não é possível atualizar clientes pois não possuem nenhum cliente registrado;

# ASPECTOS POSITIVOS:
* O código foi muito bem escrito, não possuo dificuldades de entende-lo e analisalo bem como modifica-lo;

* Não existe comentários em excesso, e os comentários quando existem são extremamente excelentes pois explicam certas condições do código que são fundamentais para o entendimento, como por exemplo, na função de excluir clientes;

* Interessante a ideia de utilizar matrizes para o armazenamento de clientes, em certos casos, permite a melhor estrutura do código;
