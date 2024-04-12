# 機械學習 筆記

## AI vs ML vs DL
- AI: Artificial Intelligence(人工智慧) -> 讓機器跟人類一樣有智慧
- ML: Machine Learning(機器學習) -> 透過過往資料中找規則
- DL: Deep Learning(深度學習) -> 機器學習的一招 (類神經網路): 模仿大腦學習

## 機器如何學習

### 機器(電腦)怎麼從資料中找規則?
- 數學、 程式 -> 透過輸入的程式(特徵) 建立模型 (Model)不斷的訓練、修正 模型

## 環境建置
- google colab

## 常用指令
### 檢視google 分配的GPU 位置
```
!nvidia-smi
```

### 透過指令在colab上安裝模組
```
!pip install (model)
```

## 方法一: 簡單線性回歸
- 將資料做一條最適合的線性座表示
- 範例: ml_01.ipynb

### 如何更有效率地找出 w,b

#### 梯度下降(gradient descent)
- 範例: gradient_descent.ipynb
- 根據斜率改變參數

    1. 先計算出 cost function: (真實數據-預測值)^2
    ```
    = (y-y_pred)^2
    = (y-(w*x+b))^2
    ```
    2. 對其結果做微分
    ```
    w方向斜率(對w做微分)
    = 2x(w*x+b-y)
    b方向斜率(對b做微分)
    = 2(w*x+b-y)
    ```
    3. 更新w, b的值
    ```
    更新w:
    w - w方向斜率*學習率
    更新b:
    b - b方向斜率*學習率
    ```

- 學習率(Learning Rate): 步伐大小

    - 學習率不得過大或過小

### 小結: 機器學習過程
1. 準備好資料
2. 設定一個模型
3. 設定一個cost function
4. 設定 optimizer(優化)

## 方法二: 多元線性回歸
- 優點: 資料可以多個特徵
- y=w1*x1+w2*x2+w3*x3....+b -> w1,w2,w3: 特徵
- 求 w1,w2,w3 以及 b 

### 資料預處理 (Label Encoding)
- 並非所有特徵都是數字，所以需要針對資料做預處理動作

### 如何加速 Gradient Descent

#### 利用特徵縮放(Feature Scaling)
- 透過每個特徵分布範圍:

    - 越大的特徵分布,w就需要較小的變動

#### (一): 標準化(Standardization)
```
(x - mean(x)) / x標準差
```

## 方法三:邏輯回歸(Logistic Regression)
- 當資料分佈無法利用一條斜直線

### 分類問題(Classification)
#### Sigmoid Function
```
z = w1*x1 + w2*x2 + w3*x3 .... +b
Sigmoid Function = 1 / 1 + e^-z
```
