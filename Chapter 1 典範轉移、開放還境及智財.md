# Chapter 1: 典範轉移、開放還境及智財

## 典範轉移與開放環境

### ICT典範轉移(Paradigm Shift)：

1.   積體電路：降低生產成本
2.   視窗系統：脫離command line
3.   物件導向：降低軟體維護成本
4.   WEB & Internet：讓使用者與網路連結
5.   物聯網：讓實體物件與網路連結
6.   大數據、人工智慧：降低管理成本、預測未來

### Web1.0 vs. Web2.0：

1.   Web1.0：

     運作模式：主從式(Client/Server)，溝通，封閉專用

     使用：讀取、固定功能、靜態社群

     內容：集中式、分類、網站、整合內容

     軟體：有生命週期

     經營：封閉式

2.   Web2.0：

     運作模式：同儕式(P2P)，溝通，開放分享、參與、貢獻、社交

     使用：創作、溝通、合作、動態社群

     內容：分散式、動態內容分享、聚合、新價值
     
     軟體：永遠的beta服務、open source、混搭產生新內容
     
     經營：社群經營、長尾效應

### 開放自由與合作共創：

1.   自由軟體(Free Software)：使用、研究、散步、改良的自由

     >   自由不等同於免費

2.   開放軟體(Open Source Software)：

     1.   可重新發佈
     2.   公開原始碼
     3.   衍生寫作
     4.   保障作者完整的原始碼
     5.   不歧視
     6.   散佈授權條款
          1.   不得專屬於特定產品
          2.   不得限制其他軟體
          3.   必須技術中立

3.   Copyleft：

     1.   版權(Copyright)：合理使用之外的利用須取得著作權人同意
     2.   Copyleft要求使用者改作後的衍生產品須以同等授權方式釋出
     3.   利用著作權法

4.   GPL(General Public License)授權條款：

     1.   以任何目的執行此程式的自由
     2.   再發行複製的自由
     3.   改進此程式並公布改進的自由

5.   開源硬體：

     1.   與開源軟體相同設計方式的硬體
     2.   包括邏輯設計、電路圖、電路板佈局、材料清單等
     3.   與軟體關係密切

6.   開放資料(Open Data)：

     1.   任何人皆可自由出版及使用
     2.   為達到資料互用/互運性(Interoperability)，須滿足：
          1.   可用與可取得性
          2.   重複使用與散佈
          3.   平等普及的參與

### 共享經濟(Sharing Econimy)：

1.   特點：資源「使用權」和「擁有權」拆分
2.   問題：法律、公平性

## 網際網路軟體開發

1.    Socket：
     1.   送收兩端分別開啟，單向通道送出或接收
     2.   平行動作需撰寫Multi-thread程式共用資源，debug挑戰高
2.   RPC(Remote Procedure Call)：
     1.   類似呼叫本機程式方式呼叫遠端程式
     2.   由Compiler轉換成Socket運作
     3.   Java RMI(Remote Method Invocation)
3.   Web-based(HTTP Request-Response)：
     1.   應用層協定(Request-Response)
     2.   簡單、非同步運作
     3.   前端瀏覽器$\rArr$後端伺服器
     4.   裝置/手機$\rArr$快取邊緣閘道$\rArr$伺服器
     5.   Web Services：伺服器$\lrArr$伺服器
     6.   RESTful API

## Web發展過程

1.   建置http的protocal協定$\rArr$html表示法

    >   利用HTTP和HTML可以從瀏覽器看到研究資料

2.   瀏覽器新增三種機制：

    1.   Javascript：Java簡化版
    2.   SSL加密(更新後為TLS)
    3.   Cookie資料暫存

3.   伺服器端(後端)透過CGI讓作業系統和應用程式溝通

    1.   CGI透過作業系統機制，安全及處理較低階

    2.   各種不同後端開發語言架構被提出

         >   ASP.NET, PHP, JSP, Django, Ruby on Rails, Node.js

4.   Web成為應用平台

5.   HTML更新到1.1後就停止更新

6.   XML被提出

    1.   各種廠商都會在HML裡做變化，利用HTML標籤式去定義不同領域的內容
    2.   W3C定義XML規範及標準
    3.   不只能用在瀏覽器規範，可以使用在所有資料中(隱藏在應用程式中)

7. REST(RESTful API)被提出，利用HTTP GET/POST來做伺服器內容的存取

    >   方便開發者取得後端資料$\implies$ 應用開發標準化、門檻降低

8. 開發行動裝置WAP(Wireless Application Protocal)

9. 手機和後端間溝通也有困難$\implies$ Push Proxy Gateway

    >   現今手機已不需WAP架構，但觀念仍影響至今

10. Web2.0 概念出現：分享及貢獻