# Bi-LSTM model for YouTube
機器學習：利用Bi-LSTM訓練模型從YouTube影片標題預測點閱數   
Machine Learning: Predicting Views from YouTube Video Titles Using Bi-LSTM Training Models


## 介紹
針對台灣地區總點閱數前50名的YouTuber，使用YouTube爬蟲取得該YouTube頻道所有影片的影片標題及公開資訊(如：頻道訂閱、影片發佈時間、影片點閱數等)，將取得的影片標題經自然語言處理後，輸入Bi-LSTM模型作訓練，最終調適出能夠有效從影片標題預測影片點閱數的機器學習模型。

## 預期模型應用
眾所皆知，影片的封面圖以及標題是否吸睛即是決定能否吸引到觀眾流量的最大影響因素之一，此模型旨在提供給YouTuber在影片發佈之前事先測試自己的影片標題是否足夠吸睛、是否足夠具有競爭力，避免自己辛苦產出的影片卻因為封面和標題不夠吸引人而導致點閱數低下，YouTuber可預先準備數個影片標題，由模型來預測何項影片標題最為吸睛，預期點閱數最高，來確保自己的影片標題能夠具有足夠競爭力！


## 使用方式
### Bi-LSTM模型訓練
使用者可自行爬取特定頻道類型的YouTuber作為輸入Bi-LSTM模型的訓練資料，抑或使用 _get_top50_YouTube.py 檔案取得台灣地區總點閱數前50名的YouTuber作為訓練資料。
```
# 使用 Youtube_Crawler.py 檔案爬取特定頻道的影片資訊
$ python Youtube_Crawler.py  

# 將爬取到的資料透過 model_F.py 檔案來作模型訓練
$ python model_F.py
```
![image](https://user-images.githubusercontent.com/111637364/187491703-e687ca21-2fa6-4679-8d1d-18260481f12c.png)
![image](https://user-images.githubusercontent.com/111637364/187491716-1692db3a-0110-4d51-892c-35445b7c1038.png)


### 自然語言處理(斷詞+詞向量)
```
# 使用 _Word2Vec_visualization_3D.py 檔案，將影片標題作Word2Vec詞向量處理並視覺化
$ python _Word2Vec_visualization_3D.py 
```
![word2Vec_gif](https://user-images.githubusercontent.com/111637364/186734029-2d3c3d5e-e059-4a75-82d3-3ac3eb5242c7.gif)

```
# 使用 _Doc2Vec_visualization.py 檔案，將影片標題作Doc2Vec詞向量處理並視覺化
$ python _Doc2Vec_visualization.py 
```
![doc2Vec](https://user-images.githubusercontent.com/111637364/186747996-65ea93cc-5dc1-452b-8874-51aec3158ffe.jpg)


### 模型預測
```
# 使用 github_predict.py 檔案，輸入特定影片ID作點閱率結果預測
$ python github_predict.py
```
![image](https://user-images.githubusercontent.com/111637364/187491916-8c2fb094-fa9c-4e23-99a9-6980a4db11b1.png)

