# Applied-Econometrics-ARIMA-model-reservoir-data

## 本專案為水庫資料分析與時間序列模型的應用
## 內容分為以下幾個部分：

### 1. 資料整理與探勘
      - heatmap
      - time-trend plot
### 2.  問題討論
> 水庫有效蓄水量是「存量」，但降雨量以及集水區流入、流出皆為「流量」。因此在上方圖示的呈現可能恰當，所以將「有效蓄水量」改為「蓄水變化量」在重複以上步驟觀察變數上的關係。

> 再改變資料頻率進行觀察，也就是將日資料轉為月資料，針對不同資料頻率下變數之間的關係是否出現變化。

### ARIMA模型建立
#### Step 1：unit root test
* 在使用ARIMA model或是其他計量時間序列模型都需要確認資料是否存在單根後才能進行模型建立，否則模型會呈現「spurious result」。

#### Step 2：Parameter Selection
##### 在模型建立這個部分，我嘗試了兩個參數挑選的方式建立模型；分別為
1. Python 套件 `pmdarima.auto_arima`
2. 計量時間序列分析: autocorrelation and partial autocorrelation functions

#### 模型比較
##### 透過兩個不同參數挑選方法建立的ARIMA模型，再以MSE為模型比較 依據，我們可以發現以「計量時間序列分析」此方法挑選參數而建構出的模型表現優於透過套件挑選參數的模型。


### 延伸討論：Application of autocorrelation function on LSTM
* autocorrelation function選擇參數的方式亦可推廣至LSTM模型中選擇其rolling window length，因為LSTM就是一個 generalized AR model in LSTM frame work
