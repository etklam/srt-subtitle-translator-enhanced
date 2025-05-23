# SRT 字幕翻譯器

這是一個基於 Ollama 的 SRT 字幕檔翻譯工具，支援多種語言之間的翻譯，並提供多項實用功能。

## 版權聲明
本專案基於 MIT License 授權的原始程式碼進行修改和擴展。原始程式碼的版權歸原作者所有，修改後的版本同樣遵循 MIT License 條款。

## 安裝步驟

1. 確保已安裝 Python 3.6 或更新版本
2. 安裝必要套件：
   ```bash
   pip install -r requirements.txt
   ```

## 使用方法

1. 運行程式：
```bash
python main.py
```

2. 可以通過以下方式添加 SRT 檔案：
   - 點擊「選擇 SRT 檔案」按鈕
   - 直接拖放檔案到視窗中（需要 tkinterdnd2 支援）

## 注意事項

- 確保 Ollama 服務運行中（http://localhost:11434）
  - 安裝ollama
  - 在`CMD`中運行`ollama run huihui_ai/aya-expanse-abliterated`, 第一次運行時會下載模型, 第二次會很快 
- 建議使用 aya 模型
- 並行請求數建議設為 3
- 翻譯大量字幕時請耐心等待

1. 備份說明
   - 備份功能只在選擇「取代原始檔案」模式時啟用
   - 備份檔案會自動保存在原始檔案所在目錄的 backup 資料夾中
   - 如果備份失敗會顯示警告訊息，但不會中斷翻譯過程

## 個人更新
   - 程式碼個人化(我不是python programmer, 清理掉我不能理解的部分更有利我管理)
     - 移除了未使用的功能，使程式碼更加簡潔
     - 重構了部分代碼結構，提高可維護性
     - 優化了錯誤處理機制
   
   - 新增功能
     - 批量處理功能
       - 支援整個文件夾的 SRT 檔案批量添加
       - 自動跳過已翻譯的中文字幕（*.zh_tw.srt）
       - 自動過濾重複檔案
       - 顯示添加和跳過檔案的統計信息
     
     - 調試模式 (Debug Mode)
       - 在控制台實時顯示翻譯進度
       - 顯示原始文本和翻譯結果的對照
       - 方便檢查翻譯質量和調試問題
     
     - 自動清理功能
       - 可選在翻譯前自動清理 SRT 檔案
       - 移除只包含括號內文字的字幕（如 Whisper AI 產生的不準確音效描述）
       - 自動備份原始檔案
       - 顯示清理進度和統計信息（總字幕數/已清理數）
     
     - 使用者介面改進
       - 添加了清理模式和調試模式的開關選項
       - 優化了進度顯示
       - 改進了錯誤提示信息
       - 改進了按鈕和選項的佈局

     - 取代原始檔案

## 授權協議

MIT License