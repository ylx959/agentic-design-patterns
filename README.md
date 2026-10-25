# agentic-design-patterns

用可執行的 Jupyter Notebook 動手實作 **Agentic AI 的設計模式**：反思（Reflection）、工具使用（Tool Use）、規劃（Planning）、多智能體（Multi-Agent），以及評估（Evaluation）。

每個設計模式都是一個資料夾，裡面放了幾個不同的範例。每個範例都包含 notebook 和它需要的程式碼與資料，說明全部使用繁體中文。

如果想要了解更多[agentic-ai](https://github.com/datawhalechina/agentic-ai)底層邏輯與觀念,請去這個連結,此repo代碼也都是從那裡來的。

## 目錄

### 🔁 [reflection-design-pattern](reflection-design-pattern/)：反思
讓 LLM 檢查自己的輸出，再根據回饋改進。

| 範例 | 說明 |
| --- | --- |
| [chart-generation](reflection-design-pattern/chart-generation/) | 依咖啡銷售資料生成圖表，由多模態 LLM 審閱第一版圖表後重寫繪圖程式碼 |
| [sql-generation](reflection-design-pattern/sql-generation/) | 把自然語言問題轉成 SQL，並透過反思修正查詢中的錯誤 |

### 🛠️ [tool-use-design-pattern](tool-use-design-pattern/)：工具使用
把 Python 函式交給 LLM，讓它自己決定什麼時候要呼叫哪個工具。

| 範例 | 說明 |
| --- | --- |
| [functions-as-tools](tool-use-design-pattern/functions-as-tools/) | 用 `aisuite` 把一般函式變成 LLM 可呼叫的工具 |
| [email-assistant](tool-use-design-pattern/email-assistant/) | 郵件助理智慧體：用自然語言查詢、寄送、刪除郵件 |

### 🗺️ [planning-design-pattern](planning-design-pattern/)：規劃
讓 LLM 直接寫程式碼當作計畫並執行，完成多步驟任務。

| 範例 | 說明 |
| --- | --- |
| [customer-service-agent](planning-design-pattern/customer-service-agent/) | 太陽眼鏡商店客服：LLM 撰寫 Python 程式來查詢與更新庫存及交易紀錄 |

### 👥 [multi-agent-design-pattern](multi-agent-design-pattern/)：多智能體
讓多個代理、工具與模型協作，組成一條完整的工作流。

| 範例 | 說明 |
| --- | --- |
| [market-research-team](multi-agent-design-pattern/market-research-team/) | 市場調研團隊：搜尋流行趨勢 → 對應商品 → 生成活動視覺與文案 → 產出高管報告 |

### 📏 [evaluation](evaluation/)：評估
量測 agentic 工作流中各個元件的表現。

| 範例 | 說明 |
| --- | --- |
| [component-level-eval](evaluation/component-level-eval/) | 針對研究步驟做元件級評估，檢查檢索來源是否來自可信網域 |

## 快速開始

這些code 你可以去google colab 執行,記得要把套件一起放過去, 但如果你想在本地端執行請依照下面步驟：

```bash
pip install jupyter python-dotenv aisuite openai anthropic pandas matplotlib \
            tinydb tavily-python wikipedia duckdb qrcode requests pillow
```

在專案根目錄建立 `.env`，填入要用到的 API 金鑰：

```
OPENAI_API_KEY=...
ANTHROPIC_API_KEY=...
TAVILY_API_KEY=...
```

接著進入任一範例資料夾，開啟其中的 `.ipynb` 依序執行即可：

```bash
cd reflection-design-pattern/chart-generation
jupyter notebook chart_generation.ipynb
```

> 每個範例都是獨立的，`utils.py` 等輔助檔案必須和 notebook 放在同一個資料夾。

## 致謝

- 課程內容來自 [DeepLearning.AI - Agentic AI](https://learn.deeplearning.ai/courses/agentic-ai/)
- 本專案改編自 [datawhalechina/agentic-ai](https://github.com/datawhalechina/agentic-ai) 的中文翻譯，感謝原專案的所有貢獻者

## License

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="知識共享授權條款" style="border-width:0" src="https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-lightgrey" /></a><br />本作品採用<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">創用 CC 姓名標示-非商業性-相同方式分享 4.0 國際授權條款</a>授權。
