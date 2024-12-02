# AvaliacaoFinal

# Sistema de Gerenciamento de Produtos

Este projeto é um sistema simples de gerenciamento de produtos, desenvolvido em C. Ele permite realizar as seguintes operações em um catálogo de produtos:

Inserir novos produtos.
Remover produtos existentes.
Buscar produtos pelo nome.
Exibir produtos agrupados por categoria.
Ordenar produtos por nome (usando o método de Bolha).
Ordenar produtos por preço (usando o método de Seleção).
Os produtos são armazenados em uma tabela hash, que é carregada a partir de um arquivo de texto (produtos.txt).

Estrutura do Sistema
Arquitetura do Código
O programa utiliza:

Tabela hash: Para armazenar e gerenciar os produtos, utilizando o nome do produto como chave.
Estrutura de produto: Cada produto possui:
Nome
Categoria
Preço
Colisões na tabela hash: Resolvidas com a técnica de encadeamento (listas ligadas).
Funcionalidades
1. Inserção de Produto
Adiciona um novo produto à tabela hash com base em seu nome, categoria e preço. O índice é calculado utilizando uma função hash.

2. Remoção de Produto
Remove um produto da tabela hash, utilizando seu nome como identificador. Caso o produto não seja encontrado, exibe uma mensagem de erro.

3. Busca de Produto
Realiza a busca por um produto utilizando seu nome. Retorna as informações do produto ou uma mensagem indicando que ele não foi encontrado.

4. Exibição de Produtos por Categoria
Organiza e exibe os produtos agrupados por suas categorias. As categorias são pré-definidas (como "Eletrônicos", "Eletrodomésticos", etc.).

5. Ordenação de Produtos
Por Nome: Utiliza o Método de Bolha para ordenar os produtos alfabeticamente.
Por Preço: Utiliza o Método de Seleção para ordenar os produtos em ordem crescente de preço.
6. Carregar Produtos de Arquivo
Os produtos são lidos de um arquivo (produtos.txt), que deve estar no formato:

arduino
Copiar código
Nome do Produto,Categoria,Preço
Exemplo:

sql
Copiar código
Smartphone Galaxy,Eletrônicos,1999.99
Geladeira Frost Free,Eletrodomésticos,2999.99
Perfume Masculino,Beleza,149.99
Como Usar
1. Pré-requisitos
Compilador C (ex.: GCC).
Um arquivo chamado produtos.txt com os produtos para carregar.
2. Compilar e Executar
Compile o programa:
bash
Copiar código
gcc -o gerenciamento_produtos gerenciamento_produtos.c
Execute o programa:
bash
Copiar código
./gerenciamento_produtos
3. Menu de Operações
Ao executar o programa, um menu será exibido:

markdown
Copiar código
--- Sistema de Gerenciamento de Produtos ---
1. Inserir produto
2. Remover produto
3. Buscar produto
4. Exibir produtos por categoria
5. Ordenar produtos por nome
6. Ordenar produtos por preço
7. Sair
Escolha uma opção:
4. Arquivo produtos.txt
Deve conter os produtos no formato:
arduino
Copiar código
Nome do Produto,Categoria,Preço
Estrutura do Código
Funções Principais
Tabela Hash

unsigned int hash(char *key): Calcula o índice da tabela hash.
Produto *hashTable[TABLE_SIZE]: Estrutura principal que armazena os produtos.
Operações Básicas

void inserirProduto(char *nome, char *categoria, float preco): Insere um produto.
void removerProduto(char *nome): Remove um produto.
Produto *buscarProduto(char *nome): Busca um produto pelo nome.
Exibição e Ordenação

void exibirProdutosPorCategoria(): Exibe produtos agrupados por categoria.
void ordenarPorNome(): Ordena os produtos por nome usando o Método de Bolha.
void ordenarPorPreco(): Ordena os produtos por preço usando o Método de Seleção.
Carregamento de Arquivo

void carregarProdutosDeArquivo(const char *fileName): Lê os produtos do arquivo produtos.txt e os insere na tabela hash.
Menu

void menu(): Gerencia a interação do usuário com o sistema.
Exemplos
Exibição de Produtos por Categoria
Exemplo de saída:

yaml
Copiar código
--- Produtos Cadastrados por Categoria ---

Categoria: Eletrônicos
  Nome: Smartphone Galaxy, Preço: 1999.99
  Nome: Smart TV 4K, Preço: 3299.99

Categoria: Eletrodomésticos
  Nome: Geladeira Frost Free, Preço: 2999.99

Categoria: Beleza
  Nome: Perfume Masculino, Preço: 149.99
...
Ordenação por Nome
yaml
Copiar código
--- Produtos Ordenados por Nome ---
Nome: Fritadeira Airfryer, Categoria: Eletrodomésticos, Preço: 499.99
Nome: Geladeira Frost Free, Categoria: Eletrodomésticos, Preço: 2999.99
Nome: Smartphone Galaxy, Categoria: Eletrônicos, Preço: 1999.99
...
Ordenação por Preço
yaml
Copiar código
--- Produtos Ordenados por Preço ---
Nome: Batom Vermelho, Categoria: Beleza, Preço: 19.99
Nome: Creme Hidratante, Categoria: Beleza, Preço: 24.99
Nome: Base Líquida Matte, Categoria: Beleza, Preço: 29.99
...
Observações
Colisões na Tabela Hash: Resolvidas por meio de listas ligadas.
Limitações:
Tamanho fixo da tabela hash.
Lista de categorias é fixa no código.
Extensões possíveis:
Salvar alterações no arquivo.
Adicionar suporte para novas categorias dinamicamente.
