# Sistema de Gerenciamento de Supermercado

## Integrantes

- Alan Goveia Alves
- Gustavo Henrique Ramos Cesar Da Silva 

## Descrição do Sistema

O Sistema de Gerenciamento de Supermercado é uma aplicação desenvolvida em C# com Windows Forms, com o objetivo de auxiliar no controle de produtos, estoque, compras e emissão de nota fiscal.

O sistema permite cadastrar produtos, consultar, atualizar e excluir registros, além de realizar compras, adicionar produtos ao carrinho, calcular subtotal, desconto, total da compra e gerar uma nota fiscal em PDF.

## Funcionalidades

- Cadastro de produtos;
- Consulta de produtos;
- Atualização de produtos;
- Exclusão de produtos;
- Limpeza dos campos;
- Cadastro de imagem do produto;
- Listagem de produtos cadastrados;
- Filtro por nome e categoria;
- Adição de produtos ao carrinho;
- Remoção de produtos do carrinho;
- Controle automático de estoque;
- Finalização de compra;
- Emissão de nota fiscal;
- Exportação da nota em PDF.

## Tecnologias Utilizadas

- C#
- Windows Forms
- .NET
- MySQL
- MySql.Data
- Visual Studio
- System.Drawing.Printing

## Banco de Dados Utilizado

O banco de dados utilizado no projeto foi o MySQL.

Nome do banco:
sql
supermercado

##Script SQL de Criação do Banco e Tabela
CREATE DATABASE supermercado;

USE supermercado;

CREATE TABLE IF NOT EXISTS produtos (
    codigo VARCHAR(20) PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    categoria VARCHAR(100) NOT NULL,
    quantidade INT NOT NULL,
    preco DECIMAL(10,2) NOT NULL,
    data_cadastro DATE NOT NULL,
    imagem VARCHAR(255)
);

##Exemplo de Produtos para Teste
INSERT INTO produtos 
(codigo, nome, categoria, quantidade, preco, data_cadastro, imagem)
VALUES
('001', 'Arroz Branco 5kg', 'Alimentos', 50, 24.90, CURDATE(), ''),
('002', 'Feijão Carioca 1kg', 'Alimentos', 40, 8.99, CURDATE(), ''),
('003', 'Leite Integral 1L', 'Frios e Laticínios', 60, 5.49, CURDATE(), ''),
('004', 'Refrigerante Cola 2L', 'Bebidas', 35, 9.99, CURDATE(), ''),
('005', 'Detergente Neutro', 'Limpeza', 80, 2.99, CURDATE(), '');

##Como Configurar o Banco de Dados
1. Abra o MySQL Workbench, phpMyAdmin ou outro gerenciador MySQL.
2. Execute o script SQL de criação do banco.
3. Verifique se o banco supermercado foi criado.
4. Configure a classe Conexao.cs com os dados do seu MySQL.

private string dadosConexao =
    "server=localhost;" +
    "database=supermercado;" +
    "user=root;" +
    "password=;";
Caso seu MySQL tenha senha, altere o campo password.

##Como Executar o Projeto
1. Abra o projeto no Visual Studio.
2. Instale o pacote MySql.Data pelo NuGet.
3. Configure a conexão com o banco na classe Conexao.cs.
4. Execute o script SQL no MySQL.
5. Pressione F5 ou clique em Iniciar no Visual Studio.
6. A aplicação será aberta com as telas de cadastro, nova compra e nota fiscal.

##Usuário e Senha de Teste
Este sistema não possui tela de login.

Portanto, não existe usuário e senha de teste.

##Estrutura Principal do Projeto
Sistema_de_Gerenciamento_de_Supermercado/
│
├── Cadastro.cs
├── Nova_Compra.cs
├── Nota_Compra.cs
├── Conexao.cs
├── README.md
└── banco_de_dados.sql

## Observações
As imagens dos produtos são armazenadas localmente em uma pasta do sistema.
O banco de dados salva apenas o caminho da imagem.
A nota fiscal pode ser exportada em PDF.
O estoque é atualizado automaticamente ao adicionar ou remover produtos do carrinho.
