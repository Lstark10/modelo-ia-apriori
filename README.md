# 🛒 Market Basket Analysis com Algoritmo Apriori

## 📋 Descrição do Projeto

Este projeto implementa uma análise de **Market Basket Analysis** (MBA) utilizando o algoritmo **Apriori** para descobrir padrões de compra e regras de associação em dados transacionais de vendas de uma loja. O objetivo é identificar quais produtos são frequentemente comprados juntos, permitindo insights valiosos para estratégias de marketing, recomendações de produtos e otimização do layout da loja.

## 🎯 Objetivos

- **Análise Exploratória de Dados (EDA)**: Compreender a estrutura e características dos dados transacionais
- **Identificação de Padrões**: Descobrir quais departamentos são mais vendidos
- **Market Basket Analysis**: Encontrar associações entre produtos usando o algoritmo Apriori
- **Geração de Regras**: Criar regras de associação com métricas de suporte e confiança
- **Visualização**: Apresentar insights através de gráficos interativos

## 📊 Dataset

O dataset (`dataset.csv`) contém dados transacionais com as seguintes colunas:

- **POS Txn**: ID único da transação
- **Dept**: Nome do departamento/produto
- **ID**: ID numérico do departamento
- **Sales U**: Quantidade de unidades vendidas

### Exemplo dos dados:
```
POS Txn,Dept,ID,Sales U
16120100160021008773,0261:HOSIERY,250,2
16120100160021008773,0634:VITAMINS & HLTH AIDS,102,1
16120100160021008773,0879:PET SUPPLIES,158,2
```

## 🔧 Tecnologias Utilizadas

### Linguagem
- **Python 3.8+**

### Bibliotecas Principais
- **pandas**: Manipulação e análise de dados
- **numpy**: Computação numérica
- **plotly**: Visualizações interativas
- **matplotlib & seaborn**: Visualizações estáticas e heatmaps
- **mlxtend**: Implementação do algoritmo Apriori e regras de associação

### Ambiente de Desenvolvimento
- **Jupyter Notebook**: Desenvolvimento interativo
- **VS Code**: Editor de código

## 🚀 Instalação e Configuração

### 1. Clone o repositório
```bash
git clone <url-do-repositorio>
cd apriori
```

### 2. Criar ambiente virtual (recomendado)
```bash
python -m venv venv
```

### 3. Ativar o ambiente virtual
```bash
# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate
```

### 4. Instalar dependências
```bash
pip install -r requirements.txt
```

### 5. Executar o Jupyter Notebook
```bash
jupyter notebook modelo_ia.ipynb
```

## 📈 Estrutura do Projeto

```
apriori/
│
├── dataset.csv              # Dataset com dados transacionais
├── modelo_ia.ipynb         # Notebook principal com análise completa
├── requirements.txt        # Dependências do projeto
└── README.md              # Documentação do projeto
```

## 🔍 Metodologia

### 1. **Carregamento e Preparação dos Dados**
- Carregamento do dataset CSV
- Renomeação de colunas para melhor legibilidade
- Limpeza de dados (remoção de quantidades negativas/zero)

### 2. **Análise Exploratória de Dados (EDA)**
- Análise da estrutura dos dados
- Identificação de departamentos mais vendidos
- Análise de volume de transações vs. unidades vendidas
- Visualização da distribuição e variabilidade das vendas
- Matriz de correlação entre departamentos

### 3. **Preparação para Market Basket Analysis**
- Criação de pivot table com transações nas linhas e departamentos nas colunas
- Conversão para formato booleano (True/False) para presença de itens
- Estruturação dos dados no formato adequado para o algoritmo Apriori

### 4. **Aplicação do Algoritmo Apriori**
- Configuração de suporte mínimo (2%)
- Geração de itemsets frequentes
- Análise de itemsets de diferentes tamanhos

### 5. **Geração de Regras de Associação**
- Aplicação de confiança mínima (40%)
- Criação de regras do tipo "Se A, então B"
- Análise de métricas como suporte, confiança e lift

## 📊 Principais Insights e Visualizações

### Gráficos Implementados:
1. **Volume de Transações por Departamento** (Top 10)
2. **Unidades Vendidas por Departamento** (Top 10)
3. **Variação nas Unidades Vendidas** (Desvio Padrão - Top 20)
4. **Média de Unidades Vendidas** (Top 20)
5. **Box Plot da Distribuição de Vendas**
6. **Matriz de Correlação entre Departamentos**

### Métricas do Apriori:
- **Suporte**: Frequência de aparição do itemset
- **Confiança**: Probabilidade condicional da regra
- **Lift**: Força da associação (valores > 1 indicam associação positiva)

## 🔧 Parâmetros Configuráveis

### Algoritmo Apriori:
- **min_support**: 0.02 (2%) - Suporte mínimo para itemsets frequentes
- **min_confidence**: 0.4 (40%) - Confiança mínima para regras de associação

### Justificativas:
- **Suporte 2%**: Garante cobertura adequada (40-100 transações) sem ser muito restritivo
- **Confiança 40%**: Equilibra precisão e quantidade de regras geradas

## 📋 Resultados Esperados

O projeto gera:
1. **Lista de itemsets frequentes** com seus respectivos suportes
2. **Regras de associação** com métricas de confiança, lift e conviction
3. **Visualizações interativas** dos padrões encontrados
4. **Insights de negócio** sobre comportamento de compra dos clientes

## 🎯 Aplicações Práticas

- **Recomendação de Produtos**: Sugerir produtos complementares
- **Layout de Loja**: Posicionar produtos relacionados próximos
- **Estratégias de Marketing**: Criar promoções cruzadas
- **Gestão de Estoque**: Otimizar níveis de estoque baseado em associações
- **Análise de Cestas**: Entender padrões de compra dos clientes

## 📝 Notas Técnicas

### Preparação dos Dados:
- Os dados são convertidos para formato de matriz binária (pivot table)
- Cada linha representa uma transação, cada coluna um departamento
- Valores True/False indicam presença/ausência do item na transação

### Performance:
- O algoritmo Apriori pode ser computacionalmente intensivo para grandes datasets
- Considere usar FP-Growth para datasets muito grandes
- O parâmetro de suporte influencia diretamente no tempo de execução

## 👥 Contribuições

Contribuições são bem-vindas! Para contribuir:

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
