# Countries of the World | 世界各國介紹網站

![website screenshot](https://github.com/chengyuu/chengyuu.github.io/blob/master/img/countries%20website.png)

### **[Website Link](https://chengyuu.github.io/Countries-Of-The-World/)**

## 資源
* 網站主要使用 `Vue.js v3` 架設而成。
* 資料來源：以 `Axios` 套件載入 **[RestFul API](https://restcountries.eu/rest/v2/all)**。
* CSS 引入 `Bootstrap 5` 的樣式。
* 字體使用 [Google Fonts](https://fonts.google.com/)、Icons 使用 [Font Awesome](https://fontawesome.com/)。
## 說明
* **API 資料的讀取、處理及應用。**
* **Nav**：導覽列以 `computed`及 `Array.filter()` 篩選資料中的 region，預設顯示全部。
* **Header**：頁首點擊後會顯示現在時間，並以每秒更新時間及畫面。
* **Main**：主要內容分為左右兩側，左側顯示國家列表，右側顯示排名。
  * **左上**：顯示篩選後筆數和頁數，另外搜尋輸入框以 `v-model` 雙向綁定輸入內容，再以正規表達式 `RegExp` 比對資料的 name 並回傳符合項目。
  * **左中**：以 `v-for` 對資料陣列進行渲染，當某筆資料被點擊後，則利用 `v-show` 切換至詳細頁面；詳細頁面以表格呈現資料中的內容，並以 <iframe> 標籤嵌入 Google Map 該國家的所在位置。
  * **左下**：因每頁顯示上限 20 筆的資料，分頁按鈕會先判斷目前所在的頁數，再切換顯示資料的索引。
  * **右側**：前兩項排名為最多人口數和土地面積最大的國家，是以 `Array.sort()` 排序資料中的 population 和 area；後兩項排名為最多國家使用的語言和貨幣，則是先以 `Array.reduce()` 統計資料中不同 languages 和 currencies 出現的次數後再進行排序。
