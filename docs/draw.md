# 繪圖

將 ComfyUI 的 workflow 導出為 API 會得到一個 JSON 檔案。

## 設定步驟

### 1. 放置 JSON 檔案
將 JSON 檔案放到以下路徑：
```
D:\AIComp\CoGPT-build-250823\CoGPT\draw\
```

### 2. 修改 API 設定檔
更改 `D:\AIComp\CoGPT-build-250823\CoGPT\Controller\comfyui_api.py` 檔案：

#### 修改模板路徑
找到 `load_workflow_template` 方法並修改：
```python
def load_workflow_template(self):
    template_path = Path("draw/Game.json")  # 修改這邊為您的JSON檔名
    print(f"load template: {template_path}")
    with open(template_path, 'r', encoding='utf-8') as f:
        return json.load(f)
```

