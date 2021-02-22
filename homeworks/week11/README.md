# 作業

## hw1：完成並加強留言板

第九週的作業只做到「利用 Session 實作登入機制」，而這一週要把後續的影片都看完（看到：「真正的實戰：留言板 - 再次修正問題篇」結束），並且把留言板的資安漏洞給修掉。

在修掉這些漏洞之前，你可以試試看入侵自己所寫的留言板，體驗一下當駭客的感覺。接著就是要把這些漏洞給修掉，包括：

1. 密碼沒有經過 hash
2. SQL Injection
3. XSS

把漏洞修補完以後，記得跟著 BE101 的課程（「真正的實戰：留言板 - 新增功能篇」與「真正的實戰：留言板 - 再次修正問題篇」），加上編輯、刪除留言的功能，也加上留言板的分頁，然後把權限的漏洞也修掉。

上面這些都在 BE101 裡面可以找到怎麼做以及範例程式碼，是屬於「跟著影片做」的部分，而 hw1 的另一個部分是「自己動手做」。

所以第二個任務就是，請幫這個留言板加上新功能：身份系統與管理後台。一共有三種不同的身份，每個人只會有一個身份，不會同時具有兩種以上的身份：

1. 管理員（可以新增留言，也可以編輯與刪除任意留言）
2. 一般使用者（可以新增留言，且編輯與刪除自己的留言）
3. 遭停權使用者（不能新增留言，但是可以編輯與刪除自己的留言）

你需要新增一個只有管理員進得去的後台頁面，在那邊可以看到留言板的所有使用者，而管理員可以調整使用者的身份。

<details>
  <summary>提示 #1</summary>
  可以在 users table 裡面新增一個叫做 role 的欄位
  裡面存放使用者的身份，資料格式可以自訂，例如說你可以存成數字
  1 代表一般使用者，0 代表被停權的使用者，2 代表 admin 之類的
  也可以用字串或是 ENUM 來存
</details>

### 延伸挑戰題

原本只有固定三種身份，而且每個身份的權限都是固定的。

現在請你加強這個身份系統，需要支援的東西有：

1. 新增以及編輯身份，例如說你可以新增一個身份叫做：「editor」，可以瀏覽以及編輯所有文章，但不能刪除
2. 更彈性的權限設計，你可以任意組合「新增文章」、「刪除自己的文章」、「刪除任意文章」、「編輯自己的文章」、「編輯任意文章」這些權限

舉例來說，管理員要可以更改遭停權使用者這個身份的權限，可以變成只能編輯文章不能刪除等等。

## hw2：陽春部落格

這是一個要靠你自己獨立完成的作業，我們只會提供設計稿還有範例。這個部落格需要有以下功能：

1. 要有登入機制，讓管理員能夠登入到管理後台
2. 身為一個管理員，要能夠新增文章
3. 身為一個管理員，要能夠編輯文章
4. 身為一個管理員，要能夠刪除文章
5. 身為一個管理員，新增文章時要有標題以及內文（如果有時間的話，可以去串 CKEditor）
6. 身為一個訪客，在首頁要能看到最新的五篇文章
7. 身為一個訪客，可以從導覽列點入：文章列表，並看到所有文章

要怎麼建置資料庫，要怎麼設計程式碼，這都是你可以自己決定的，那就加油囉！

設計稿：https://zpl.io/aXBw5PE 

（這一週作業的主軸是程式而不是切版，不一定要跟設計稿長得一模一樣，也可以自由發揮，如果時間不夠，請先忽略細節，先把功能做出來）

如果時間不夠的話，這邊有已經切好版的 html，你只需要幫它套上 PHP 即可：[範例線上看](https://lidemy.github.io/mentor-program-4th/examples/week11/hw2/static/index.html)，
檔案：[https://github.com/Lidemy/mentor-program-4th/tree/master/examples/week11/hw2/static](https://github.com/Lidemy/mentor-program-4th/tree/master/examples/week11/hw2/static)

（附註：在這週的範例裡面沒有實作 6 跟 7，而是直接在首頁上顯示所有文章）

### 延伸挑戰題

在設計稿裡面的一些東西其實是加分項目，不在作業的基本需求裡面，這些加分項目為：

1. 串接 CKEditor
2. 實作分類功能
3. 實作 view more 功能
4. 實作分頁機制
5. 新增關於我頁面
6. 支援 RWD

你不需要把這些功能全部做完，就算只做完一項也可以繳交挑戰題作業。再次強調，如果你有時間的話再來挑戰，沒有的話完成基本項目即可。

## hw3：簡答題

1. 請說明雜湊跟加密的差別在哪裡，為什麼密碼要雜湊過後才存入資料庫
2. `include`、`require`、`include_once`、`require_once` 的差別
3. 請說明 SQL Injection 的攻擊原理以及防範方法
4. 請說明 XSS 的攻擊原理以及防範方法
5. 請說明 CSRF 的攻擊原理以及防範方法

請將答案寫在 [hw3.md](hw3.md)。