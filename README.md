# Projeto-Final-Henrique-Ismael-e-Diego

###📝Introdução
Este documento descreve um notebook Jupyter contendo código Python para realizar consultas a APIs web, manipular dados, e armazenar informações em um banco de dados SQLite. O código consiste em várias funções organizadas em seções, incluindo a criação de ambiente virtual, manipulação de banco de dados, extração de dados de APIs, transformação desses dados e a execução principal (`main`), bem como uma seção de carregamento (LOAD) para visualizar e verificar os dados no banco de dados SQLite.

## Ambiente Virtual
Para executar este código, é necessário criar um ambiente virtual Python. As bibliotecas necessárias estão listadas na seção de ambiente virtual, incluindo `virtualenv` e `virtualenvwrapper-win`.

📖 Bibliotecas Utilizadas
- `pandas`: Para manipulação e análise de dados.
- `requests`: Para fazer solicitações HTTP às APIs web.
- `sqlite3`: Para interação com o banco de dados SQLite.
- `datetime`: Para manipulação de datas e horas.
- `pprint`: Para a formatação bonita de saída no console.
- `plyer`: Para notificações no sistema.

## Funções

### 1. Função `alerta(nivel, base, etapa)`
Esta função gera alertas de erros com base nos parâmetros fornecidos.
- **Parâmetros:**
  - `nivel`: Inteiro indicando o nível de alerta.
  - `base`: Nome da base de dados ou API onde o erro ocorreu.
  - `etapa`: Etapa ou processo onde o erro foi gerado.
- **Retorno:**
  - `notificacao`: Objeto de notificação para alertas no sistema.

### 2. Funções de Banco de Dados
#### a. `inserir_dadosDB(df, nome_tabela)`
Esta função insere um DataFrame no banco de dados SQLite.
- **Parâmetros:**
  - `df`: DataFrame a ser inserido no banco de dados.
  - `nome_tabela`: Nome da tabela onde os dados serão inseridos.
- **Retorno:**
  - `True` se a inserção for bem-sucedida.

#### b. `ler_dadosDB(nome_tabela)`
Esta função lê uma tabela no banco de dados e retorna um DataFrame com os dados.
- **Parâmetros:**
  - `nome_tabela`: Nome da tabela a ser lida.
- **Retorno:**
  - `df`: DataFrame contendo os dados da tabela.

#### c. `sys_tables()`
Esta função retorna um DataFrame com os nomes das tabelas no banco de dados.
- **Retorno:**
  - `schema`: DataFrame contendo os nomes das tabelas no banco de dados.

### 3. Funções de Extração
#### a. `tipo_url(tipo, dado)`
Esta função retorna o endpoint da API de acordo com os parâmetros passados.
- **Parâmetros:**
  - `tipo`: Tipo de dado a ser extraído (cnpj, clima, cidade).
  - `dado`: Dado específico para a consulta na API.
- **Retorno:**
  - `url`: URL completa para a consulta na API.

#### b. `get_api(dado)`
Esta função retorna os dados do endpoint da API.
- **Parâmetros:**
  - `dado`: URL completa para a consulta na API.
- **Retorno:**
  - `data_json`: Dados obtidos da API no formato JSON.

### 4. Funções de Transformação
#### a. `trata_dataframe(tipo, dataframe)`
Esta função recebe um tipo de dado e um DataFrame e retorna um novo DataFrame com os dados tratados de acordo com o tipo.
- **Parâmetros:**
  - `tipo`: Tipo de dado (empresa, cidade, clima).
  - `dataframe`: DataFrame contendo os dados brutos da API.
- **Retorno:**
  - `dados`: DataFrame com os dados tratados.

### 5. Função Principal `main(cnpj)`
Esta função principal realiza a chamada de todas as funções para obter, transformar e armazenar os dados.
- **Parâmetros:**
  - `cnpj`: CNPJ da empresa para a qual as informações serão consultadas.

## Execução e Uso
Após criar o ambiente virtual e instalar as bibliotecas necessárias, o código solicita o CNPJ da empresa ao usuário. Em seguida, ele chama a função `main(cnpj)` para obter os dados da empresa, da cidade associada ao CNPJ e informações climáticas sobre essa cidade. Os dados são então tratados e armazenados em um banco de dados SQLite chamado `coderhouse.db`. Após a execução, os dados são lidos do banco de dados e exibidos como um DataFrame para verificação.

## Conclusão
Este notebook fornece uma estrutura para consulta de APIs web, manipulação de dados e armazenamento em um banco de dados SQLite. Ele pode ser adaptado para diferentes tipos de consultas e necessidades de armazenamento de dados.
