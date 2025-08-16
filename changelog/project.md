根據您的項目代碼，這是系統的技術架構：

## 後端架構 (Python)

### 核心框架
- **FastAPI** - 現代化的Python Web框架，提供自動API文檔和高性能
- **SQLite** - 輕量級數據庫，適合中小型應用
- **Uvicorn** - ASGI服務器，運行在端口6001

### 項目結構
```
CoGPT/
├── Controller/dashboard/     # API路由控制器
│   ├── knowledge_base.py    # 知識庫CRUD
│   ├── upload_file.py       # 文件上傳
│   ├── chat_controller.py   # WebSocket聊天
│   └── user.py             # 用戶管理
├── Model/                   # 數據模型層
│   ├── BaseModel.py        # 基礎模型類
│   ├── User.py             # 用戶模型
│   └── KnowledgeBase.py    # 知識庫模型
├── Service/                 # 業務邏輯層
│   ├── llm.py              # LLM調用服務
│   ├── embedding.py        # 向量化服務
│   └── upload_file.py      # 文件處理服務
└── main.py                 # 應用啟動入口
```

### 技術特色
- **MVC架構** - 控制器、模型、服務分離
- **WebSocket** - 實時聊天功能，支持個人和群組
- **權限系統** - 基於角色的訪問控制(RBAC)
- **向量數據庫** - Chroma，用於知識庫檢索
- **多模型支持** - 集成Groq、OpenAI等多個LLM提供商

## 前端架構 (Vue.js)

### 核心技術棧
- **Vue 3** - 使用Composition API
- **Vite** - 現代化構建工具
- **Tailwind CSS** - 原子化CSS框架
- **Vue Router** - 單頁應用路由

### 項目結構
```
View/src/
├── components/              # 可復用組件
│   ├── basicSetting.vue    # 基本設定組件
│   ├── knowledgeBaseSetting.vue # 知識庫設定
│   └── uploadWindow.vue    # 文件上傳組件
├── views/                   # 頁面組件
│   ├── DashboardLayout.vue # 儀表板布局
│   └── KnowledgebaseView.vue # 知識庫頁面
├── utils/                   # 工具函數
│   └── fetchWithToken.js   # 帶Token的API調用
└── main.js                 # 應用入口
```

### 狀態管理
- **Vuex** - 中央化狀態管理
- **組件通信** - Props/Events + 自定義事件

