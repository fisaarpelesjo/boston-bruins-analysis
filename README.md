# NHL Hockey Analytics - Boston Bruins

Projeto de análise de dados esportivos de hóquei no gelo, focado na performance do Boston Bruins na temporada 2024-25.

## 📊 Fonte dos Dados

Os dados foram obtidos gratuitamente no **MoneyPuck**:

- **Site:** https://moneypuck.com/data.htm
- **Arquivo:** `BOS.csv` (dados jogo a jogo do Boston Bruins)
- **Período:** Temporadas de 2008-09 até 2024-25

O MoneyPuck disponibiliza dados de jogadores, times, goleiros e chutes (shots) desde 2008. Os dados são gratuitos para uso não comercial, com crédito ao MoneyPuck.com.

## 🎯 Objetivo

Análise de **Sorte vs Habilidade (xGoals Analysis)** - comparar os gols esperados (Expected Goals) com os gols reais para identificar se o time está tendo "sorte" ou "azar" nos resultados.

## 📁 Estrutura do Projeto

```
nhl-analytics/
├── README.md
├── BOS.csv                      # Dados brutos do MoneyPuck
└── boston_bruins_analysis.ods   # Análise no LibreOffice Calc
```

## 📋 Estrutura da Planilha

### Aba: BOS

Dados brutos importados do CSV com 109 colunas de métricas.

### Aba: xGoals_Analysis

Análise filtrada com as seguintes colunas:

| Coluna        | Descrição                          |
| ------------- | ---------------------------------- |
| gameId        | ID único do jogo                   |
| gameDate      | Data do jogo (YYYYMMDD)            |
| opposingTeam  | Time adversário                    |
| home_or_away  | HOME ou AWAY                       |
| situation     | Situação do jogo (all, 5on5, etc.) |
| xGoalsFor     | Gols esperados (ataque)            |
| goalsFor      | Gols reais marcados                |
| xGoalsAgainst | Gols esperados (defesa)            |
| goalsAgainst  | Gols reais sofridos                |
| season        | Temporada                          |
| luckOffense   | goalsFor - xGoalsFor               |
| luckDefense   | xGoalsAgainst - goalsAgainst       |
| totalLuck     | luckOffense + luckDefense          |

## 📈 Métricas de Análise

### Expected Goals (xGoals)

Estimativa estatística de quantos gols um time "deveria" marcar/sofrer, baseado na qualidade das chances criadas. O modelo considera:

- Distância do gol
- Ângulo do chute
- Tipo de jogada
- Situação do jogo (power play, etc.)

### luckOffense (Sorte no Ataque)

```
luckOffense = goalsFor - xGoalsFor
```

- **Positivo:** Marcou mais do que esperado (sorte/eficiência excepcional)
- **Negativo:** Marcou menos do que esperado (azar/ineficiência)

### luckDefense (Sorte na Defesa)

```
luckDefense = xGoalsAgainst - goalsAgainst
```

- **Positivo:** Sofreu menos do que esperado (sorte/goleiro excepcional)
- **Negativo:** Sofreu mais do que esperado (azar/goleiro fraco)

### totalLuck (Sorte Total)

```
totalLuck = luckOffense + luckDefense
```

Visão geral da "sorte" do time no jogo.

## 🔧 Ferramentas Utilizadas

- **LibreOffice Calc** (versão 26.2.0.3)
- **MoneyPuck** (fonte de dados)

## ⚙️ Configuração de Importação

Ao importar o CSV no LibreOffice Calc (Português Brasil), configure:

- **Localidade:** English (USA)
- **Separador de campo:** Vírgula
- Isso garante que os decimais (ponto) sejam lidos corretamente.

## 📅 Filtros Aplicados

Para análise da temporada 2024-25:

- **season:** 2024
- **situation:** all (todas as situações do jogo)
- **Total de jogos:** 82

## 📝 Créditos

- Dados fornecidos por [MoneyPuck.com](https://moneypuck.com)
- Projeto desenvolvido para fins de estudo e análise esportiva

## 📜 Licença

Este projeto é para uso pessoal e educacional. Os dados do MoneyPuck são gratuitos para uso não comercial com devida atribuição.
