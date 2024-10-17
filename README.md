-- PRIMEIROS CÓDIGOS NO SQL

-- Determinar quais colunas dos dados serão exibidos nos resultados: SELECT
-- Determinar qual Tabela será exibido nos resultados: FROM
-- Selecionando todas as colunas de uma tabela (*)

-- select * from [tabela ou banco.tabela];
select * from base.produtos; -- Se o banco de dados não estiver como base
select * from produtos; -- Se o banco de dados estiver como base

-- Selecionando algumas colunas de uma tabela 
-- Alterar nome de colunas e Tabelas: AS

-- select [coluna1, coluna2...] from [tabela];
select 
Nome as Nome_Cliente, 
Email, 
Telefone 
from clientes;



-- Trabalhas com valores distintos: DISTINCT

select Marca_Produto from produtos; -- Devolve todas as marcas dos produtos até os repetidos
select distinct Marca_Produto from produtos; -- Devolve as marcas distintas sem repetições



-- Ordernar (numérica ou alfabética) as informações de uma tabela: ORDER BY
-- Crescente: ASC
-- Decrescente: DESC

-- order by [coluna] asc/desc;
select * from produto
order by Preco_Unit asc;

-- order by [coluna1, coluna 2];
select * from clientes
order by Nome asc, Sobrenome asc; - Sem o asc/desc ele fará uma ordenação lógica



-- Para visualizar uma qtd de linhas (ranking): LIMIT

select * produtos 
order by Preco_Unit desc
limit (5); -- Exibirá as 5 primeiras linhas dos preços dos produtos em ordem decrescente



-- Filtrar dados de uma tabela: WHERE

--where [coluna] 'condição'
select * from clientes
where Qtd_Filhos > 0;

select * from clientes
where Renda_Anual >= 50000
order by Renda_Anual asc;

select * from clientes
where Escolaridade = 'Parcial';



--Filtros com mais de uma condição: AND, OR, IN BETWEEN

select * from clientes
where Sexo = 'M' and Qtd_Filhos > 0
order by Qtd_Filhos; -- comando AND filtra duas condições simultaneamente

select * from produtos
where Marca_Produto = 'DELL' or Preco_Unit >=1000; -- comando OR filtra uma condição ou outra

select * from produtos
where Marca_Produto in ('DELL', 'SANSUNG', 'ALTURA'); -- comando in tem o mesmo contexto do or, só que ele é utilizado quando a mais de 2 condições

select * from produtos
Where Preco_Unit between 1000 and 3000; -- comando between tem o mesmo contexto do and, simplifica o código quando a condição está entre intervalos



-- Filtrar dados de uma tabela a partir de um padrão: LIKE




