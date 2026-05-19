# bi-microsoft-end-to-end-ssis-ssas-ssrs

       FASE 1 — MODELAGEM DO SISTEMA OPERACIONAL (OLTP)  Objetivo da fase

Criar o banco transacional do e-commerce.

Esse banco representa o sistema operacional da empresa, responsável pelas operações do dia a dia:

vendas
cadastro de clientes
cadastro de produtos
emissão de notas
pagamentos

O que foi desenvolvido
Criação do banco OLTP

Banco:

COMERCIO
Criação das tabelas operacionais

Tabelas:

CLIENTE
ENDERECO
PRODUTO
CATEGORIA
FORNECEDOR
VENDEDOR
FORMA_PAGAMENTO
NOTA_FISCAL
ITEM_NOTA

Uso de:
Primary Key (PK)
Foreign Key (FK)
Integridade referencial
Estrutura normalizada

O banco foi criado em modelo relacional normalizado para:

evitar redundância
garantir integridade
melhorar manutenção
Conceitos utilizados
Banco OLTP

(Online Transaction Processing)

Sistema focado em:

operações rápidas
inserções
atualizações
transações
Modelagem Relacional

Uso de:

entidades
relacionamentos
cardinalidade
Normalização

FASE 2 — CRIAÇÃO DA ÁREA STAGE

A Stage funciona como área temporária de processamento ETL.

Criação das tabelas STAGE

Tabelas:

ST_CLIENTE
ST_PRODUTO
ST_CATEGORIA
ST_VENDEDOR
ST_FORNECEDOR
ST_NOTA
ST_FATO
Extração dos dados do OLTP

Os dados foram extraídos do banco operacional utilizando:
SQL Server Integration Services

Transformações realizadas
Limpeza de dados

Exemplo:

remoção de inconsistências
ajuste de tipos
Padronização

Exemplo:

Camel Case
formatação textual
Tratamento de NULL

Validação de dados incompletos.

Regras de negócio

Aplicação de lógica antes da carga no DW.

Conceitos utilizados
ETL

(Extract, Transform, Load)

rea de Staging

Camada intermediária para:

limpeza
auditoria
preparação de dados
Data Quality

Tratamento de qualidade dos dados

_TRATAMENTO DE ERROS (BI_ERROR)-Regra implementada

Clientes sem endereço:

não seguem para o DW
são enviados para tabela de erro

FASE 3 — CONSTRUÇÃO DO DATA WAREHOUSE (DW)
Objetivo da fase

Construir o ambiente analítico da empresa.

Transformar os dados operacionais em dados estratégicos.

Modelagem dimensional

Uso de:

Star Schema (modelo estrela)
Criação das dimensões

Tabelas:

DIM_CLIENTE
DIM_PRODUTO
DIM_FORNECEDOR
DIM_VENDEDOR
DIM_FORMA
DIM_NOTA
DIM_TEMPO
Criação da tabela fato

Tabela:

FATO_VENDAS
Estrutura da fato

Armazena:

quantidade
valor total
lucro
custo
Uso de chaves surrogate

Campo:

IDSK
Criação da dimensão tempo

A dimensão tempo foi criada via T-SQL contendo:

dia
mês
trimestre
nome do mês
estação do ano
fim de semana
Implementação de SCD

Campos:

INICIO
FIM

Uso de:

Slowly Changing Dimension (Tipo 2)
Conceitos utilizados
Data Warehouse

Banco analítico voltado para:

consultas
análise
indicadores
Star Schema

Modelo:

Fato no centro
+
Dimensões ao redor
Tabela fato

Armazena métricas numéricas.

Tabela dimensão

Armazena contexto analítico.

Surrogate Key

Chave artificial do DW.

SCD Tipo 2

Controle histórico de alterações.

_CARGA INCREMENTAL

Procedure de carga incremental

Procedure:

CARGA_FATO
Lógica utilizada

A procedure:

identifica última data carregada
carrega apenas novos registros
Conceitos utilizados
Incremental Load

Carga incremental.

Watermark

Controle temporal da carga.

Separação lógica dos dados.
