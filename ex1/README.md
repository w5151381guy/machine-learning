# 摘要

1. 機器學習概述<br>
2. 一元線性回歸<br>
3. 梯度下降法<br>
---
# 機器學習應用

1. 反垃圾郵件（貝葉斯算法）<br>
2. 數據挖掘：Web click data/medical records/biology/engineering<br>
3. 無法編程的場景：自主直升機/筆跡識別/自然語言處理（natural language processing, NLP）/計算機視覺<br>
4. 自治編程：Amazon、Netflix產品推薦<br>
5. 了解人腦學習<br>
---
# 機器學習演算法

### 監督式學習([Supervised learning](https://zh.wikipedia.org/wiki/%E7%9B%A3%E7%9D%A3%E5%BC%8F%E5%AD%B8%E7%BF%92))

1. 會明確給出答案的對錯<br>
* 房產價格預測，由之前的趨勢預測，這屬於回歸問題（regresion problem）<br>
* 乳腺癌，腫瘤大小/年齡（或者引入更多變量）與是否惡性的聯繫，這屬於分類問題（classification）<br>

### 非監督式學習([Unsupervised learning](https://zh.wikipedia.org/wiki/%E9%9D%9E%E7%9B%A3%E7%9D%A3%E5%BC%8F%E5%AD%B8%E7%BF%92))

1. 不會明確給出答案的對錯<br>
* 乳腺癌的例子裡只給出數據點而不告訴你是否惡性，將數據范圍分為兩個集群<br>
* Google新聞<br>
* 組織計算集群、社交網絡分析、市場劃分、天文數據分析<br>
* 雞尾酒會問題：音頻分離<br>
* Reinforcement learning、recommender systems<br>
---
# 一元線性回歸（Linear Regression with single variable）——模型表示（model representation）

1. 監督式學習過程：訓練數據->學習算法->提出假設函數h<br>
2. h(x)=θ0+θ1*x，選擇合適的參數來吻合訓練數據<br>
3. 效用函數：函數值與真實價格平方差之和除以數據量最小，J(θ0,θ1)= 1/2m∑1m(h(xi) - yi)<br>
4. 簡化假設：θ0=0即h(x)=θ1*x，如此J(θ1)變成一個二次函數，有最低點<br>
5. 等值線圖（[contour plot](https://zh.wikipedia.org/wiki/%E7%AD%89%E9%AB%98%E7%B7%9A)）：若不做簡化，則價值函數就從平面二次函數變為三維中的曲面（MATLAB實現），就可以在自變量平面上畫等值線<br>
---

# 梯度下降法（[Gradient descent](https://zh.wikipedia.org/wiki/%E6%A2%AF%E5%BA%A6%E4%B8%8B%E9%99%8D%E6%B3%95)）

1. 這是個局部方法，因為它依賴的是當前這一點的梯度方向和大小，順著梯度的方向邁步子（就像下山一樣），步子大小由梯度大小決定<br>
2. 需要計算偏導數，並指定α<br>
3. learing rate：算法中的α的值，需要我們選定，α選得太小，下降速度太慢；α選得太大，有可能因為步子過大而導致本應收斂的算法無法收斂甚至發散<br>
4. 如果設計合理，梯度下降法是能夠收斂到一個局部最小解上的，即使算法過程中α是固定的；因為在最小解附近，隨著每一步越來越逼近最小解，梯度大小不斷變小（因為最小解點處梯度值為零），下一步的步子也越來越小，慢慢就會收斂於最小解<br>
5. 線性回歸中的梯度下降法：針對之前的線性回歸的例子，對效用函數做梯度下降（偏導數計算從略）<br>
6. 為了保證算法流暢性，可以把初始點取在一個局部範圍裡；或者對於凸函數（[convex function](https://zh.wikipedia.org/wiki/%E5%87%B8%E5%87%BD%E6%95%B0)）來說，具有全局意義<br>
