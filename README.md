# 📊 E-commerce Business Intelligence Project

## 🔎 Visão Geral
Projeto completo de Business Intelligence desenvolvido para um cenário fictício de e-commerce, cobrindo todas as etapas do pipeline de dados: modelagem OLTP, processos de ETL, área de Stage, Data Warehouse e análise com Power BI.  
O projeto simula uma arquitetura corporativa completa, com foco em governança, qualidade e integração de dados.

---

## 🎯 Objetivo do Projeto
Transformar dados operacionais em informações estratégicas, fornecendo indicadores e análises de negócio que suportem a tomada de decisão em um ambiente corporativo de e-commerce.

---

## 🏗️ Arquitetura da Solução
A solução foi estruturada em quatro fases principais:

- **Documento de Requisitos**  
- **Fase 1 – Modelagem OLTP**  
- **Fase 2 – Área Stage**  
- **Fase 3 – Data Warehouse**  
- **Fase 4 – Relatório Executivo**  

---

## ⚙️ Tecnologias Utilizadas
- **SQL Server**  
- **SSIS**  
- **ETL**  
- **Stage**  
- **Data Warehouse**  
- **Star Schema**  
- **Slowly Changing Dimension Tipo 2**  
- **Watermark**  
- **Power BI**  
- **DAX**  

---

## 📂 Estrutura do Projeto
| Diretório | Descrição |
|------------|------------|
| **DOCUMENTACAO/** | Documento de requisitos e especificações do projeto |
| **OLTP/** | Scripts de criação do banco transacional |
| **STAGE/** | Estrutura de tabelas intermediárias para processamento ETL |
| **DW/** | Scripts de criação do Data Warehouse |
| **SSIS/** | Pacotes ETL desenvolvidos no SQL Server Integration Services |
| **POWERBI/** | Relatórios e dashboards analíticos |

---

## 🔄 Fase 1 — Modelagem OLTP
- Criação do banco transacional do e-commerce.  
- Estrutura normalizada para evitar redundância e garantir integridade.  
- Principais tabelas: CLIENTE, ENDERECO, PRODUTO, CATEGORIA, FORNECEDOR, VENDEDOR, FORMA_PAGAMENTO, NOTA_FISCAL, ITEM_NOTA.  
- Uso de PK, FK e integridade referencial.  

---

## 🔄 Fase 2 — Área Stage
- Camada intermediária para limpeza, padronização e auditoria dos dados.  
- Transformações: remoção de inconsistências, ajuste de tipos, padronização textual, tratamento de NULLs.  
- Implementação de regras de negócio e tratamento de erros (ex.: clientes sem endereço → tabela BI_ERROR).  

---

## 🔄 Fase 3 — Data Warehouse
- Construção do ambiente analítico com **Star Schema**.  
- **Dimensões:** Cliente, Produto, Fornecedor, Vendedor, Forma de Pagamento, Nota Fiscal, Tempo.  
- **Fato:** FATO_VENDAS (quantidade, valor total, custo, lucro).  
- Implementação de **SCD Tipo 2** para controle histórico.  
- Carga incremental com **Watermark** para rastreabilidade temporal.  

---

## 🔄 Fase 4 — Relatório Executivo (2015–2016)
Dashboard desenvolvido no **Power BI**, consolidando indicadores estratégicos e análises comerciais.

<img width="1247" height="696" alt="image" src="https://github.com/user-attachments/assets/fa957757-ecfa-4e84-97a1-3e292825519d" />


### Indicadores Gerais
| Indicador | Valor |
|------------|--------|
| **Faturamento Total** | R$ 5,24 bilhões |
| **Lucro Total** | R$ 887,83 milhões |
| **Quantidade Vendida** | 2 milhões de produtos |
| **Clientes Atendidos** | 10 |
| **Produtos Comercializados** | 5 |

### Principais KPIs
- **Margem de Lucro:** 16,9%  
- **Ticket Médio por Cliente:** R$ 524 milhões  
- **Quantidade Média Vendida por Cliente:** 200 mil produtos  
- **Valor Médio por Produto Vendido:** R$ 2.620  

### Principais Análises
- **Distribuição Regional:** concentração no Sudeste e Sul.  
- **Desempenho Comercial:** três vendedores concentram a maior parte das vendas.  
- **Evolução Temporal:** oscilações mensais, mas manutenção do volume consolidado.  


## ▶️ Como Executar o Projeto
1. Criar o banco OLTP com os scripts disponíveis na pasta **OLTP/**.  
2. Configurar a área **Stage** e o **Data Warehouse** conforme os scripts das respectivas pastas.  
3. Executar os pacotes **SSIS** para realizar o processo ETL.  
4. Abrir o relatório **Power BI** e conectar ao DW para visualizar os dashboards.  

---

## 📚 Aprendizados
- Construção de pipeline completo de BI corporativo.  
- Implementação de **SCD Tipo 2** e **carga incremental** com Watermark.  
- Aplicação de **Data Quality** e auditoria de dados.  
- Desenvolvimento de **dashboards interativos** com DAX.  
- Consolidação de indicadores estratégicos para análise comercial.  

---

## 👩‍💻 Autora
**Jeniffer Santos**  
Estudante de Sistemas de Informação  
Foco em Dados, BI e Engenharia de Dados  
