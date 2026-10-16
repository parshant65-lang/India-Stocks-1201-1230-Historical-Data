# India-Stocks-1201-1230-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1201 to 1230)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1201-1230-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1201 to 1230)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1201 | `GSPCROP` | GSP Crop Science Limited | `GSPCROP.NS` |
| 1202 | `GSPLTRANS` | GSPL Transmission Limited | `GSPLTRANS.NS` |
| 1203 | `GSS` | GSS Infotech Limited | `GSS.NS` |
| 1204 | `GTECJAINX` | G-TEC JAINX EDUCATION LIMITED | `GTECJAINX.NS` |
| 1205 | `GTL` | GTL Limited | `GTL.NS` |
| 1206 | `GTLINFRA` | GTL Infrastructure Limited | `GTLINFRA.NS` |
| 1207 | `GTPL` | GTPL Hathway Limited | `GTPL.NS` |
| 1208 | `GUFICBIO` | Gufic Biosciences Limited | `GUFICBIO.NS` |
| 1209 | `GUJALKALI` | Gujarat Alkalies and Chemicals Limited | `GUJALKALI.NS` |
| 1210 | `GUJAPOLLO` | Gujarat Apollo Industries Limited | `GUJAPOLLO.NS` |
| 1211 | `GUJENERGY` | GUJARAT ENERGY LIMITED | `GUJENERGY.NS` |
| 1212 | `GUJRAFFIA` | Gujarat Raffia Industries Limited | `GUJRAFFIA.NS` |
| 1213 | `GUJTHEM` | Gujarat Themis Biosyn Limited | `GUJTHEM.NS` |
| 1214 | `GULFOILLUB` | Gulf Oil Lubricants India Limited | `GULFOILLUB.NS` |
| 1215 | `GULFPETRO` | GP Petroleums Limited | `GULFPETRO.NS` |
| 1216 | `GULPOLY` | Gulshan Polyols Limited | `GULPOLY.NS` |
| 1217 | `GVKPIL` | GVK Power & Infrastructure Limited | `GVKPIL.NS` |
| 1218 | `GVPIL` | GE Power India Limited | `GVPIL.NS` |
| 1219 | `GVPTECH` | GVP Infotech Limited | `GVPTECH.NS` |
| 1220 | `GYFTR` | Gyftr Limited | `GYFTR.NS` |
| 1221 | `HALDER` | Halder Venture Limited | `HALDER.NS` |
| 1222 | `HALDYNGL` | Haldyn Glass Limited | `HALDYNGL.NS` |
| 1223 | `HALEOSLABS` | HALEOS LABS LIMITED | `HALEOSLABS.NS` |
| 1224 | `HAMPTON` | Hampton Sky Realty Limited | `HAMPTON.NS` |
| 1225 | `HAPPSTMNDS` | Happiest Minds Technologies Limited | `HAPPSTMNDS.NS` |
| 1226 | `HAPPYFORGE` | Happy Forgings Limited | `HAPPYFORGE.NS` |
| 1227 | `HARDWYN` | Hardwyn India Limited | `HARDWYN.NS` |
| 1228 | `HARIOMPIPE` | Hariom Pipe Industries Limited | `HARIOMPIPE.NS` |
| 1229 | `HARRMALAYA` | Harrisons  Malayalam Limited | `HARRMALAYA.NS` |
| 1230 | `HARSHA` | Harsha Engineers International Limited | `HARSHA.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream GSPCROP 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1201-1230-Historical-Data/main/GSPCROP/1m/2026/10/GSPCROP_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
