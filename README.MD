# Banco1
# Banco1
-- criando banco de dados
create database bdteste;

-- usar banco de dados

use bdteste;

-- criar tabelas
create table clientes (
codigo int primary key,
 nome varchar (100),
 email varchar (200),
 datanaci date
);

-- alter table clientes
 alter table clientes add cpf varchar(11);
 
 -- CRIAR TABELA produtos
 create table produtos (
codigo int primary key,
nome varchar(100),
preco decimal(10,2)
);
-- criar tabelas 
create table faturas (
codigo int primary key,
 dataCriacao date,
 valorFatura decimal (10,2)
);


-- auterar nome de coluna
alter table produtos rename column nome to nomeProdutos;




---------------------------------------------------------------------------




exercicios  complementares
create database exerciciocomplementar; -- criar database

use exerciciocomplementar; -- usar database
-- 1. Criação da tabela Funcionarios
CREATE TABLE Funcionarios (
    ID INT PRIMARY KEY,-- ID do funcionário, chave primária
    Nome VARCHAR(50),-- Nome do funcionário
    Sobrenome VARCHAR(50),-- Sobrenome do funcionário
    Salario DECIMAL(10, 2)-- Salário do funcionário
);

-- 2. Adicionando coluna DataNascimento à tabela Funcionarios
ALTER TABLE Funcionarios
ADD DataNascimento DATE;-- Data de nascimento do funcionário

-- 3. Criação da tabela Departamentos
CREATE TABLE Departamentos (
    ID INT PRIMARY KEY,-- ID do departamento, chave primária
    Nome VARCHAR(50)-- Nome do departamento
);

-- 4. Adicionando coluna IDDepartamento à tabela Funcionarios
ALTER TABLE Funcionarios
ADD IDDepartamento INT;-- ID do departamento associado ao funcionário

-- 5. Criação da tabela Projetos
CREATE TABLE Projetos (
    ID INT PRIMARY KEY,-- ID do projeto, chave primária
    NomeProjeto VARCHAR(100)-- Nome do projeto
);

-- 6. Criação da tabela Alocacoes
CREATE TABLE Alocacoes (
    ID INT PRIMARY KEY,-- ID da alocação, chave primária
    IDFuncionario INT,-- ID do funcionário (chave estrangeira)
    IDProjeto INT,-- ID do projeto (chave estrangeira)
    FOREIGN KEY (IDFuncionario) REFERENCES Funcionarios(ID), -- Chave estrangeira para Funcionarios
    FOREIGN KEY (IDProjeto) REFERENCES Projetos(ID)          -- Chave estrangeira para Projetos
);

-- 7. Renomeando a coluna Sobrenome para Apelido na tabela Funcionarios
ALTER TABLE Funcionarios
RENAME COLUMN Sobrenome TO Apelido; -- Renomeia a coluna

-- 8. Criação da tabela Clientes
CREATE TABLE Clientes (
    ID INT PRIMARY KEY,-- ID do cliente, chave primária
    NomeCliente VARCHAR(100)-- Nome do cliente
);

-- 9. Adicionando coluna IDCliente à tabela Projetos
ALTER TABLE Projetos
ADD IDCliente INT;-- ID do cliente associado ao projeto

-- 10. Criação da tabela Enderecos
CREATE TABLE Enderecos (
    ID INT PRIMARY KEY,-- ID do endereço, chave primária
    Rua VARCHAR(100),-- Rua do endereço
    Cidade VARCHAR(50),-- Cidade do endereço
    CEP VARCHAR(10)-- CEP do endereço
);

-- 11. Adicionando coluna IDEndereco à tabela Funcionarios
ALTER TABLE Funcionarios
ADD IDEndereco INT;-- ID do endereço associado ao funcionário

-- 12. Renomeando a coluna NomeCliente para NomeEmpresa na tabela Clientes
ALTER TABLE Clientes
RENAME COLUMN NomeCliente TO NomeEmpresa; -- Renomeia a coluna

-- 13. Criação da tabela Pedidos
CREATE TABLE Pedidos (
    ID INT PRIMARY KEY, -- ID do pedido, chave primária
    DataPedido DATE  -- Data do pedido
);

-- 14. Adicionando coluna IDCliente à tabela Pedidos
ALTER TABLE Pedidos
ADD IDCliente INT;  -- ID do cliente associado ao pedido

-- 15. Criação da tabela ItensPedido
CREATE TABLE ItensPedido (
    ID INT PRIMARY KEY, -- ID do item do pedido, chave primária
    IDPedido INT,  -- ID do pedido (chave estrangeira)
    IDProduto INT, -- ID do produto (chave estrangeira)
    FOREIGN KEY (IDPedido) REFERENCES Pedidos(ID),   -- Chave estrangeira para Pedidos
    FOREIGN KEY (IDProduto) REFERENCES Produtos(ID)   -- Chave estrangeira para Produtos
);

-- 16. Renomeando a coluna NomeProduto para DescricaoProduto na tabela Produtos
ALTER TABLE Produtos
RENAME COLUMN NomeProduto TO DescricaoProduto; -- Renomeia a coluna

-- 17. Criação da tabela Estoques
CREATE TABLE Estoques (
    ID INT PRIMARY KEY, -- ID do estoque, chave primária
    Quantidade INT -- Quantidade disponível
);

-- 18. Adicionando coluna IDProduto à tabela Estoques
ALTER TABLE Estoques
ADD IDProduto INT; -- ID do produto associado ao estoque

-- 19. Criação da tabela Vendas
CREATE TABLE Vendas (
    ID INT PRIMARY KEY, -- ID da venda, chave primária
    DataVenda DATE -- Data da venda
);

-- 20. Adicionando coluna IDCliente à tabela Vendas
ALTER TABLE Vendas
ADD IDCliente INT; -- ID do cliente associado à venda
