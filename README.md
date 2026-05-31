<img width="1672" height="941" alt="image" src="https://github.com/user-attachments/assets/881a2913-41dc-47bd-b0c7-9875aedb1c3e" />

# ⚗ Midas Lab

Pipeline de inteligência preditiva para ações da B3. Coleta dados de +400 ativos, treina regressão linear por ação, classifica previsibilidade e sugere carteira batendo a Selic. Inclui backtest real — simulamos quanto R$ 100k teriam rendido se investidos 3 meses atrás.

---

## 🔬 Como Funciona

1. **Coleta** — yfinance baixa histórico de +400 tickers da B3
2. **Busca de parâmetros** — 7 janelas de treino testadas em escala → vencedora: **7 meses**
3. **Modelagem** — Regressão Linear Simples por ativo (feature: tempo; target: preço de fechamento)
4. **Validação** — Split temporal treino/teste → métricas MAE, RMSE, MAPE, R², acerto direcional
5. **Classificação** — 4 níveis de previsibilidade por acerto direcional
6. **Carteira** — sugere compra se previsível + retorno previsto > Selic + 0.5%
7. **Backtest** — simula R$ 100k investidos 3 meses atrás com resultado real

---

## 📊 Resultados

| Janela Vencedora | Score | MAPE | Acerto Direcional |
|---|---|---|---|
| **7 meses** | 73.4 | 34.07% | 46.7% |

**Backtest (período Mai/2026):**
- 7 ações sugeridas como ✅ COMPRAR
- 6 de 7 acertaram a direção (86%)
- Destaques: USIM5 +56.72%, USIM3 +42.63%, PRIO3 +14.24%

---

## 🛠️ Stack

`Python 3.10+` · `yfinance` · `pandas` · `numpy` · `scikit-learn` · `matplotlib` · `openpyxl`

---

## ⚙️ Como Rodar

```bash
git clone https://github.com/kaue/midas-lab.git
cd midas-lab
pip install yfinance pandas numpy matplotlib plotly scikit-learn python-dotenv python-dateutil openpyxl -q
jupyter notebook Midas_Lab_v2.ipynb
```

---

## 👥 Contributors

| Colaborador | GitHub |
|---|---|
| Kaue Mandarino | [@kaue](https://github.com/kaue) |
| Yago Cavalcante | [@apenas-datasci](https://github.com/apenas-datasci) |
| Hélio Oliveira | [@helioliveira1](https://github.com/helioliveira1) |

---

## ⚠️ Disclaimer

As sugestões geradas pelo Midas Lab são produzidas por modelo estatístico simples e **não constituem recomendação de investimento**. Rentabilidade passada não garante resultados futuros.

---

## 📄 Licença

MIT License
