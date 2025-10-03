# 📊 Análise de concessionária com Power BI

Essa análise foi criada para visualizar o rendimento de uma concessionária com base nas 5 marcas de carros que são vendidas e os países no qual os carros são vendidos

O dashboard foi feito com base em dados já tratados vindo de um banco de dados.

## 1. Banco de dados

### 1.1 Estrutura Geral
o Banco de dados segue uma estrutura relacional

**Tabela: Carros**

Contém as informações sobre os carros da concessionária

    id_carros (PK)
    marca
    pais_origem
    modelo
    ano_producao
    cilindrada DECIMAL(2,1)
    combustivel ENUM('Gasolina', 'Diesel', 'Híbrido')
**Tabela: Imagem**

Contém as imagens das marcas dos carros que são vendidos

    id_imagem(PK)
    marca
    url TEXT
**Tabela: lojas**

Contém informações da concessionária

    id_lojas (PK)
    id_carro (FK -> Carros)
    modelo
    valor DECIMAL(10,2)
    pais_venda
**Tabela: meta_marca**

Contém a meta de lucro de cada marca

    id_meta_marca (PK)
    marca
    meta_marca
**Tabela: pais_meta**
Contém a meta de lucro para cada país que é vendido

    pais_meta(PK)
    pais
    meta

### 1.2 Regra de negócio

- Conversão da coluna valor que estava em dolar para reais 

## 2. ETL e dados

**Fonte:** Base de dados retirado do kaggle: https://www.kaggle.com/datasets/minahilfatima12328/car-sales-info

**Limpeza e alterações feitas**

- Separação das colunas do arquivo para as 5 tabelas

- Conversão de valores para padronização em reais

- Adição de 3 tabelas, onde duas delas armazena a meta para cada país vendido e outra a meta para cada marca de carro, além da tabela que armazenaas imagens de cada marca.

# 3. Dashboard
### 3.1 Ferramenta

O dashboard foi feito no **Power BI**

### 3.2 Conteúdo do dashboard

O dashboard possui 2 páginas, tendo 2 dicas de ferramentas e medidas.

**Elementos das páginas**

**Página 1**

Destinado aos carros e marcas 

- Scroller das marcas com seus valores e quantos % esta acima ou abaixo de sua respectiva meta

- Segmentação de dados: Marca, cilindrada e ano do carro

- Logo das marcas

- Cartão de linhas múltiplas com % total dos lucros por cada tipo de combustivel

- Treemap com lucro total de cada país que fabricam os carros

- Gráfico de barras clusterizadas com lucro total por cada modelo de carro

- Gráfico de colunas clusterizadas com lucro total e metas de cada meta

**Página 2**

Destinado aos países vendidos

- Segmentação de dados: Marca

- Logo das marcas

- Indicador com lucro total geral e sua meta, com dica de ferramenta que indica quantos % faltam para atingir a meta

- Gráifco de colunas mostrando os 3 países que mais lucraram em cada marca e dica de ferramenta indicando o lucro total com essa marca e quantos % esse valor representa no lucro total do país

- Tabela onde possui as colunas país, total de país, meta_de_pais, ganho ou perda (representa quantos % o lucro do país teve de lucro ou prejuízo)
