# eEDB-011---T1

Trabalho 01 ministrado pelo professor Leandro Mendes Ferreira no segundo semestre de 2022 - Ingestão de Dados

## 🚀 Começando

Definimos os seguintes passos:

- Download dos dados de Ranking de Instituições por Índice de Reclamações através de csv
- Definição da utilização do programa Automation Edge
- Criação do Data Warehouse na AWS
- Acesso aos dados de tarifas através de API Rest
- Construção do pipeline de dados com ETL
- Geração das tabelas utilizando SQL no intuito de montar uma tabela fato  (DBeaver)
- Inserção dos dados gerados nas tabelas no DW
- Geração dos gráficos através de dados inseridos no Database

Consulte **Implantação** para saber como implantar o projeto.

### 📋 Requerimentos

De que coisas você precisa para instalar o software e como instalá-lo?

```
    1. Separar os jobs:
        read.py
            - Leitura do csv
                - Escreve na RAW (S3)
            - Leitura da API
                 - Escreve na RAW (S3)
        clean.py
            - Impla os dados, escreve na  pasta TRUSTED (LIMPEZA DOS DADOS - dados limpos e tratados - CSV, PARQUET)
        insert_dados_bd.py
            - Do TRUSTED, deve-se jogar dentro do banco de dados realizar modelos TRUSTED para o modelo STAR SCHEMA em SQL
        Camanda de Visualização: Possível ter 3 gráficos no final do notebook. 
```

### 🔧 Instalação



## ⚙️ Executando os testes



### 🔩 Analise os testes de ponta a ponta


### ⌨️ E testes de estilo de codificação


## 📦 Desenvolvimento



## 🛠️ Construído com

Mencione as ferramentas que você usou para criar seu projeto

* [DBeaver](https://dbeaver.io/download/) - O programa utilizado para acesso ao banco de dados
* [AutomationEdge](https://automationedge.com.br/) - Programa para fluxo de dados ETL

## 🖇️ Colaborando

Por favor, leia o [COLABORACAO.md](https://gist.github.com/usuario/linkParaInfoSobreContribuicoes) para obter detalhes sobre o nosso código de conduta e o processo para nos enviar pedidos de solicitação.

## 📌 Versão

Nós usamos [SemVer](http://semver.org/) para controle de versão. Para as versões disponíveis, observe as [tags neste repositório](https://github.com/suas/tags/do/projeto). 

## ✒️ Autores

Mencione todos aqueles que ajudaram a levantar o projeto desde o seu início

* **Um desenvolvedor** - *Trabalho Inicial* - [umdesenvolvedor](https://github.com/linkParaPerfil)
* **Fulano De Tal** - *Documentação* - [fulanodetal](https://github.com/linkParaPerfil)

Você também pode ver a lista de todos os [colaboradores](https://github.com/usuario/projeto/colaboradores) que participaram deste projeto.

## 📄 Licença

Este projeto está sob a licença (sua licença) - veja o arquivo [LICENSE.md](https://github.com/usuario/projeto/licenca) para detalhes.

## 🎁 Expressões de gratidão

* Conte a outras pessoas sobre este projeto 📢
* Convide alguém da equipe para uma cerveja 🍺 
* Obrigado publicamente 🤓.
* etc.



