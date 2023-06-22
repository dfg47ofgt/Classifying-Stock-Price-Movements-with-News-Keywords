## 專案名稱 
**Classifying-Stock-Price-Movements-with-News-Keywords**


## 專案介紹
在本專案中，我們採用從mobile01，ppt以及yahoo股市收集的新聞資訊，作為預測股市走勢的主要依據。我們運用自然語言處理（Natural Language Processing，NLP）技術，將新聞內容轉化為向量空間模型（Vector Space Model，VSM），以便進行深度分析。之後，我們將這些向量化的數據作為輸入，透過各種機器學習分類器進行訓練，以預測相關股票的未來價格漲跌趨勢。透過這種方式，我們的專案能夠為投資者提供更精確、具有預測性的市場分析，從而協助他們在投資決策中獲得更高的勝算。本專案已陽明2609為例子做訓練，採移動回測的方式去驗證模型的準確度，最後結果可達到89.4%的出手率以及60.5%的準確度。


## Code說明
**Monpa批次切辭.ipynb:** 在這份notebook中，我們進行資料的前置處理工作，包含了以下三個部分:

- 利用Word2Vec來找出與"2609陽明"相關性最高的前六個詞彙，作為後續新聞資料篩選的標準。
- 刪除stopwords，即去除不具有太多語義信息的常用詞，如"的"、","不","為"等，以降低雜訊對分析的影響。
- 採用Monpa套件進行新聞的段詞切分，將文章切割成單獨的詞彙，方便後續處理。

**篩選文章與關鍵詞.ipynb**: 這份notebook專注於文章的篩選以及關鍵詞的抽取工作:
- 我們根據股價的信賴區間來定義漲跌，以此標準分類出兩類文章，作為後續模型訓練的數據集。
- 關鍵詞挑選的部份，我們使用了TF-IDF、n-gram、卡方檢定(chi-square)以及主題模型(LDA)等方法，根據這些指標的結果選出最具代表性的關鍵詞，並將這些詞彙轉換成向量空間模型(VSM)的形式。

**模型訓練測試.ipynb**: 最後，我們在這份notebook中，進行機器學習模型的訓練和驗證:
- 我們訓練多種分類器，並驗證各模型的準確率和分類結果，找出效果最佳的模型。
- 訓練方式採用"移動窗口回測"的策略，即每四個月的數據作為一次的訓練資料，並用第五個月的數據來驗證模型的預測能力，進行漲跌預測。

## 開發工具、環境
Anaconda3（Python）、Jupyter notebook



















