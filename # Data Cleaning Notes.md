# Data Cleaning Notes

記錄一些做資料分析之前，清理資料的一些方法

可先針對整體資料檢視一下個特徵所含有的Missing Value的數量
針對Missing Value 數量大的欄位先處理
逐步處理至Missing Value數量小的欄位

根據不同類型的資料(numerical and string)可以使用不同的處理方式

可參考的處理方式筆記如下：

1. 檢視欄位特徵的必要性  
   先評估欄位資料的完整性，若欄位內Null Data的占比很大  
   則可以評估看看此欄位的必要性，若對整個系統來說其相關性不大  
   則可以考慮將此欄位去除  

2. ​針對Missing Data補值  
  可考慮補值的選項有：
  + 補一個常數，如0、其他常數值...
  + 補Mean值
  + 補Mode
  + 補Median
  + 補與上一筆資料相同的數值
  + 補與下一筆資料相同的數值
  + 將兩筆資料中間的Missing Value 取線性分割
  + 若為文字類的，可補Others​
  
3. 用計算的方式補Null Data  
  若特徵內的Missing Value可被計算，則可以依照其對應的計算方式補值  
  
4. 參考其他欄位來補Null Data  
  若Missing Value內的資料可由參考其他欄位獲取資料，則用參照的方式來補值  
  
5. ​刪除含有Null Data的資料  
  但在資料量較小的情境下較不適用  
  適合用於較不完整的資料上  
  
6. ​檢視Outliar 的狀況  
  可針對Numerical 的資料去檢視每項特徵的分布狀況  
  (看個別的Historgram或兩兩取Scatter Plot)  
  找出Outliar 的資料並檢視其資料的必要性  
  若對整體而言較不影響，可考慮去除Outliar  
  
7. 若針對分類較多的String 類的資料  
  可將多項分類整併起來，減少分類的項目  

參考資料：
Google Cloud Dataprep Documentation	https://cloud.google.com/dataprep/docs/
