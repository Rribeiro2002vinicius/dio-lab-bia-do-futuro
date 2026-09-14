# Base de Conhecimento

## Dados Utilizados


| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Utilizar o histórico para contextualizar as mensagnes do usuário |
| `perfil_investidor.json` | JSON | Personalizar explicações sobre os tipos de investimentos adequados para o cliente e oque o cliente deve aprender |
| `produtos_financeiros.json` | JSON | apresentar os produtos ao cliente |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente para dar dicas sobre como planejar melhor os gastos |

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Adicionei a variável custo_fixo_mensal e adicionei mais alguns produtos financeiros

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

```python
import panda as pd
import json

# CSV's
historico = pd.read_csv('data/historico_atendimento.csv')
transacoes = pd.read_csv('data/transacoes.csv')

# JSON's
with open('data/perfil_investidor.json', 'r', encoding='UTF-8') as f:
perfil = json.load(f)

with open('data/produtos_financeiros.json', 'r', encoding='UTF-8') as f:
produtos = json.load(f)

```

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

```python
import json
import pandas as pd

# Perfil e dados do cliente
with open('data/perfil_investidor.json', 'r', encoding='UTF-8') as f:
perfil = json.load(f)

# Transacoes
transacoes = pd.read_csv('data/transacoes.csv')

# Produtos disponiveis
with open('data/produtos_financeiros.json', 'r', encoding='UTF-8') as f:
produtos = json.load(f)

# Historico de atendimento
historico = pd.read_csv('data/historico_atendimento.csv')

```
---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Saldo disponível: R$ 5.000

Gastos mensais:
- Água: 150
- Luz	: 300
- Gás	: 150
- Aluguel	: 2.000
- IPTU : 100
- Transporte	: 300
- Alimentação	: 900

Produtos disponiveis:
- Tesouro Selic
- CDB (Certificado de Depósito Bancário) - Liquidez Diária
- LCI/LCA
- Fundo Multimercado
- Fundo de Ações
- Tesouro IPCA
- Fundo Imobiliário (FII)
```
