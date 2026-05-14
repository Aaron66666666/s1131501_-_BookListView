BookListView - 古典文學借書系統
這是一個基於 C# Windows Forms 開發的簡單圖書瀏覽與借閱系統。使用者可以透過不同的檢視模式（ListView）查看書籍資訊，並點擊書籍進行借閱登記。

🚀 功能特點
多種檢視模式切換：支援大圖示、詳細資料、小圖示、清單、以及平鋪（Tile）模式。

動態資料呈現：程式啟動時自動載入書籍名稱、作者及類別。

互動式借閱機制：

雙擊（Activate）書籍項目觸發借閱流程。

具備確認對話框（MessageBox）防止誤點。

重複借閱檢查：系統會自動判斷書籍是否已在借閱清單中，避免重複新增。

🛠 使用控制項
ComboBox (cmbView): 切換 ListView 的 View 屬性。

ListView (lvwBooks): 核心顯示區域，展示書籍的詳細資訊與圖示。

ListBox (lstBorrow): 紀錄使用者已選擇借閱的書籍清單。

📖 程式邏輯說明
1. 初始化資料 (frmBooks_Load)
在表單載入時，程式會執行以下操作：

初始化下拉選單（ComboBox）的選項。

設定 ListView 的欄位（書名、作者、類別）。

使用 BeginUpdate() 與 EndUpdate() 最佳化效能，並透過迴圈將陣列資料填入 ListViewItem。

2. 切換檢視 (cmbView_SelectedIndexChanged)
透過 switch 判斷索引值，動態修改 lvwBooks.View：

0: LargeIcon (大圖示)

1: Details (詳細資料)

2: SmallIcon (小圖示)

3: List (清單)

4: Tile (大圖示加詳細資料)

3. 借閱處理 (lvwBooks_ItemActivate)
當使用者雙擊書籍時：

取得選取項目的書名。

檢查 lstBorrow 是否已包含該書。

彈出詢問視窗，若使用者點選「是」，則將書名加入右側清單。

📂 資料結構
程式內建了三組對應的字串陣列作為資料來源：

b_name: 書名（如：三國演義、紅樓夢...）

author: 作者（如：羅貫中、曹雪芹...）

kind: 類別（如：章回小說、戲曲...）

📋 開發者資訊
專案名稱: s1131501_林昱綸_BookListView

開發語言: C#

框架: .NET Windows Forms# s1131501_林昱綸_BookListView
