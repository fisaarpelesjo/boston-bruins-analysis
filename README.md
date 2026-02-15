# NHL Hockey Analytics - Boston Bruins

Projeto de análise de dados esportivos de hóquei no gelo, focado na performance do Boston Bruins na temporada 2024-25.

## 📊 Fonte dos Dados

Os dados foram obtidos gratuitamente no **MoneyPuck**:

* **Site:** [https://moneypuck.com/data.htm](https://moneypuck.com/data.htm)
* **Arquivo:** `BOS.csv` (dados jogo a jogo do Boston Bruins)
* **Período:** Temporadas de 2008-09 até 2024-25

O MoneyPuck disponibiliza dados de jogadores, times, goleiros e chutes (shots) desde 2008. Os dados são gratuitos para uso não comercial, com crédito ao MoneyPuck.com.

---

## 🎯 Objetivo

Análise de **Processo vs Resultado (xGoals Analysis)** — comparar os gols esperados (Expected Goals) com os gols reais para identificar eficiência, dominância estatística e possível influência de sorte nos resultados.

---

## 📁 Estrutura do Projeto

```
boston-bruins-analysis/
├── README.md
├── BOS.csv                      # Dados brutos do MoneyPuck
└── boston_bruins_analysis.ods   # Análise no LibreOffice Calc
```

---

## 📋 Estrutura da Planilha

### Aba: BOS

Dados brutos importados do CSV com 109 colunas de métricas.

### Aba: xGoals_Analysis

Tabela analítica por jogo com métricas derivadas.

| Coluna               | Descrição                                        |
| -------------------- | ------------------------------------------------ |
| Game_ID              | ID único do jogo                                 |
| Game_Date            | Data do jogo                                     |
| Opposing_Team        | Time adversário                                  |
| Home_or_Away         | HOME ou AWAY                                     |
| Situation            | Situação do jogo (all, 5on5, etc.)               |
| xG_For               | Gols esperados criados                           |
| Goals_For            | Gols reais marcados                              |
| xG_Against           | Gols esperados concedidos                        |
| Goals_Against        | Gols reais sofridos                              |
| Season               | Temporada                                        |
| Luck_Offense         | Goals_For - xG_For                               |
| Luck_Defense         | xG_Against - Goals_Against                       |
| Net_xG               | xG_For - xG_Against                              |
| Net_Goals            | Goals_For - Goals_Against                        |
| xG_Share             | xG_For / (xG_For + xG_Against)                   |
| Performance_Delta    | Net_Goals - Net_xG                               |
| Shooting_Efficiency  | Goals_For / xG_For                               |
| Defensive_Efficiency | Goals_Against / xG_Against                       |
| PDO                  | Shooting_Efficiency + (1 - Defensive_Efficiency) |

---

## 📈 Métricas de Análise

### Expected Goals (xG)

Estimativa estatística de quantos gols um time "deveria" marcar ou sofrer com base na qualidade das chances criadas. O modelo considera:

* Distância do gol
* Ângulo do chute
* Tipo de jogada
* Situação do jogo (power play, 5v5, etc.)

---

### Luck_Offense

```
Luck_Offense = Goals_For - xG_For
```

Diferença entre gols reais marcados e gols esperados.

---

### Luck_Defense

```
Luck_Defense = xG_Against - Goals_Against
```

Diferença entre gols esperados concedidos e gols reais sofridos.

---

### Net_xG

```
Net_xG = xG_For - xG_Against
```

Mede dominância estatística baseada na qualidade das chances.

---

### Net_Goals

```
Net_Goals = Goals_For - Goals_Against
```

Resultado real do jogo.

---

### xG_Share

```
xG_Share = xG_For / (xG_For + xG_Against)
```

Percentual de controle do jogo baseado em chances criadas.

---

### Performance_Delta

```
Performance_Delta = Net_Goals - Net_xG
```

Diferença entre resultado real e desempenho esperado.

---

### Shooting_Efficiency

```
Shooting_Efficiency = Goals_For / xG_For
```

Eficiência ofensiva comparada ao esperado.

---

### Defensive_Efficiency

```
Defensive_Efficiency = Goals_Against / xG_Against
```

Eficiência defensiva comparada ao esperado.

---

### PDO

```
PDO = Shooting_Efficiency + (1 - Defensive_Efficiency)
```

Indicador agregado de eficiência ofensiva e defensiva.

---

## 🔧 Ferramentas Utilizadas

* LibreOffice Calc (versão 26.2.0.3)
* MoneyPuck (fonte de dados)

---

## ⚙️ Configuração de Importação

Ao importar o CSV no LibreOffice Calc:

* Localidade: English (USA)
* Separador de campo: Vírgula

Isso garante que os decimais (.) sejam lidos corretamente.

---

## 📅 Filtros Aplicados

Para análise da temporada 2024-25:

* season: 2024
* situation: all
* Total de jogos: 82

---

## 📝 Créditos

* Dados fornecidos por MoneyPuck.com
* Projeto desenvolvido para fins de estudo e análise esportiva

---

## 📜 Licença

Este projeto é para uso pessoal e educacional. Os dados do MoneyPuck são gratuitos para uso não comercial com devida atribuição.
