





# # E-commerce Business Intelligence Project

Projeto completo de Business Intelligence desenvolvido para um cenário fictício de e-commerce, cobrindo todas as etapas do pipeline de dados: modelagem OLTP, ETL, área de Stage, Data Warehouse e análise com Power BI.


## Features

- Modelagem OLTP
- Área Stage
- ETL com SSIS
- Tratamento de dados
- Banco de erros
- Data Warehouse
- SCD Tipo 2
- Carga incremental
- Dashboards Power BI

# fase 0 - DOCUMENTO DE REQUISITOS

A documentação completa do projeto está disponível na pasta DOCUMENTACAO:


# FASE 1 — MODELAGEM DO SISTEMA OPERACIONAL (OLTP) 

## Objetivo da fase:

Criar o banco transacional do e-commerce. Esse banco representa o sistema operacional da empresa, responsável pelas operações do dia a dia:

vendas, cadastro de clientes, cadastro de produtos, emissão de notas pagamentos....

O banco foi criado em modelo relacional normalizado para: 

Evitar redundância, garantir integridade, melhorar manutenção.


. Criação das tabelas operacionais

Tabelas:
- CLIENTE
- ENDERECO
- PRODUTO 
- CATEGORIA 
- FORNECEDOR 
- VENDEDOR 
- FORMA_PAGAMENTO
- NOTA_FISCAL 
- ITEM_NOTA

Uso de: Primary Key (PK), Foreign Key (FK), Integridade referencial, Estrutura normalizada.

Sistema focado em: Operações rápidas inserções atualizações transações Modelagem Relacional

Uso de: Entidades, relacionamentos, cardinalidade, Normalização.

## FASE 2 — CRIAÇÃO DA ÁREA STAGE

A Stage funciona como área temporária de processamento ETL.

Tabelas:

- ST_CLIENTE 
- ST_PRODUTO 
- ST_CATEGORIA 
- ST_VENDEDOR 
- ST_FORNECEDOR 
- ST_NOTA 
- ST_FATO 

Os dados foram extraídos do banco operacional utilizando: SQL Server Integration Services

Transformações realizadas:

- Limpeza de dados

Exemplo:

remoção de inconsistências ajuste de tipos Padronização

Exemplo:

Camel Case formatação textual Tratamento de NULL

Validação de dados incompletos.

Regras de negócio

Aplicação de lógica antes da carga no DW.

- Conceitos utilizados:  ETL(Extract, Transform, Load)

Camada intermediária para: limpeza auditoria preparação de dados Data Quality

_TRATAMENTO DE ERROS (BI_ERROR)-Regra implementada
Clientes sem endereço: não seguem para o DW são enviados para tabela de erro.

## FASE 3 — CONSTRUÇÃO DO DATA WAREHOUSE (DW) 
## Objetivo da fase: 

- Construir o ambiente analítico da empresa.
- Transformar os dados operacionais em dados estratégicos.

Uso de: Star Schema (modelo estrela), Criação das dimensões

Tabelas:

- DIM_CLIENTE 
- DIM_PRODUTO 
- DIM_FORNECEDOR 
- DIM_VENDEDOR 
- DIM_FORMA 
- DIM_NOTA 
- DIM_TEMPO 
- Criação da tabela fato

Estrutura da Tabela fato: FATO_VENDAS 

Armazena:

quantidade, valor total, lucro, custo, Uso de chaves surrogate

Campo:

IDSK Criação da dimensão tempo

A dimensão tempo foi criada via T-SQL contendo:

dia, mês, trimestre, nome do mês, estação do ano, fim de semana, Implementação de SCD

Campos:

INICIO, FIM

Uso de: Slowly Changing Dimension (Tipo 2) Conceitos utilizados Data Warehouse

Banco analítico voltado para:
- consultas, análise, indicadores

Modelo:
Fato no centro + Dimensões ao redor Tabela fato

Armazena métricas numéricas.

Tabela dimensão

Armazena contexto analítico.

Surrogate Key

Chave artificial do DW.

SCD Tipo 2

Controle histórico de alterações.

_CARGA INCREMENTAL

Procedure de carga incremental

- CARGA_FATO 

A procedure: identifica última data carregada, carrega apenas novos registros

Carga incremental.

Watermark

Controle temporal da carga.

Separação lógica dos dados.

# Observação final

Projeto desenvolvido com objetivo acadêmico e prático, simulando uma arquitetura corporativa completa de Business Intelligence aplicada a um cenário de e-commerce.

 ## Autora: Jeniffer Santos
 ## Estudante de Sistemas de Informação 
 ## Foco em Dados, BI e Engenharia de Dados
