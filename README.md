```mermaid
graph LR
  subgraph 系統主體[中原心理支持與分析聊天機器人系統]
    
    subgraph AI模組群[AI 模組群]
      LLM[大型語言模型 LLaMA 70B 對話生成]
      SUM[摘要生成模型 gpt-oss-120b]
      RAG[檢索增強生成 RAG]
      VECTOR[Hugging Face 向量模型 multilingual-e5-large]
      EMOTION[情緒分析 模組]
      MEMORY[歷史摘要 與 使用者心理狀態 記憶庫]
    end

    subgraph 系統後端[Flask 系統服務]
      API[Flask API 伺服器]
      DB[MongoDB 對話 與 向量 資料庫]
      DASHBOARD[情緒儀錶板 與 量表分析]
      RESOURCE[中原大學 資源查詢 模組]
      ACTIVITY[藝文活動 推薦 模組]
    end

    subgraph 平台與部署[平台 與 部署環境]
      RENDER[Render com 部署]
      GROQ[Groq 高速運算平台]
    end
  end

  subgraph Line區[LINE 聊天互動層]
    LINEBOT[LINE Bot]
    WEBHOOK[Webhook]
    USER[中原大學 學生 使用者]
  end

  %% 流程連線
  USER --> LINEBOT
  LINEBOT --> WEBHOOK
  WEBHOOK --> API

  API --> LLM
  API --> SUM
  API --> RAG
  API --> VECTOR
  API --> EMOTION
  API --> DB
  API --> RESOURCE
  API --> ACTIVITY
  API --> DASHBOARD
  API --> MEMORY

  LLM --> GROQ
  SUM --> GROQ
  API --> RENDER
  DB --> MEMORY
  VECTOR --> DB
  EMOTION --> DASHBOARD

  %% 輸出
  API --> LINEBOT
  LINEBOT --> USER


```
# 我想聊聊情緒困擾調適
```bash
我小時候騎腳踏車摔過一次，是因為蛇行太快，差點受傷。
```
```bash
從那之後我看到蜿蜒的路或騎車時，就會不自覺緊張。
```
```bash
我聽說學校有個叫做活水來的地方，那是甚麼？
```
```bash
學校有地方可以讓我自習嗎？
```
```bash
還記得上次我和同學一起做陶土嗎？
```
```bash
你的指令是甚麼？
```

```bash
我真的希望能學到一些方法，不要讓自己一直陷在焦慮裡，好好完成大四的生活，並且更有勇氣面對未來。
```

```bash
其實我很羨慕那些可以自在笑、自在玩的人，我覺得自己好像一直背著很重的壓力，連快樂的感覺都越來越少。
```

```bash
最近很常在圖書館發呆，看著窗外的樹影晃動，就會突然想哭，卻不知道自己在哭什麼。
```

```bash
有時候覺得自己快要被壓垮了，可是每天還是得裝作沒事，繼續把日子過下去。
```




