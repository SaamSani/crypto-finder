
# 🚀 Crypto Finder: Market Volume & Sentiment Tracker

This project is a fully automated system that collects, tracks, and visualizes cryptocurrency trading volume, price, and sentiment across major exchanges. It supports daily updates and highlights top trending coins using CoinGecko’s sentiment data.

---

## 🔧 Project Structure

```
crypto-finder/
├── data/
│   ├── todays_data.csv           # Clean data with volume, price, exchange, and sentiment
│   ├── volume_history.csv        # Historical volume for past 7 days
│   ├── volume_change.csv         # Daily % volume change vs previous day
│
├── Untitled.ipynb                # Main pipeline to fetch, format, and export data
├── .gitignore
└── README.md
```

---

## ⚙️ How It Works

1. **Fetches real-time data** from:
   - Binance
   - KuCoin
   - Coinbase
   - Kraken
   - Bitfinex
   - Bitstamp
   - CoinGecko

2. **Cleans and combines** all sources into a single master DataFrame

3. **Engineers key metrics**:
   - `volume_display` in readable billions/trillions
   - `price_display` with 10-decimal formatting
   - `sentiment_score` based on CoinGecko trending symbols
   - `volume_change_%` computed daily (up to 7-day history)

4. **Exports data to**:
   - `todays_data.csv` for current metrics
   - `volume_change.csv` for Tableau
   - `volume_history.csv` (rotates weekly)

---

## 📊 Tableau Dashboard

You can connect Tableau directly to the `data/` folder to create:

- Daily coin volume bar charts
- Volume change % trends
- Sentiment-based filtering (trending coins)
- Exchange-wise comparison visuals

**📍 Tip:** Format price columns to show 10 decimal places in Tableau.

---

## 📅 Daily Update Logic

- Appends each day's data to `volume_history.csv`
- Automatically filters history to the past 7 days
- Prevents duplicate entries for the same coin/date
- Computes % change vs previous day for every coin

---

## 🧠 Example Output (`todays_data.csv`)

| Coin     | Volume Display | Price Display      | Exchange | Sentiment Score |
|----------|----------------|--------------------|----------|-----------------|
| PEPE     | 681.21 billion | $0.0000079840      | KuCoin   | 1               |
| DOGE     | 1.32 trillion  | $0.0834120000      | Binance  | 0               |
| BTC      | 34.5 billion   | $94,348.0000000000 | Binance  | 0               |

---

## 📦 Requirements

- Python 3.8+
- `pandas`, `numpy`, `requests`, `matplotlib`, `seaborn`
- (Optional) Tableau for data visualization

```bash
pip install pandas numpy requests matplotlib seaborn
```

---

## 🧠 Features Used

| Feature             | Description                                     |
|---------------------|-------------------------------------------------|
| `volume_display`    | Volume in human-readable format (e.g., billion) |
| `price_display`     | Up to 10 decimal places                         |
| `sentiment_score`   | 1 if trending on CoinGecko, else 0              |
| `volume_change_%`   | Daily percent change in volume                  |

---

## 📬 Contact

Built by [Saam Sani](https://github.com/SaamSani)  
For questions or collaboration, open an issue or connect via [LinkedIn](https://linkedin.com/in/SaamSani)
