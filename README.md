# eEDB-011 - T1

Trabalho 01 ministrado pelo professor Leandro Mendes Ferreira no segundo semestre de 2022 - Ingestão de Dados.

O trabalho consiste em ingerir dados de um CSV e uma API utilizando ferramentas visuais, criar uma tabela fato utilizando esquema estrela e disponibilizar 3 gráficos utilizando um *dashboard*.

## 🚀 Etapas do projeto

Definimos os seguintes passos:
* Download dos dados de Ranking de Instituições por Índice de Reclamações através de csv;
* Definição da utilização do programa Automation Edge;
* Criação do Amazon Relational Database Service utilizando uma conta de estudante;
* Acesso aos dados de tarifas através de API Rest;
* Construção do pipeline de dados com ETL;
* Geração das tabelas utilizando SQL no intuito de montar uma tabela fato  (DBeaver);
* Inserção dos dados gerados nas tabelas no DW;
* Geração dos gráficos através de dados inseridos no Database.


## 📋 Arquitetura mínima para entrega

* Ferramenta de ETL Padrão;
* Base de dados intermediária (Stage) em uma base de dados relacional;
* Data Warehouse final;
* Banco de dados relacional ou banco de dados específico para DW;
* Postgre, MySQL, Pinot, Druid;
* Modelagem Star Schema;
* Dashboard.

## 🔧 Projeto

### 1. Dados

Foram utilizados os dados mais recentes (2020, 2121) de duas bases governamentais:

1. [Ranking de Instituições por Índice de Reclamações](https://dados.gov.br/dataset/ranking-de-instituicoes-por-indice-de-reclamacoes)
2. [Tarifas Bancárias - por Segmento e por Instituição](https://dados.gov.br/dataset/tarifas-bancarias-por-segmento-e-por-instituicao)

Os dados obtidos estão disponíveis por trimestre.

### 2. Fluxo de leitura

Através Ranking de Instituições por Índice de Reclamações, foi construído no programa *Automation Edge* o fluxo para leitura das tarifas por meio de API Rest:

![AutomationEdge_Fluxo](/2-AutomationEdge/AutomationEdge_Fluxo.png)

A unificação dos arquivos `1-Dados\2020*.csv` e `1-Dados\2021*.csv` compõe o arquivo `1-Dados\Ranking_Reclamacoes_2020_2021.csv`. Após o fluxo via Rest o arquivo com a tarifa sumarizada está em `1-Dados\Tarifas_Intituicoes.csv`. Entretanto esse não é o arquivo final.

Disponibilizamos as tarifas de cada instituição com a url obtida em `1-Dados\Tarifas_Intituicoes.csv`.

### 3. Star Schema

Para cada CNPJ disponibilizado sumarizou-se as tarifas agrupando por `Ano`, `Trimestre` e `CNPJ` e foi criada uma tabela fato a fim de disponibilizarmos informações visuais dos dados.

![Star_Schema](/1-Dados/Star_Schema.png)

Os códigos utilizados para criação da tabela estão diponíveis em `2-AutomationEdge\ComandosSQL.docx`.

### 4. *RDS Amazon*

Utilizamos o serviço de estudante da *Amazon RDS* para armazenamento dos arquivos e os acessamos através do programa `DBeaver`.

![DBeaver](/1-Dados/DBeaver.png)

### 5. *Dashboards*

Por meio do Grafana foi possível acessarmos o RDS montado e populado para extração de informações.

![Dashboard_Grafana](/3-Grafana/Dashboard_Grafana.png)


## 🛠️ Construído com

* [DBeaver](https://dbeaver.io/download/) - O programa utilizado para acesso ao banco de dados;
* [AutomationEdge](https://automationedge.com.br/) - Programa para fluxo de dados ETL;
* [Draw.io](https://app.diagrams.net/) - Programa para desenvolvimento do modelo estrela;
* [Grafana](https://grafana.com/) - Programa para desenvolvimento dos dashboards;

## ✒️ Autores

* [Vitor Marques](https://github.com/vitormrqs)
* [Wellington Cassio Faria](https://github.com/wellicfaria)
* [Rodrigo Vitorino](https://github.com/digaumlv)
* [Thais Nabe](https://github.com/thaisnabe)
* [Wesley Lourenço Barbosa](https://github.com/wesleyloubar)
