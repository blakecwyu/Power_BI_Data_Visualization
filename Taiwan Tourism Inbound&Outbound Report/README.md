[中文版本](README.md) | [English](README_EN.md)  
  
# 台灣觀光出入境分析儀表板   
  
## 概述  
此Power BI儀表板分析2019至2025年台灣出入境旅客趨勢，提供年份及月份的篩選功能，視覺化呈現季節性、國家地區分布、入境旅客目的、以及各縣市飯店旅館平均住房率，同時也比較近年與疫情前數據，顯示出入境人數的巨大差異。  

## 資料來源  
- 來源:  
  - 交通部觀光署觀光統計資料庫  
    1. [旅館業(一般旅館)營運報表](https://admin.taiwan.net.tw/businessinfo/FilePage?a=9711)  
    2. [來臺旅客_按性別及來臺目的分析](https://stat.taiwan.net.tw/statistics/month/inbound/gender/purpose)  
    3. [中華民國國民出國_按目的地分析](https://stat.taiwan.net.tw/statistics/month/outbound/destination)  
- 涵蓋範圍:  
  - 2019–2025年每月份  
- 備註:  
  - 另外有一個手動建置的表格，列出入境與出境表格的國家地區。其中部分國家地區名稱在入境與出境資料中不完全相同，比方說入境資料香港與澳門合併計算，但出境資料則為分開。   
  - 旅客入境目的與縣市別名表於Power BI內手動建立，用於中英文名詞對照。  
  - 日期時間表格建立在Power BI裡。  
  - 使用Power BI裡的Power Query進行資料清洗與轉換。  

## 儀表板內容  
![Preview Images](preview_images/Preview_Taiwan_Tourism_Inbound&Outbound_Report_01.png)  
- 使用Power Query自動清理與轉換新資料。  
- 動態年份及月份按鈕選項。  
- 出入境數據皆與前一月份、前一年同月份、疫情前同月份(2019年)比較。
- 可選擇的當月主要出入境國家地區。  
- 旅客入境目的排名。  
- 各年份入境人數趨勢，提供疫情前後年份比較。  
- 折線直條組合圖顯示出入境間明顯人數差異及變化。  
- 形狀地圖顯示各縣市飯店旅館平均住房率。  

## 展示影片  
![Dashboard Demo](demo_video/Demo_Taiwan_Tourism_Inbound&Outbound_Report.gif)  
  
## 專案架構  
Taiwan Tourism Inbound&Outbound Report/  
├── data/  
│   └── Hotels by CountyCity/  
│   └── Inbound/  
│   └── Outbound/  
├── demo_video/  
│   └── Demo_Taiwan Tourism Inbound&Outbound Report.gif  
├── pbip/  
│   └── Taiwan Tourism Inbound&Outbound Report.pbip  
├── preview_images/  
│   └── Preview_Taiwan_Tourism_Inbound&Outbound_Report_01.png  
│   └── Preview_Taiwan_Tourism_Inbound&Outbound_Report_02.png  
│   └── Preview_Taiwan_Tourism_Inbound&Outbound_Report_03.png   
└── README.md  
  
## 如何調整資料夾路徑  
此儀錶板使用Power Query自動從資料夾匯入資料，若您使用不同電腦或資料存放於不同路徑，請依以下步驟調整資料夾路徑：  
- 在Power BI點選`Transform Data`。  
- 於各資料集上按右鍵，選擇`Advanced Editor`。  
- 在`Folder.Files("...")`函式中更新資料夾路徑(通常位於程式碼第一行)。  
- 針對所有資料集(Inbound、Outbound、Inbound_gender、Inbound_purpose、Hotels by CountyCity)重複此步驟。  
- 套用變更並重新整理資料。  
此設定可確保儀錶板於不同電腦上正確載入與處理新資料。  

## 限制  
- 此資料通常在月份結束3個月後才會公布，可能無法顯示即時的事件或趨勢。  
- 因Power BI本身的限制，在尚無資料的未來月份，月份選擇按鈕無法停用，僅以條件式底色讓其看似無法選取，但實際上仍可點選。  
- 出境資料的國家地區為旅客之出境目的地，可能並非旅客之國籍或最終目的地。
- 入境與出境資料的國家地區名稱並不完全相同。  
- 國家地區、入境旅客目的、縣市別名表為手動建立，未來如來源資料內容有所變更，需要手動更新這些別名表。  
- 地圖資料(TopoJSON)以中文地名為判斷依據，限制了使用上的彈性。  

## Credits  
- 資料來源: 中華民國交通部觀光署
- 地圖資料(TopoJSON): 台灣地圖資料使用由[jason2506](https://github.com/jason2506/Taiwan.TopoJSON)依據台灣縣市界線圖資製作之地圖 

## 權限  
此儀錶板使用政府公開資料，供非商業及學術使用。  
所有Power BI文件、Power Query資料轉換之程式碼(M code)、以及視覺化呈現等內容皆以MIT授權模式。  
聲明: 此儀錶板為個人學習與技術展示使用，與任何政府部門或圖資(TopoJSON)提供者無關。  
