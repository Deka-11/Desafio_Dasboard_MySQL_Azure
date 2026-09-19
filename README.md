# Processando e Transformando Dados com Power BI

Projeto desenvolvido como parte da Formação **Power BI Analyst da DIO**.

## Sobre o projeto

O objetivo deste desafio foi integrar uma base de dados MySQL ao Power BI, realizar o tratamento e a transformação dos dados e criar um relatório para análise das informações da base **Company**.

O projeto original da DIO propõe a utilização de uma instância MySQL no **Microsoft Azure**.

Como não tive acesso ao Azure, adaptei essa etapa utilizando uma instância local do MySQL, mantendo as demais etapas propostas no desafio.

O fluxo utilizado no projeto foi:

**MySQL Local → MySQL Workbench → Power BI Desktop → Power Query → Modelo de Dados → Relatório**

## Tecnologias utilizadas

- MySQL
- MySQL Workbench
- Power BI Desktop
- Power Query
- SQL
- GitHub

## Base de dados

Foi utilizada a base de teste **Company**, disponibilizada nos materiais do desafio.

O schema utilizado foi:

`azure_company`

As principais tabelas trabalhadas foram:

- `employee`
- `department`
- `dependent`
- `dept_locations`
- `project`
- `works_on`

## Etapa SQL

No MySQL Workbench, a base foi criada e populada utilizando os scripts disponibilizados no projeto.

Também foram utilizadas consultas SQL para explorar, relacionar, filtrar e recuperar os dados necessários para análise.

Um exemplo de consulta utilizada foi:

```sql
SELECT
    CONCAT(Fname, ' ', Minit, ' ', Lname) AS Name,
    Dno AS Department,
    COUNT(*) AS Total_dependents
FROM employee AS e
INNER JOIN dependent AS d
    ON e.Super_ssn = d.Essn
GROUP BY 1, 2;
```

## Resultado da consulta

![Resultado da consulta SQL](images/SQLrecuperandodados.png)

## Integração com o Power BI

Após a preparação da base no MySQL, foi realizada a conexão com o Power BI Desktop.

As tabelas foram importadas e tratadas no Power Query.

## Transformação dos dados

No Power Query foram realizadas etapas de preparação e organização da base, incluindo:

- verificação dos tipos de dados;
- análise de valores nulos;
- tratamento de colunas;
- mescla entre tabelas;
- associação entre colaboradores, departamentos e gerentes;
- agrupamento de informações;
- remoção de colunas desnecessárias;
- criação de consultas auxiliares.

Essas transformações permitiram preparar os dados para a etapa de modelagem e análise.

## Modelo de dados

Após o tratamento, os relacionamentos entre as tabelas foram organizados no Power BI.

Foram utilizados relacionamentos entre tabelas como:

- `employee`
- `department`
- `dependent`
- `dept_locations`
- `project`
- `works_on`

Também foram utilizadas consultas auxiliares para complementar algumas análises.

## Relatório

Ao final do projeto, foi criado um relatório para caracterização da base Company.

Entre as informações apresentadas estão:

- total de departamentos;
- total de projetos;
- total de dependentes;
- total de colaboradores;
- total de horas;
- distribuição das horas;
- análise por departamento;
- análise de dependentes;
- análise dos colaboradores;
- filtros por departamento e localização.

### Dashboard

![Dashboard Power BI](images/desafio3.png)

## Adaptação do Azure

O desafio original utiliza uma instância MySQL hospedada no **Microsoft Azure**.

Como não tive acesso ao Azure, utilizei os arquivos disponibilizados no projeto e criei a base diretamente no MySQL local.

Assim, em vez do fluxo:

**Azure → MySQL → Power BI**

foi utilizado:

**MySQL Local → MySQL Workbench → Power BI**

Essa adaptação permitiu realizar normalmente as etapas de integração, transformação, modelagem e análise propostas no desafio.

## Principais aprendizados

Com este projeto foi possível praticar:

- criação e utilização de banco de dados MySQL;
- consultas SQL;
- integração entre MySQL e Power BI;
- transformação de dados com Power Query;
- mescla e organização de tabelas;
- criação de relacionamentos;
- modelagem de dados;
- construção de relatórios no Power BI.

## Estrutura do repositório


desafio-power-bi-mysql/
│
├── README.md
├── relatorio-company.pbix
├── script_bd_company.sql
├── insercao_de_dados_e_queries_sql.sql
│
└── images/
    ├── desafio3.png
    └── SQLrecuperandodados.png


## Referência

Projeto desenvolvido com base no desafio **Processando e Transformando Dados com Power BI**, da Formação **Power BI Analyst da DIO**.
