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

[Sua descrição aqui]

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

[ex: Os JSON/CSV são carregados no início da sessão e incluídos no contexto do prompt]

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

[Sua descrição aqui]

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Saldo disponível: R$ 5.000

Últimas transações:
- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55
...
```
