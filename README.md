<strong> Ferramentas utilizadas: </strong> MySQL, SQL

<br> 

## SISTEMA DE GERENCIAMENTO DE HOTEL E SERVIÇOS

<br>

Projeto desenvolvido para a disciplina de Banco de Dados, com o objetivo de criar um sistema para gerenciar as principais funcionalidades necessárias para um hotel, como o cadastro de clientes, o controle de reservas e ocupações, a gestão de quartos, além da administração de serviços adicionais como restaurante, frigobar, massagens e os pagamentos. Utilizou-se o MySQL para o desenvolvimento do projeto, um sistema de gerenciamento de banco de dados relacional (SGBD).

<br>

### Ações:

1. Criação da base de dados e estruturação.

2.  Inserção de dados nas tabelas Restaurante, Massagem, Frigobar, Cliente, Reserva.
   
3. Aplicação de um acréscimo de 15% nas diárias dos quartos acima do 3º andar.
   
4. Diminuição de 40% no valor das diárias dos quartos que já não são mais ocupados há 2 anos.
   
5. Listagem do nome e sexo de todos os clientes por ordem alfabética.
   
6. Listagem do número de todos os quartos por ordem decrescente de andar e crescente de valor da diária.
  
7. Listagem do número de todos os quartos com valor da diária entre R$ 100 e R$ 150.
   
8. Listagem do CPF e o CEP de todos os clientes brasileiros residentes em “Curitiba”.

9. Listagem de todas as reservas de um determinado cliente.

10. Listagem dos números dos quartos que já foram ocupados algum dia.

11. Listagem do número das reservas que tiveram algum tipo de aprovação pelo gerente.

12. Listagem do número das reservas que fizeram uso do restaurante.

13. Listagem das reservas que foram pagas em dinheiro.

14. Listagem, em ordem alfabética, do nome de todos os clientes e a data de entrada de suas reservas.

15. Listagem do nome e o CPF de todos os clientes brasileiros.

16. Listagem do nome e o passaporte de todos os clientes estrangeiros.

17. Listagem do número da reserva e o nome do gerente de todas as reservas aprovadas.

18. Listagem do número da reserva, a descrição e o valor dos pratos consumidos por todas as ocupações.

19. Listagem do nome do cliente e o tipo de pagamento de todas as ocupações pagas.
    
20. Listagem do nome do cliente e os produtos utilizados nas massagens dos clientes que ficaram hospedados no último ano.

21. Listagem do nome do cliente, a data de nascimento e o andar do quarto em que ficaram hospedados os clientes nos últimos três meses.

22. Listagem do estado, o nome da cidade e o nome do cliente, para os clientes que se hospedaram nos últimos cinco anos.

<br>

### Tópicos:

- Manipulação de dados

```sql
UPDATE Quarto
SET VlrDiaria = VlrDiaria * 1.15
WHERE Andar > 3;
```

<br>

- Filtragem de dados

```sql
SELECT CPF, CEP
FROM ClienteBrasileiro
WHERE Cidade = 'Curitiba';
```

<br>

- Junção entre tabelas

```sql
SELECT C.Nome, TP.Descricao
FROM Cliente C
INNER JOIN Reserva R 
ON C.Id = R.ClienteId
INNER JOIN Ocupacao O 
ON R.Numero = O.ReservaNumero
INNER JOIN PagamentoOcupacao PO 
ON O.ReservaNumero = PO.ReservaNumero
INNER JOIN TipoPagamento TP 
ON PO.TipoPagamentoId = TP.Id;
```

<br> <br>


