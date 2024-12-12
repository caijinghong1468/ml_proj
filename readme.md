# ML_PROJ

這是一個機器學習專案，在判定PTT黑特政治版文章的政治傾向

## 整個流程簡介
##### 從PPT抓取資料 --> 初步過濾文章內容 --> 使用Jieba進行斷詞 --> 過濾斷詞結果中的停用詞 --> 進行模型訓練 --> 產生結果後做不同模型的比較

## 解釋model(模型)及label(標準答案)、feature(特徵值)的關係

`label`：可以想成這個些資料的標準答案，model會利用這些標準答案去學習。  

`feature`：特徵值就像是把每個文章的關鍵字抓出來。  

我們把每個文章的feature(關鍵字)以及label(標準答案)丟給model做學習，因此當model遇到新的文章時，看到之前學習過的feature(關鍵字)就可以推算出label(標準答案)。  
當然model不會每次都有辦法預測的精準，所以我們的報告要做的是比較不同model預測出來的數據，哪些較好、哪些較差。

<img src="/img/text.png" alt=" "  >

## 研究動機


## 欲解決的問題
```
1.  以PEST分析來看，
    P(政治)
    企業需了解政策走向及相關利益相關方的政治立場，進而調整應對策略。
    E(經濟)
    消費者信任與品牌價值：品牌在多元化市場中，需避免觸碰政治敏感地帶。
    S(社會)
    社交媒體上的激進或極端內容可能威脅公共秩序，或有帶風向的可能。
    T(技術)
    AI模型容易因網路上客觀性的數據偏差而產生不當的政治傾向分析，可能引發爭議。
  
    （濃縮版）
    企業需根據政策趨勢與利益相關方立場調整策略，避免觸及政治敏感議題以維護品牌信任。
    在社會層面，需警惕社交媒體上的極端內容可能影響公共秩序與輿論方向；
    技術層面則需注意AI因數據偏差引發政治傾向爭議，確保分析的客觀性與公正性。

2.  媒體釋讀:
    可以看自己看得文章立場是不是很相似，
    可以確保自己是不是在同溫層

3.  風向判斷:
    政黨可以知道現在網路上風向是怎麼樣。
    如果有大量負評語好評，可以推測哪個政黨有在用網軍，去加以應對。
```
## 參考資料
[PPT HatePolitics](https://www.ptt.cc/bbs/HatePolitics/index.html)	

## 網頁爬蟲
在 `webcrawler.ipynb` 中，使用了 `Python` 實作來抓取 PTT 黑特政治版的文章。

資料集有 1327 筆數據。

功能:
- 從文章中提取內容元素
- 過濾文章內容，僅保留『中文』字元和『數字』。
- 使用 『Jieba』 進行分詞，加入『自定義詞典』以調整文章的分詞
- 『jieba』斷詞結果中的停用詞
  
## 標籤
使用七個標籤來分類文章的政治傾向：

<img src="/img/label.png" alt=" "  width=200px height=240px/>


## 特徵值
使用 TF-IDF 作為特徵表示方法


## 模型


## 分析
 
## 結論
