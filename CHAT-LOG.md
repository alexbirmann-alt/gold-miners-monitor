# Chat Log — Precious Metals Monitor
**Data de inicio:** 2026-03-18
**Projeto:** Gold & Silver Miners Monitor (NYSE)
**Repo:** https://github.com/alexbirmann-alt/gold-miners-monitor
**GitHub Pages:** https://alexbirmann-alt.github.io/gold-miners-monitor/

---

## Resumo do Projeto

Web app single-page (HTML puro) que monitora mineradoras de ouro e prata listadas na NYSE, com dados ao vivo do Finnhub.

### Stack
- HTML/CSS/JS puro (sem frameworks)
- API: Finnhub (key: [REDACTED])
- Hospedagem: GitHub Pages

---

## Features Implementadas

### 1. Aba Ouro
- 14+ mineradoras de ouro (NEM, GOLD, AEM, KGC, AU, GFI, HMY, AGI, EGO, BTG, IAG, EQX, CGAU, NGD)
- Mineradoras ouro+prata (CDE, SSRM)
- Streamers/Royalty (OR, FNV, WPM, RGLD)
- ETFs: GDX, GDXJ, GLD, AAAU
- Vista cards + tabela com sort

### 2. Aba Prata
- Prata pura: AG, EXK, SVM, MAG
- Prata+ouro: PAAS, HL, FSM, USAS
- ETFs: SLV, SLVP, PSLV

### 3. Dados por Empresa
- Preco atual, variacao, variacao %
- 52 Week High / 52 Week Low
- P/E Trailing e P/E Forward
- Abertura, Volume, Market Cap
- Badge visual: Au (ouro), Ag (prata), Au+Ag (ambos)

### 4. Aba Portfolio (Simulador Hipotetico)
- Capital inicial configuravel
- 3 perfis: Conservador, Balanceado, Agressivo
- **Seletor de acoes com checkboxes** (filtro por tipo, busca, select all/clear all)
- Pie chart (canvas donut) com alocacao por categoria
- Tabela detalhada: ticker, peso %, valor USD, preco, numero de acoes
- Redistribuicao automatica quando acoes sao desmarcadas
- Disclaimer: "nao constitui recomendacao de investimento"

### 5. Visual
- Dark theme
- Icones Au/Ag no logo
- Badges coloridos por metal primario
- Cards com gradientes e bordas por tipo
- Responsivo (mobile/tablet/desktop)

---

## Tickers Removidos (sem dados no Finnhub US)
- SAND (Sandstorm Gold) → so existe como SSL.TO
- GATO (Gatos Silver) → so existe como GATO.TO
- SILV (SilverCrest Metals) → so existe como SIL.TO

---

## Historico de Commits

1. **Initial commit** — app base com abas ouro/prata, dados Finnhub
2. **Add 52W High/Low, P/E Trailing/Forward** — 4 novas colunas de dados
3. **Add visual distinction by primary metal** — badges Au/Ag/Au+Ag
4. **Add hypothetical portfolio simulator tab** — pie chart + tabela
5. **Add stock selector with checkboxes** — filtros, busca, select all
6. **Remove SAND, GATO, SILV** — fix tickers indisponiveis

---

## Decisoes Tecnicas

- **Finnhub vs Yahoo Finance:** Yahoo bloqueava CORS, Finnhub funciona direto do browser
- **Canvas pie chart:** implementado manualmente sem bibliotecas externas
- **Portfolio redistribuicao:** quando acoes sao desmarcadas, pesos das categorias ativas se ajustam proporcionalmente
- **Safety net:** tickers com preco=0 sao automaticamente ignorados

---

## Como Rodar Localmente
Abrir `gold-miners-monitor.html` em qualquer browser.

## Como Fazer Deploy
O arquivo `index.html` e uma copia do `gold-miners-monitor.html`.
Push para `main` → GitHub Pages atualiza automaticamente.
