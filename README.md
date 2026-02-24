Esse projeto implementa uma pipeline de dados automatizada utilizando a Arquitetura Medallion, transformando dados de uma rede de lojas de bicicletas em tabelas analíticas de alta performance.


Objetivo:
Resolver o problema de fragmentação de dados entre vendas, estoques e clientes, permitindo que o time de operações tome decisões baseadas em dados em tempo real (focando em pedidos pendentes e performance regional).


Linguagem: Python / Spark SQL

Engine: Apache Spark (Databricks)

Arquitetura: Medallion (Bronze ➔ Silver ➔ Gold)

Orquestração: Databricks 

Arquitetura e Fluxo de Dados


🥉 Camada Bronze (Raw & Ingestion)

Ingestão de 9 fontes de dados (brands, categories, customers, orders, etc.).

Foco: Preservação da fidelidade dos dados originais.

Data Validation: Etapa 00-Bronze_Validate para garantir a integridade da carga inicial.


🥈 Camada Silver (Cleaned & Integrated)

Unificação de entidades de produtos, pedidos e clientes.

Tratamento de tipos de dados, normalização e limpeza.

Governance: Nova etapa de validação (00-Silver_Validate) antes da promoção para a camada final.


🥇 Camada Gold (Business / Analytics)

Entrega de tabelas prontas para consumo de BI:

Gold_Sales_NY: Agregação de vendas entregues especificamente para o estado de NY, facilitando o monitoramento de metas regionais.

Gold_Orders_Pending: Visão 360º dos clientes com pedidos pendentes, unindo dados de contato para ações de Customer Success.

<img width="1018" height="742" alt="image" src="https://github.com/user-attachments/assets/d1d123a1-db69-46e1-95fc-fbac0ed57e87" />
