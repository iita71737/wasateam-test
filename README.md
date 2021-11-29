# wasateam-test

## Project setup
```
yarn install
```
### Compiles and hot-reloads for development
```
yarn serve
```
### Compiles and minifies for production
```
yarn build
```
### Firebase Deploy Host
[firebase host](https://test-deploy-cbeaf.web.app)

### 前測需求描述
```
1. 用Vue Cli或Nuxt 完成以下功能  
2. 以scss撰寫內容樣式
3. 應用component功能
4. 應用computed功能
5. 製作 輸入類型 text, radio, select 、同一component切換prop來改變對應的輸入類型，並可套用v-model
6. 可切換頁面
7. 設定頁面title, description
8. 設定Global參數、讓頁面的顏色、主題會隨著更換
9. 串接一組列表資料api [https://mocki.io/fake-json-api](https://mocki.io/fake-json-api)
10. 程式架構做到最大的沿用性、維護性，並於Readme說明你的想法
11. 使用Firebase Hosting，提供連結給我們進行瀏覽
12. 提供Github程式碼
```

### 前測作答想法
```
#1.我是以vue-cli產生專案，且專案為vue2版本，因為我對於nuxt不熟悉，
目前只知道是協助SPA應用程式包裝成SSR，以利解決SEO的框架套件。

#2.我依照需求，將 輸入類型 作為一個可重複利用的component,
透過父組件傳遞的props來改變子組件要渲染的 輸入類型

#3.我雖然在scss檔設定了不同的data-theme，對應不同主題顏色，
但自認感覺在vue組件去操作DOM(document.documentElement.setAttribute)這種方式好像不是很理想？
雖然畫面應該有改變，但感覺好像有更好的方式去改變。

#4.因為第一次用firebase hosting,所以僅只於按照網路上的資料，
在firebase創建專案與部署空間後，
透過npm run build打包成靜態檔案，
透過firebase deploy直接部署。
```


