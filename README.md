# tabelog_to_googlemap
# 🍣 Tabelog 高評分餐廳擷取器

本專案是一個簡單實用的 Python 工具，可以自動從 [Tabelog 食べログ](https://tabelog.com) 抓取指定城市的前幾頁餐廳列表，並：

- 擷取「店名、評分、店家網址」
- 過濾評分高於指定門檻的餐廳
- 自動從每家餐廳的頁面抓取詳細地址
- 產生可點選的 Google 地圖搜尋連結
- 匯出為 `.csv` 檔案，方便查找與分享！

---

## 🧰 功能 Features

- ✅ 抓取多頁 Tabelog 列表資料
- ✅ 過濾高於指定評分的餐廳
- ✅ 自動進入每家店的詳細頁擷取地址
- ✅ 產生 Google Maps 搜尋連結（精準搜尋）
- ✅ 輸出為可用於 Excel 或 Google Maps 的 CSV 清單

---


```bash
pip install requests beautifulsoup4 pandas tqdm
🚀 使用方式 Usage
開啟 tabelog_scraper.py（或你命名的檔案）

編輯上方的參數：

python
複製
編輯
base_url = "https://tabelog.com/tokyo/rstLst/"  # 修改地區如 osaka、kyoto URL必須是日文界面
page_count = 3                                   # 要抓取的頁數
rating_threshold = 3.5                           # 評分門檻
output_csv_name = "tabelog_高評分清單.csv"       # 匯出檔名
執行後會自動顯示進度與完成訊息，CSV 檔案會出現在同一資料夾下。
中文網站版:
base_url         = "https://tabelog.com/tw/tokyo/rstLst/cafe"  # 不帶 /{page}/
page_count       = 5                                         # 要爬的頁數 n
rating_threshold = 3.8                                       # 評分門檻
output_file      = "tabelog_high_score.csv"                  # 輸出檔名
pause_per_item   = 0.5                                       # 請求間隔（秒）
'''bash
📝 注意事項
尊重 robots.txt：請先確認目標站點允許爬取

延遲請求：建議 pause_per_item ≥ 0.5s，避免過度負載

錯誤重試：預設遇 429 會自動指數退避重試
