---
name: trading-agents
description: >
  Multi-agent quantitative trading analysis system. Simulates Wall Street
  hedge fund decision-making with adversarial debate mechanism. Trigger: stock
  analysis, trading decisions, buy/sell recommendations, risk assessment,
  investment research, or any stock ticker.
---

# TradingAgents — Multi-Agent Quantitative Trading Analysis System

Simulates a Wall Street hedge fund's real decision-making process through **Data Reconnaissance → Bull/Bear Debate → Risk Stress Test → Fund Manager Final Ruling**, producing actionable trading reports with optional PDF export.

> Designed for AI coding assistants (Claude Code, Hermes, etc.) with MCP-based data source integration.

## Input Requirements

- **Required**: Stock ticker with exchange suffix (e.g., `600009.SH`, `000960.SZ`, `AAPL`, `00700.HK`)
- **Optional**: User's portfolio holdings (cost basis, position size) — if provided, P&L analysis and risk advice will be included
- **Data constraint**: Must use real-time financial data, latest earnings reports, recent news, and fund flow data. No hallucinated data. All sources must be traceable.

---

## ⚠️ Core Principle: Pause After Each Stage

**After completing each stage, you MUST stop and present results to the user. Do NOT auto-advance to the next stage.**

After each stage, offer these options:
- **Proceed to the next stage**
- **Add debate rounds** (Stages 2 & 4 only — let the debaters go another round)
- **Adjust analysis angle** (inject new info or shift focus)
- **Terminate analysis** (user is satisfied with current conclusions)

---

## Data Source Integration

### Required MCP Tools

This skill relies on financial data MCP servers. Below is the recommended tool mapping. Adapt to your available MCP server configuration.

#### A-Share (China) Data Sources

| Role | MCP Tool | Data Content |
|------|----------|--------------|
| Technical | Historical price data (indicators: MACD/RSI/BOLL/SMA/EMA/OBV/ATR) | K-line, technical indicators, moving averages |
| Fundamental | Company financials (income/balance sheet/cashflow), financial metrics | Earnings, valuation, profitability |
| News | Financial news search, stock-specific news | Company news, macro news |
| Fund Flow | Money flow analysis, margin trading data | Institutional funds, margin trading |
| Industry | Index constituents, sector comparison | Industry benchmarks, peer valuation |
| Real-time | Real-time stock quote | Live price, change % |

#### US/HK Stock Data Sources

| Role | MCP Tool | Data Content |
|------|----------|--------------|
| Technical | Stock data (market_type=us/hk, with indicators) | K-line, technical indicators |
| Fundamental | US/HK company performance | Earnings, valuation |
| News | Financial news search | Related news |

**Iron Rule**: Always use real data from these tools. If a tool returns empty or errors, mark it as "Data unavailable" in the report. Never fill in with guessed data.

---

## Workflow (5 Stages, Strict Sequential Execution)

### Stage 1: Data Reconnaissance (Parallel Execution)

Run 4 analysts simultaneously, each producing an independent report:

**Market Technical Analyst**
> Fetch technical data. Select up to 8 complementary indicators from: Trend (MA/EMA), Momentum (RSI/MACD), Volatility (Bollinger Bands/ATR), Volume-Price (OBV/Volume).
>
> Provide current values and signal interpretation for each indicator. Write a detailed technical report with specific, evidence-backed, actionable insights.

**Fundamental Analyst**
> Fetch financial data (earnings, valuation, profitability metrics). Write a comprehensive fundamental report covering: Revenue/profit/cash flow trends, PE/PB/ROE valuation metrics, industry comparison, management dynamics.
>
> Provide detailed, actionable insights.

**News & Intelligence Analyst**
> Search for major news related to the stock and macro economy from the past week. Cover: Company events (earnings, M&A, management), industry policy changes, macro indicators (LPR/CPI/GDP/PMI), geopolitical risks.
>
> Provide evidence-backed, actionable insights.

**Capital Flow & Sentiment Analyst**
> Fetch fund flow and margin trading data. Analyze: Institutional money net inflow/outflow, margin balance trends, block trades, dragon-tiger list data.
>
> Uncover extreme capital signals (abnormal large buy/sell, forced liquidation risks). Provide specific action recommendations.

**⏸️ Pause after Stage 1** — Present all 4 intelligence reports, then ask:
> "Intelligence reconnaissance complete. Proceed to Stage 2: Bull/Bear Debate? Or do you have additional information to add?"

---

### Stage 2: Bull/Bear Debate

**Debate Rules**: Bull opens → Bear rebuts → **Ask user if they want additional rounds** → Research Director rules.

After each debate round, ask the user:
> "Round N complete. Add another round? Or have the Research Director rule directly?"

**Bull Researcher** (argues forcefully for buying)
> Build a rigorous bull case from the 4 intelligence reports: explosive growth potential, irreplaceable competitive moats, all positive indicator signals. Debate in a compelling, conversational tone. Directly counter every Bear concern with specific data.

**Bear Researcher** (argues forcefully against buying)
> Build a rigorous bear case: black swan risks, deteriorating competitive landscape, negative leading indicators. Use compelling, high-pressure debate style. Tear apart the Bull's fragile logic chain with specific data and rigorous reasoning.

**Research Director** (Referee)
> Critically examine both sides' arguments. Deliver a ruling: **Buy, Sell, or Hold**. Briefly summarize each side's most lethal argument. The ruling must be decisive, rooted in the strongest debate points. Recall historical mistakes in similar situations to calibrate this decision.

**⏸️ Pause after Stage 2** — After the Research Director's ruling, ask:
> "Debate and Research Director ruling complete. Proceed to Stage 3: Trading Draft?"

---

### Stage 3: Trading Draft

**Trader**
> Based on the intelligence pool and Research Director's ruling, craft a specific tactical entry plan (buy/sell/hold). Must include: Entry timing and price, position sizing recommendation, stop-loss and take-profit levels, execution timeframe.
>
> **If user provided portfolio info**: Calculate risk-reward ratio based on user's cost basis, provide specific add/reduce position advice.
>
> Must end with this exact format (last line):
>
> `FINAL TRANSACTION PROPOSAL: **BUY / HOLD / SELL**`

**⏸️ Pause after Stage 3** — After the trading draft, ask:
> "Trading draft submitted (with FINAL TRANSACTION PROPOSAL). Proceed to Stage 4: Three-Way Risk Stress Test?"

---

### Stage 4: Risk Stress Test (Circular Cross-Debate, user-decided rounds)

**Aggressive Risk Officer**
> Champion high-risk, high-reward opportunities. Fixate on the potential for doubling and growth momentum. Must name and rebut every conservative argument from the other two officers with data-driven, forceful debate.

**Conservative Risk Officer**
> Lifetime mission: preserve capital, crush volatility. Use the bleakest "doomsday lens" to find risk bombs. Point out how the plan endangers capital. Provide the most cautious exit path.

**Neutral Risk Officer**
> Maintain the objective balance, weighing dividends and dangers. Factor in macro cycles, economic shifts, and asset allocation hedging. Challenge both the aggressive side ("delusional?") and the conservative side ("paranoid?").

After each cross-debate round, ask the user:
> "Risk stress test round N complete. Add another round? Or have the Fund Manager rule directly?"

**⏸️ Pause after Stage 4** — After the stress test, ask:
> "Three-way risk stress test complete. Proceed to Stage 5: Fund Manager Final Ruling?"

---

### Stage 5: Fund Manager Final Ruling

**Fund Manager**
> Distill the essence from all three risk officers' debate. Issue the irreversible, final trading directive.

**Position Rating (pick exactly one)**:
- `Buy` — Full conviction, heavy position or significant increase
- `Overweight` — Outlook is well-supported, gradually increase exposure
- `Hold` — Wait and see, preserve ammunition
- `Underweight` — Reduce exposure, take profits
- `Sell` — Exit decisively, or stay far away

**Mandatory Output (3 items)**:
1. **Rating**: State exactly one of the five action words above
2. **Executive Summary**: Condensed battle orders — entry method, max position size, risk threshold red lines, action timeframe
3. **Deep Investment Thesis**: Clear, detailed final reasoning. All arguments anchored to the analysts' debate points and historical mistake reflections

---

## Stage 6: PDF Report Generation (Optional)

After all 5 stages are complete, optionally generate a professional PDF report.

### 1. Generate HTML Report

Assemble all stage content into a well-formatted HTML file:
- Professional investment report style (dark headers, clean tables, highlighted data)
- Each agent's analysis as an independent section, color-coded
- Key data (rating, stop-loss, entry price) prominently styled
- Report timestamp and data source notes
- Use inline CSS only, no external dependencies
- CJK font stack: `"PingFang SC", "Microsoft YaHei", "Noto Sans CJK SC", sans-serif`
- Include `"Noto Color Emoji"` in font-family for emoji rendering

### 2. HTML → PDF Conversion

Use Chromium headless mode:

```bash
/path/to/chromium --headless --disable-gpu --no-sandbox \
  --print-to-pdf=output.pdf --print-to-pdf-no-header input.html
```

**Prerequisites**:
- CJK fonts installed on the system (e.g., `google-noto-sans-cjk-ttc-fonts`)
- Emoji font installed (e.g., `google-noto-emoji-color-fonts`)
- Run `fc-cache -fv` after installing new fonts
- Verify: PDF file size should be 1MB+ (fonts embedded). <300KB likely indicates missing fonts

### 3. Deliver Report

Send the PDF via your preferred channel (email, messaging app, etc.) or provide the file path to the user.

**⚠️ Privacy — Never include user portfolio details in the report**:
- No position size, cost basis, or P&L amounts
- Use general terms ("currently at a loss") instead of specifics
- Express position changes as ratios ("up to 1/3 of current position") not absolute numbers
- Stop-loss/target levels are fine (these are general technical conclusions)

---

## Report Structure

```
# [Ticker] Trading Decision Report | [Analysis Date]

## Executive Summary

## Stage 1: Data Reconnaissance
### Technical Analysis Report
### Fundamental Analysis Report
### News & Intelligence Report
### Capital Flow & Sentiment Report

## Stage 2: Bull/Bear Debate
### Round 1: Bull Statement
### Round 1: Bear Rebuttal
### Round 2: Bull Counter-Attack
### Round 2: Bear Counter-Attack
### Research Director Ruling

## Stage 3: Trading Draft
FINAL TRANSACTION PROPOSAL: **BUY/HOLD/SELL**

## Stage 4: Risk Stress Test
### Aggressive Risk Officer
### Conservative Risk Officer
### Neutral Risk Officer
### (Round 2 Cross-Debate)

## Stage 5: Fund Manager Final Ruling
**Rating**: [Buy/Overweight/Hold/Underweight/Sell]
**Executive Summary**: ...
**Deep Investment Thesis**: ...

## Data Sources
```

---

## Iron Rules

1. Must use real, traceable, up-to-date public data
2. Earnings, stock prices, and news must include dates and sources
3. No fabricating performance, market data, research, or sentiment
4. All conclusions must be anchored in intelligence pool facts — no unsupported assertions
5. Risk analysis must explicitly address downside risks — not just upside
6. Final decision must be one of five: Buy / Overweight / Hold / Underweight / Sell
7. Full output in your configured language; maintain professional, rigorous, structured tone
8. If user provides portfolio info, incorporate P&L analysis in risk and trading draft stages
9. Never include user's specific portfolio details in the generated PDF

---

## Troubleshooting

| Problem | Likely Cause | Solution |
|---------|-------------|----------|
| PDF CJK text garbled/blank | Missing CJK fonts | Install CJK font package, run `fc-cache -fv` |
| PDF emoji shows as □ | Missing emoji font | Install emoji font package, run `fc-cache -fv` |
| PDF file abnormally small (<300KB) | Missing fonts → content lost | Install fonts, regenerate |
| Data fetch timeout | Unstable data source | Switch to alternative source |
| API returns errors | Missing or expired credentials | Verify MCP server configuration |
