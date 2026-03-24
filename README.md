# 📄 **README.md — Formulas DAX Básicas 



# 🚚 Análise de Fretes — Power BI 

Projeto de estudo e prática de modelagem, DAX e visualização de dados

Este repositório contém um projeto desenvolvido para treinar conceitos fundamentais de **Power BI**, incluindo:
- Modelagem de dados
- Criação de medidas DAX
- Indicadores de desempenho logístico
- Construção de dashboards

---

## 📦 Base de Dados

A base utilizada se chama **Base Frete** e contém **58.980 linhas** com as seguintes colunas:

- **Viagem**
- **Data Pedido**
- **Prazo Entrega**
- **Tempo Entrega**
- **Status Entrega**
- **UF**
- **Tipo Veículo**
- **KM**
- **Custos**
- **Valor do Frete**

Esses dados representam operações de transporte e entrega, permitindo análises de desempenho logístico.

---

## 📊 Medidas Criadas (DAX)

### 💰 Receita Total
```DAX
Receita Total = SUM('Base Frete'[Valor do Frete])
```

### 🚛 Quilômetros Rodados (média)
```DAX
Kilometros Rodados = AVERAGE('Base Frete'[Km])
```

### 💸 Maior Custo
```DAX
Maior Custo = MAX('Base Frete'[Custos])
```

### 💸 Menor Custo
```DAX
Menor Custo = MIN('Base Frete'[Custos])
```

### 📦 Quantidade de Entregas
```DAX
Qtd Entrega = COUNT('Base Frete'[Viagem])
```

### 🌎 Regiões Atendidas
```DAX
Regioes Atendidas = DISTINCTCOUNT('Base Frete'[UF])
```

### ⏱️ Entregas no Prazo
```DAX
Entregas no Prazo = 
CALCULATE(
    COUNTROWS('Base Frete'),
    'Base Frete'[Status Entrega] = "No Prazo"
)
```

### 📈 Percentual de Entregas no Prazo
```DAX
Percentual no Prazo = DIVIDE([Entregas no Prazo], [Qtd Entrega])
```

### 🟢 Status de Performance
```DAX
Status = IF([Percentual no Prazo] >= 0.7, "Bom", "Em Alerta")
```

---

## 🎯 Objetivo da Análise

O objetivo deste projeto é:

- Avaliar o desempenho logístico das entregas  
- Identificar regiões atendidas  
- Monitorar custos e quilometragem  
- Medir eficiência no cumprimento de prazos  
- Criar indicadores de performance (KPIs)

---

## 📈 Possíveis Visualizações

- KPI de Receita Total  
- KPI de Percentual no Prazo  
- Mapa por UF  
- Gráfico de barras por Tipo de Veículo  
- Distribuição de Custos  
- Evolução de Entregas por Data  

---

## 🛠️ Ferramentas Utilizadas

- **Power BI Desktop**
- **Power Query**
- **DAX**
- **GitHub** (documentação e versionamento)

---

## 📌 Status do Projeto

✔ Em desenvolvimento  
✔ Medidas criadas  
⬜ Dashboard final (em construção)




