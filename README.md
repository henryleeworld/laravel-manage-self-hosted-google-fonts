# Laravel 10 管理本地端 Google 字型

引入 spatie 的 laravel-google-fonts 套件來管理本地端 Google 字型。Google 字型網站收錄大量開放原始碼字型專案，讓使用者透過目錄篩選的方式找到自己需要的字型資源，但依賴 Google 字型是有代價的，通過在外部網域管理字體，瀏覽器需要執行額外的網域名稱系統查找。這會減慢初始化頁面加載速度。此外，您將訪問者引導至 Google 資源，注重隱私的用戶可能不喜歡這種做法。

## 使用方式
- 把整個專案複製一份到你的電腦裡，這裡指的「內容」不是只有檔案，而是指所有整個專案的歷史紀錄、分支、標籤等內容都會複製一份下來。
```sh
$ git clone
```
- 將 __.env.example__ 檔案重新命名成 __.env__，如果應用程式金鑰沒有被設定的話，你的使用者 sessions 和其他加密的資料都是不安全的！
- 當你的專案中已經有 composer.lock，可以直接執行指令以讓 Composer 安裝 composer.lock 中指定的套件及版本。
```sh
$ composer install
```
- 產生 Laravel 要使用的一組 32 字元長度的隨機字串 APP_KEY 並存在 .env 內。
```sh
$ php artisan key:generate
```
- 執行 __Artisan__ 指令的 __storage:link__ 來建立連結符號，讓公用可存取的檔案維持在一個目錄中。
```sh
$ php artisan storage:link
```
- 在瀏覽器中輸入已定義的路由 URL 來訪問，例如：http://127.0.0.1:8000。
- 你可以經由 `/` 來瀏覽歡迎頁面。

----

## 畫面截圖
![](https://i.imgur.com/AC9mZ7p.png)
> 當第一次請求字型時，這個套件將抓取 CSS，從 Google 的伺服器取得資源，將它們儲存在本地端，並行內呈現 CSS 