# Alex專案 Vercel部署完整指南

## 🚀 立即部署步驟

### Step 1: 準備檔案結構
建立以下檔案結構：
```
alex-war-analyzer/
├── vercel.json              # Vercel配置
├── requirements.txt         # Python依賴
├── api/
│   └── main.py             # 主要Python文件
└── README.md               # 專案說明
```

### Step 2: 建立檔案內容

#### 1. 建立 `vercel.json`
```json
{
  "version": 2,
  "name": "alex-war-analyzer",
  "builds": [
    {
      "src": "api/main.py",
      "use": "@vercel/python"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "api/main.py"
    }
  ],
  "env": {
    "ANTHROPIC_API_KEY": "@anthropic_api_key"
  },
  "functions": {
    "api/main.py": {
      "maxDuration": 300,
      "memory": 1024
    }
  }
}
```

#### 2. 建立 `requirements.txt`
```
fastapi==0.104.1
uvicorn==0.24.0
python-multipart==0.0.6
anthropic==0.7.8
python-dotenv==1.0.0
pydantic==2.5.0
```

#### 3. 建立 `api/main.py`
把Claude Code生成的Python代碼複製到這個檔案中。

### Step 3: GitHub Repository設定

#### 1. 建立GitHub Repository
```bash
# 在電腦上建立專案資料夾
mkdir alex-war-analyzer
cd alex-war-analyzer

# 初始化Git repository
git init

# 複製所有檔案到資料夾中
# (vercel.json, requirements.txt, api/main.py)

# 建立.gitignore
echo "__pycache__/
*.pyc
.env
.DS_Store
*.log" > .gitignore

# 第一次commit
git add .
git commit -m "Initial Alex WAR Analyzer for Vercel deployment"

# 連接到GitHub repository (需要先在GitHub建立)
git remote add origin https://github.com/你的用戶名/alex-war-analyzer.git
git branch -M main
git push -u origin main
```

### Step 4: Vercel部署

#### 1. 登入Vercel
- 前往 https://vercel.com
- 使用GitHub帳號登入

#### 2. Import專案
- 點擊 "New Project"
- 選擇你的GitHub repository "alex-war-analyzer"
- 點擊 "Import"

#### 3. 設定環境變數
在Vercel Dashboard中：
- 前往 Project Settings → Environment Variables
- 新增環境變數：
  - Name: `ANTHROPIC_API_KEY`
  - Value: `你的Claude API Key`
  - Environment: All (Production, Preview, Development)

#### 4. 部署
- 點擊 "Deploy"
- 等待部署完成

### Step 5: 測試部署

#### 1. 訪問網站
部署完成後，Vercel會提供URL，例如：
`https://alex-war-analyzer.vercel.app`

#### 2. 測試功能
- 首頁載入 ✅
- 健康檢查: `/health` ✅
- API資訊: `/api/info` ✅
- WAR檔案上傳測試 ✅

## 🛠️ 故障排除

### 常見問題與解決方案

#### 1. Python模組導入錯誤
```bash
# 檢查requirements.txt是否正確
# 確保所有依賴都已列出
```

#### 2. 環境變數問題
```bash
# 確認ANTHROPIC_API_KEY已正確設定
# 檢查API Key是否有效
```

#### 3. 檔案大小限制
```bash
# Vercel有檔案上傳限制
# 確保WAR檔案 < 100MB
```

#### 4. 超時問題
```bash
# 如果分析時間過長，調整maxDuration
# 在vercel.json中增加時間限制
```

### 除錯指令
```bash
# 本地測試
cd api
uvicorn main:app --reload --port 8000

# 檢查logs
vercel logs https://your-project.vercel.app

# 重新部署
git commit -am "Fix deployment issues"
git push
```

## 📋 部署檢查清單

### 部署前檢查
- [ ] 所有檔案已建立並放在正確位置
- [ ] vercel.json配置正確
- [ ] requirements.txt包含所有依賴
- [ ] GitHub repository已建立並推送
- [ ] Claude API Key已取得

### 部署後檢查
- [ ] 網站可正常訪問
- [ ] `/health` 端點回應正常
- [ ] WAR檔案上傳功能正常
- [ ] 分析結果正確顯示
- [ ] 效能指標符合預期

### Alex展示準備
- [ ] 網站URL已確認可用
- [ ] 準備63MB測試WAR檔案
- [ ] 競爭優勢訊息清晰展示
- [ ] 分析結果專業化程度確認
- [ ] Demo流程練習完成

## 🎯 給Alex的展示重點

### 1. 立即可用性
"這個工具現在就能用，不需要等18個月開發"

### 2. 效能優勢
"我們7秒完成，樂達90分鐘失敗"

### 3. 專業分析
"針對COBOL-to-Java的executeSQL模式識別"

### 4. 成本效益
"$108K vs 傳統$400K，立即ROI"

## 🔗 部署完成後的URLs
- 主頁: `https://alex-war-analyzer.vercel.app/`
- 健康檢查: `https://alex-war-analyzer.vercel.app/health`
- API文件: `https://alex-war-analyzer.vercel.app/docs`

## ⚡ 緊急聯絡
如果部署遇到問題：
1. 檢查Vercel Dashboard的部署日誌
2. 確認所有環境變數設定正確
3. 檢查GitHub repository檔案結構
4. 必要時重新部署

---

**🚀 部署完成後，立即通知Alex可以開始測試！**# Alex WAR Analyzer - Demo Ready Fri Jul  4 10:31:27 CST 2025
