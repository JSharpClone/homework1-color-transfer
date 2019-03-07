# CSFX HW 1

```
Team #15
107062503 許博皓
10706XXXX 鄭家鈞
107062566 黃鈺程
```

## Introduction

我們準備了三張圖片：

[人臉](https://i.imgur.com/4S6XvLu.png)
[蘋果](https://i.imgur.com/VKd1dfg.png)
[橘子](https://i.imgur.com/vKQNUwr.jpg)

進行四個實驗：

1. 蘋果 轉換成 **橘子風格**
2. 人臉 轉換成 **橘子風格**
3. 橘子 轉換成 **蘋果風格**
5. 人臉 轉換成 **蘋果風格**

並使用四種 model 來實驗。

---

另外，我們有對程式碼進行一點小修改：
![](https://i.imgur.com/m65TjNg.png)

根據 tqdm 的文檔，當 `tqdm` 與 `enumerate` 相互使用了，應寫成 `enumerate(tqdm())` 而不是 `tqdm(enumerate())`，因為 `len` 無法作用在 `enumerate` 的結果上，造成 `tqdm` 抓不到總共有幾個 iteration。

## Exp: Cycle GAN (64x64) with our weight
訓練：

![](https://i.imgur.com/DqdWR1i.png)

轉成橘子（結果在左，原圖在右）：

![](https://i.imgur.com/50O1Ozp.png)
![](https://i.imgur.com/dymfNnS.png)

轉成蘋果（結果在左，原圖在右）：

![](https://i.imgur.com/x6U6T3m.png)
![](https://i.imgur.com/obPRqBF.png)


## Exp: Cycle GAN (256x256) with our weight

訓練：

![](https://i.imgur.com/bZKxKKS.jpg)


轉成橘子（結果在左，原圖在右）：

![](https://i.imgur.com/ORLvC2b.png)
![](https://i.imgur.com/ZLEAbwp.png)

轉成蘋果（結果在左，原圖在右）：

![](https://i.imgur.com/5EM3cCP.png)
![](https://i.imgur.com/vyGU7aS.png)

## Exp: Cycle GAN with pretrained weight

轉成橘子（結果在左，原圖在右）：

![](https://i.imgur.com/cTv8GgO.png)
![](https://i.imgur.com/YBO7T4E.png)

轉成蘋果（結果在左，原圖在右）：

![](https://i.imgur.com/XZe8yo4.png)
![](https://i.imgur.com/qPempbc.png)


## Exp: Color Transfer

Source 為風格，Target 為要轉換的圖片，Transfer 為結果。

![](https://i.imgur.com/hBamxGK.png)
![](https://i.imgur.com/PV9R4bI.png)
![](https://i.imgur.com/LqG1EjR.png)
![](https://i.imgur.com/1dqCxIb.png)

## Report

根據以上實驗，我們有三個結論：

1. Color Transfer 基本就是調色調而已，相對 Cycle GAN 效果並不好。但速度非常快。
2. size 為 64 的結果效果較差，顆粒感重。而 size 為 256 則效果較好，看起來自然許多，也沒有顆粒感，但就需要訓練比較久。
3. 和 pre-trained weights 相比，pre-trained 的效果較好，蘋果轉橘子的光澤較為自然。

## Misc.

我們還使用了其他 dataset 訓練。一些結果如下：

### horse2zebra

訓練：
![](https://i.imgur.com/IJk1PlH.png)

轉成馬（結果在左，原圖在右）：

![](https://i.imgur.com/BtYdLQB.png)

轉成斑馬（結果在左，原圖在右）：

![](https://i.imgur.com/nIF3quX.png)
