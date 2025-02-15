## 1. 推薦閱讀
- [程式與網頁開發者必備技能！Git 和 GitHub 零基礎快速上手，輕鬆掌握版本控制的要訣！](https://www.youtube.com/watch?v=FKXRiAiQFiY&t=634s)

## 2. 還沒使用 git 前：以資料夾註記版控

-   在初學程式階段，還不會使用 Git 時，如果練習到一個階段，想避免之後的練習改壞這包程式，十之八九會這麼操作
    -   先把放專案程式的資料夾，整包複製一份。
    -   更改複製出來的資料夾名稱。
    -   安心的修改原本的程式。

![upgit_20250214_1739514678.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739514678.png)

-   優點：
    -   相對簡單
    -   適合在改計畫、PAPER 等少少文件修改
-   缺點：
    -   占用硬碟空間
    -   不易追溯歷史
    -   容易誤刪版本
    -   不易協作

## 3. 集中式版本控制 (Centralized Version Control, CVCS) vs. 分散式版本控制 (Distributed Version Control, DVCS)

### 3.1. 集中式版本控制 (Centralized Version Control, CVCS)

-   集中式版本控制系統 (CVCS) 使用單一的中央伺服器 來儲存所有版本的檔案。
-   開發者的電腦上不會儲存完整的專案歷史，而是從中央伺服器下載最新版本，進行修改後再提交回伺服器。

![upgit_20250213_1739436840.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739436840.png)

### 3.2. 分散式版本控制 (Distributed Version Control, DVCS) => git

-   分散式版本控制系統 (DVCS) 不依賴中央伺服器，每個開發者的電腦上都有完整的版本庫 (Repository)。
-   可以在本地進行提交 (commit)、回溯 (checkout) 等操作，並在需要時與遠端倉庫同步 (push/pull)。

![upgit_20250213_1739437120.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739437120.png)

## 4. git

![upgit_20250214_1739514804.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739514804.png)

-   將【儲存的資訊】以及【對檔案隨時間的變更】視為檔案並儲存。
    ![upgit_20250213_1739437259.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739437259.png)

### 4.1. git 的三種狀態：

-   已修改 (Modified)
    -   檔案已經被更改，但還沒有加入版本控制系統中。
    -   這些變更仍然存在於工作目錄 (Working Directory) 中。
-   已暫存 (Staged)
    -   已修改的檔案被標記為下一次提交 (commit) 的候選對象。
    -   這些變更已經加入 暫存區 (Staging Area)，但尚未正式提交到 Git 倉庫。
-   已提交 (Committed)
    -   變更已經被永久存入 Git 倉庫 (Repository) 中，並保存在本地端的 Git 目錄。

### 4.2. 可以下載的套件

![upgit_20250214_1739515016.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739515016.png)

## 5. 安裝 git

## 6. 建立 Repository
![upgit_20250213_1739438782.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739438782.png)

### 6.1. Lab：[github 建立 Repository，clone 到 PC 使用](./Lab/github_to_PC.md)
### 6.2. Lab：[PC_to_github](./Lab/PC_to_github.md)

### 6.3. 安裝好後設定使用者身分
```
git config --global user.name "Wei-Cheng Chen"
git config --global user.email N96144250@gs.ncku.edu.tw
```

### 6.4. 對參數取得說明

```
git help 需要查詢的指令
eg：git help config
```
### 6.5. Lab：[本地新增 test02.txt，並上傳到 github](./Lab/add_txt_to_github)

## 7. Commit Message 之規範

-   參考來源：[Git Commit Message 這樣寫會更好，替專案引入規範與範例 - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10228738)
- 不能只把 Git 當作程式碼的 FTP，這樣太可惜了，要把 Git 當作歷史查閱的工具才拿發揮 Git 的功能。
- 好的 Commit Message：如何在一年後的讓維護人員進入狀況，
- 不良的 Commit Message：如何在一個月內讓維護人員找不出異動脈絡。
- commit 要全選刪除的語法：ggdG
```
# Commit Message語法閨法
<type> <subject>

<body>

<footer>
```

-   type(沒有硬性規定)
    -   feat (feature)：新增/修改功能
    -   fix：修 bug
    -   docs：文件
    -   refactor：重構
    -   test：增加測試
    -   revert：撤銷回覆先前的 commit 例如
-   subject：代表此 commit 的簡短描述，不要超過 50 個字元
-   body：對本次 Commit 的詳細描述。可以分成多行，每一行不要超過 72 個字元。
-   footer：填寫任務編號（如果有的話）

### 7.1. 範例 01：fix

```
fix: 自訂表單新增/編輯頁面，修正離開頁面提醒邏輯

問題：
1.原程式碼進入新增頁面後，沒做任何動作之下，離開頁面會跳提醒
2.原程式碼從新增/編輯頁面回到上一頁後（表單列表頁面），離開頁面會跳提醒

原因：
1.新增頁面時，頁面自動建立空白題組會調用 sort_item，造成初始化 unload 事件處理器。
2.回到上一頁後，就不需要監聽 unload 事件，應該把 unload 事件取消。

調整項目：
1.初始化 unload 事件處理器：排除新增表單時，頁面自動建立空白題組調用 sort_item 的情境
2.回到上一頁後，復原表單被異動狀態且清除 unload 事件處理器

issue #1335
```

### 7.2. 範例 02：fix

```
fix: 意見反應，信件看不到圖片問題

問題：
1.客戶反應：意見反應的信件都看不到圖片。

原因：
1.目前程式碼都會要求先登入後才可查看使用者上傳的檔案， 造成在信件上會看不見圖片的問題。

調整項目：
1.File.php，經討論後，開放讓意見反應頁面上傳的檔案，不用登入就可以查看/下載。

issue #1229
```

### 7.3. 範例 03：feat

```
feat: message 信件通知功能

因應新需求做調整：
1.通知和 message 都要寄發每日信件，
2.通知和 message 都用放在同一封信裡面就好， 不然信件太多可能也不會有人想去看。

調整項目：
2. mail_template.php，新增 message 區塊。
3. Send_today_notify_mail.php，新增 取得每日 Message 邏輯。 3
4. Message_model_api.php，新增 $where 參數，以便取得每日訊息。
5. Message_api.php、Message_group_user_model_api.php，新增 **取得訊息使用者** 邏輯，以便撈取每日訊息。

issue #1229
```



## 8. 查看提交歷史：git log

-   基本語法：git log
-   比較會用的方式：git log --oneline
    ![upgit_20250213_1739450058.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739450058.png)
-   PC 端：
    -   HEAD -> main：代表當前位置
-   github 端：
    -   origin/main：遠端倉庫 (remote repository)位置
    -   origin/HEAD：
        -   預設分支指標，是一個特殊的指標，通常指向遠端倉庫的預設分支 (default branch)
        -   遠端倉庫 (`origin`) 預設應該使用 `main` 作為主要分支。
        -   當你 `git clone` 時，Git 會自動讓你進入 `main` 分支。

-   所以，如果我這時候在做一次提交
    -   git add.
    -   git commit -m "2025.02.13"
-   查看當下紀錄：git log --oneline
    ![upgit_20250213_1739450312.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739450312.png)
-   git reflog：列出所有 HEAD 的變更記錄，包括未來的提交
## 9. git pull

-   直接在遠端修改 README
-   在 PC 端 git pull
### 9.1. Lab：在github上修改README，在PC端pull
- 在github上修改README：增加文字【這是直接在github上新增的文字】
- 在PC上git pull
- 在PC上對README新增文字【這是直接在PC上新增的文字】
## 10. `.gitignore`
### 10.1. Lab：建立檔案key.txt，並利用gitignore忽略它
-   完整檔案名稱：
```
.env # 環境設定檔
.config # 配置檔案
.DS_Store # macOS Finder 產生的檔案
app.log # 名叫 app 的 log 檔案
```

-   直接定義要忽略的副檔名

```
*.log           # 忽略所有以 .log 結尾的檔案
*.tmp           # 忽略所有以 .tmp 結尾的檔案
```

-   忽略任何叫某個名字的檔案(不管副檔名)

```
hello.* # 忽略任何叫 hello 的檔案，包含 hello.txt、hello.java ...
```

-   忽略所有以某個字樣開頭的資料

```
image* # 忽略所有以 image 開頭命名的資料(包含檔案與目錄)
```

-   忽略目錄底下的 「所有內容」

```
.vscode/        # Visual Studio Code 設定檔
.idea/          # IntelliJ IDEA 設定檔
node_modules/   # Node.js 的依賴模組
build/          # 編譯或建置的結果目錄
dist/           # 發布版程式碼的目錄
```

## 11. 從 Git 版本庫中移除檔案：git rm

-   還記得 git 的用處嗎：將【儲存的資訊】以及【對檔案隨時間的變更】視為檔案並儲存。
-   他儲存的是檔案邊更，而非檔案本身。因此，刪除檔案對 git 來說，也是一種【要記錄的過程】
-   因此，如果要【讓檔案直接移除 git 紀錄】，就需要 git rm
-   示範：單純右鍵刪除檔案，查看 git status

### 11.1. Lab：將檔案key.txt commit ，在利用gitignore跟rm清除她
- 嘗試將gitignore的文字註解調，讓私人檔案做紀錄
- 在利用gitignore跟rm清除她削掉PC紀錄

```
git rm -r --cached .
git add .
git commit -m "移除已被忽略的檔案"
git push
```

-   如果這份檔案已經(push 到 GitHub/GitLab，你需要使用 git filter-branch。
-   注意：這會改變 Git 歷史，可能會影響其他開發者，因此建議在小型團隊或個人專案中使用。

```
git filter-branch --force --index-filter "git rm --cached --ignore-unmatch <要清除紀錄的機密檔案>" --prune-empty --tag-name-filter cat -- --all

git push origin --force --all
```


> 到這邊休息一下



## 12. tag

-   `git tag` 用於 標記 (tag) Git 的特定版本，通常用來標記軟體的發佈版本，例如 `v1.0.0`、`v2.0.1`
-   標記特定版本（例如 `v1.0.0`）。
-   快速回到某個穩定版本（可以隨時 `checkout` 回標記）。

![upgit_20250214_1739530569.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739530569.png)



### 12.1. 創建 `tag`

-   創建【沒有描述的標籤】：git tag v1.0.0
-   創建【有描述的標籤】：git tag -a v2.0.0 -m "有描述的標籤 2.0.0"
-   為前面的 commit 補標籤：git tag v0.9.0 -m "有描述的標籤 0.9.0"

### 12.2. 查看 tag
-   git tag
### 12.3. 將 tag 推到雲端
-   預設標籤是不會被發送到雲端的，如果要將 tag 發送到雲端：git push --tags
-   可以將當前的工作區變更「暫存」起來，然後恢復乾淨的工作區，之後再取回這些變更。










## 13. 版本切換
- 返回之前 commit的時機
	-   只是想回去看看
	-   回前面看看，並加給行註記(跟現階段完全無關)
	-   現在做爛了，要回到某個時間點，然後從那個時間點當作 main 繼續下去 => git reset

### 13.1. 將檔案從站存區移開
- 將檔案從站存區移開：git reset

### 13.2. git checkout 和 Detached HEAD
-   在【回到過去某一個紀錄點】時，Git 會進入  **Detached HEAD**  狀
    -   **HEAD**（當前工作目錄的指向）不再指向某個分支，而是直接指向某個特定的提交
    -   你在這個狀態下所做的任何更改都不會影響任何分支，除非你明確地創建一個新分支來保存這些更改。

### 13.3. Lab：只是想回去看看
- 查看前面的：這時候會呈現detached HEAD狀態
	- git checkout hash值
	- git checkout HEAD~1
- 返回：main分支在最前面 => 
	- git checkout main
	- git switch main


### 13.4. Lab：在 Detached HEAD 狀態下做了更改，並希望保存這些更改
```
git log --oneline # 查看要到哪一個commit
git checkout HEAD~1或hash值

##### 建立一個新分支來保存變更 #####
git checkout temp-branch
git switch temp-branch

##### 將變更加入暫存區 ##### 
git add .
git commit -m "Temporary changes in Detached HEAD"

##### 切換回 main 或其他分支 #####
git switch main # 切回 main 分支
```
### 13.5. 重置當前分支(HEAD)的狀態：git reset
-   可以幫助你撤銷提交、取消暫存文件，甚至恢復到某個歷史提交的狀態。
-   會根據選項決定如何處理工作目錄和暫存區。
    -   --soft：只重置  **HEAD**  指針，不影響暫存區和工作目錄。
    -   --mixed（預設模式）：重置  HEAD  指針和暫存區，但不影響工作目錄。
        -   這個情況就很像「已經執行  `git add .`，但還沒執行  `git commit` 」 的時間點了。
    -   --hard：重置  HEAD 指針、暫存區和工作目錄。 => 絕對不要用他
-   如果你剛剛提交了一個提交，但發現有問題，可以使用  `git reset`  撤銷該提交。

```
git reset HEAD~1 # 撤銷最近的一個提交
git reset HEAD~2 # 撤銷最近的兩個提交
```

-   如果你想將當前分支恢復到某個歷史提交的狀態，可以使用  `git reset`

```
git reset <commit-hash>
```

### 13.6. git revert

-   `git revert` 是 Git 中用來撤銷某個 commit 的指令，
-   但與 `git reset` 不同，`git revert` 不會刪除提交歷史，而是 產生一個新的 commit 來撤銷變更。

```
git log --oneline
git revert a1b2c3d # 返回某一個commit
# Git 會開啟文字編輯器，讓你輸入 commit 訊息
# 撤銷該 commit，並會建立一個新的 commit
```


## 14. Git flow
-   參考來源：[Git 上的三種工作流程. 此篇介紹 Git 的三種工作流程，建議對 Git 有簡單了解再閱讀此篇。若要找 git… | by Bowen | 儲思盆 | Pensieve | Medium](https://medium.com/i-think-so-i-live/git%E4%B8%8A%E7%9A%84%E4%B8%89%E7%A8%AE%E5%B7%A5%E4%BD%9C%E6%B5%81%E7%A8%8B-10f4f915167e)
    ![upgit_20250214_1739516163.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739516163.png)
-   Master(main)：最終發行版
-   Develop：是所有開發的基礎分支
    -   當要新增功能時，會新增 feature 分支，開發完後再合併回 Develop。
-   Feature：要開發新功能
-   Release：當認為 Develop 分支夠成熟了，就可以把 Develop 分支合併到 Release 分支
    -   進行算是上線前的最後測試
-   Hotfix：當 master 有 Bug 時，會緊急產生 hotfix 的分支修復，修完後再合併回 master




## 15. branch

-   Git 的 分支 (branch) 是用來管理不同版本的變更，讓你可以同時開發多個功能，而不影響主線程 (`main` 或 `master`)。

![upgit_20250213_1739453196.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739453196.png)

### 15.1. 查看 branch

-   查看本地所有分支：git branch
-   查看雲端所有分支：git branch -r
-   查看 PC+雲端所有分支：git branch -a
-   示範：在 github 上新增分支

### 15.2. 建立分支

-   建立分支：git branch <新分支名稱>(eg：git branch feature-login)
    -   這會創建 `feature-login` 分支，但不會切換過去

![upgit_20250214_1739506274.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739506274.png)

-   git 如何知道你目前處在哪一支分支=>HEAD
    ![upgit_20250214_1739506309.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739506309.png)

### 15.3. 切換分支

-   切換到新分支：git checkout <分支名稱>(eg：git checkout testing)
-   改變 HEAD 指標，指向 hceckout 的那個分支
    ![upgit_20250214_1739506472.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739506472.png)

-   這時候去 add 跟 commit
    ![upgit_20250214_1739506500.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739506500.png)

-   如果再切回 master
    ![upgit_20250214_1739506536.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739506536.png)

-   這時候，我們再從 main(master)去 commit
    ![upgit_20250214_1739506584.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739506584.png)

### 15.4. 其他事項

-   推送新分支到遠端：git push -u origin <分支名稱>(eg：git push -u feature-login)
-   刪除分支：git branch -d <分支名稱>

### 15.5. 分支合併：merge

#### 15.5.1. Fast-Forward Merge：

![upgit_20250214_1739507213.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739507213.png)

-   是 Git **最簡單的合併方式**
-   只發生在 **目標分支（main）沒有新的提交** 的情況下

```
git checkout main # 切換到 main 分支
git pull # 確保 main 分支是最新的
git merge --ff-only feature-login # 嘗試 Fast-Forward Merge
```

#### 15.5.2. 3-way merge(一般合併)

![upgit_20250214_1739507498.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739507498.png)

-   當兩個分支有分叉時，Git 會創建一個新的合併提交，結合兩個分支的更改。

```
git checkout main # 切換到 main 分支
git pull # 確保 main 分支是最新的
git merge feature-login 合併 feature-login
```

-   示範：一般 merge，處理衝突

### 15.6. 分支合併：merge

-   Git rebase 是 Git 中用於整合分支的另一種方式
-   與  `git merge`  不同，它通過重新應用提交來保持線性歷史。
    -   Merge 會創建一個合併提交，保留分支結構。
    -   Rebase 會重新應用提交，使歷史更整潔。
-   Rebase 會改寫提交歷史，如果已經將分支推送到遠程倉庫，強制推送（`git push --force`）可能會影響其他開發者。
-   將當前分支(testing) rebase 到目標分支(main)

```
git checkout testing # 切換到要 rebase 的分支
git rebase main # 執行 rebase

##### 如果發生衝突 #####
# 手動解決衝突
git add .
git rebase --continue # 繼續 rebase
```
## 16. Git Stash (暫存變更)

-   當你在某個分支上進行開發，突然需要切換到另一個分支，但不想 commit 未完成的變更時，可以使用 `git stash` 暫存變更。

### 16.1. 暫存當前變更

-   git stash：未追蹤 (untracked) 或忽略 (ignored) 的檔案不會被 stash

### 16.2. 查看 Stash 列表

-   git stash list：

### 16.3. 取回暫存的變更

-   git stash apply：取回最近的 stash 但不刪除 stash
-   git stash apply stash@{2}：取回特定的 stash，例如 stash@{2}
-   git stash pop（取回並刪除 stash）

### 16.4. 刪除 Stash

-   git stash drop stash@{0}：刪除 `stash@{0}`，但不影響其他 stash。
-   git stash clear：清空所有 stash



