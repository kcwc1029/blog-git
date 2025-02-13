## 1. 集中式版本控制 (Centralized Version Control, CVCS) vs. 分散式版本控制 (Distributed Version Control, DVCS)

### 1.1. 集中式版本控制 (Centralized Version Control, CVCS)

-   集中式版本控制系統 (CVCS) 使用 單一的中央伺服器 來儲存所有版本的檔案。
-   開發者在本地端只能存取最新版本，所有的版本記錄都存放在伺服器上。

![upgit_20250213_1739436840.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739436840.png)

### 1.2. 分散式版本控制 (Distributed Version Control, DVCS) => git

-   分散式版本控制系統 (DVCS) 不依賴中央伺服器，每個開發者的電腦上都有完整的版本庫 (Repository)。
-   可以在本地進行提交 (commit)、回溯 (checkout) 等操作，並在需要時與遠端倉庫同步 (push/pull)。
    ![upgit_20250213_1739437120.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739437120.png)

## 2. git

> [!NOTE] 將【儲存的資訊】以及【對檔案隨時間的變更】視為檔案並儲存。

![upgit_20250213_1739437259.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739437259.png)

### 2.1. git 的三種狀態：

![upgit_20250213_1739437519.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739437519.png)

-   已修改 (Modified)
    -   檔案已經被更改，但還沒有加入版本控制系統中。
    -   這些變更仍然存在於工作目錄 (Working Directory) 中。
-   已暫存 (Staged)
    -   已修改的檔案被標記為下一次提交 (commit) 的候選對象。
    -   這些變更已經加入 暫存區 (Staging Area)，但尚未正式提交到 Git 倉庫。
-   已提交 (Committed)
    -   變更已經被永久存入 Git 倉庫 (Repository) 中，並保存在本地端的 Git 目錄。

## 3. 安裝 git

-   從 github 新增目錄，再 clone 到本機

### 3.1. 安裝好後得初始設定

-   設定使用者身分

```
git config -- global user.name "John Doe"
git config -- global user.email johndoe@example.com
```

-   取得說明

```
git help 需要查詢的指令
eg：git help config
```

### 3.2. 在 github 上面設定私人或公開

### 3.3. Lab：本地新增 test01.txt，並上傳到 github

![upgit_20250213_1739438782.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739438782.png)

- 確認遠端倉庫：git remote -v
- 新增檔案 text.txt
- 查看狀態：git status
- 將變更加入暫存區 (Staging Area)：git add .
- 查看狀態：git status
- 將暫存區的變更存入 Git 倉庫：git commit -m "附加描述"
- 將 git 倉庫推到 github：git pull

## 4. Commit Message 之規範
- 參考來源：[Git Commit Message 這樣寫會更好，替專案引入規範與範例 - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10228738)
-   不能只把 Git 當作程式碼的 FTP，這樣太可惜了，要把 Git 當作歷史查閱的工具才拿發揮 Git 的功能。
-   「好的 Commit Message」如何在一年後的讓維護人員進入狀況，
-   「不良的 Commit Message」如何在一個月內讓維護人員找不出異動脈絡。
- commit 要全選刪除的語法：ggdG
```
<type> <subject>

<body>

<footer>
```
- type
	- feat (feature)：新增/修改功能
	- fix：修bug
	- docs：文件
	- refactor：重構
	- test：增加測試
	- revert：撤銷回覆先前的 commit 例如
- subject：代表此 commit 的簡短描述，不要超過 50 個字元
- body：對本次 Commit 的詳細描述。可以分成多行，每一行不要超過 72 個字元。
- footer：填寫任務編號（如果有的話）

### 4.1. 範例01：fix
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
### 4.2. 範例02：fix
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
### 4.3. 範例03：feat
```
feat: message 信件通知功能

因應新需求做調整： 
1.通知和 message 都要寄發每日信件， 
2.通知和 message 都用放在同一封信裡面就好， 不然信件太多可能也不會有人想去看。

調整項目： 
2. mail_template.php，新增 message 區塊。 
3. Send_today_notify_mail.php，新增 取得每日 Message 邏輯。 3
4. . Message_model_api.php，新增 $where 參數，以便取得每日訊息。 
5. Message_api.php、Message_group_user_model_api.php，新增 **取得訊息使用者** 邏輯，以便撈取每日訊息。

issue #1229
```

## 5. 查看提交歷史
- 基本語法：git log
- 比較會用的方式：git log --oneline
![upgit_20250213_1739450058.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739450058.png)
- PC端：
	- HEAD -> main：代表當前位置
- github端：
	- origin/main：遠端倉庫 (remote repository)位置
	- origin/HEAD：
		- 預設分支指標，是一個特殊的指標，通常指向遠端倉庫的預設分支 (default branch)
		- 遠端倉庫 (`origin`) 預設應該使用 `main` 作為主要分支。
		- 當你 `git clone` 時，Git 會自動讓你進入 `main` 分支。

- 所以，如果我這時候在做一次提交
	- git add.
	- git commit -m "2025.02.13"
- 查看當下紀錄：git log --oneline
![upgit_20250213_1739450312.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739450312.png)

## 6. git pull 
- 直接在遠端修改README
- 在PC端git pull

## 7. `.gitignore`

## 8. 從 Git 版本庫中移除檔案：git rm
- 還記得git的用處嗎：將【儲存的資訊】以及【對檔案隨時間的變更】視為檔案並儲存。
- 他儲存的是檔案邊更，而非檔案本身。因此，刪除檔案對git來說，也是一種【要記錄的過程】
- 因此，如果要【讓檔案直接移除git紀錄】，就需要git rm
- 示範：單純右鍵刪除檔案，查看git status
### 8.1. Lab：移除 `.gitignore` 忽略的檔案
- 如果某些檔案被 `.gitignore` 忽略了，但你想確保 Git 不再追蹤這些檔案
```
git rm -r --cached .
git add .
git commit -m "移除已被忽略的檔案"
git push
```
### 8.2. Lab：Git 移除已經被追蹤的隱私檔案（誤提交的機密檔案）
- 如果你 不小心把隱私檔案（如 API 金鑰、密碼、個人設定檔）提交到 Git，但又不能讓 Git 繼續追蹤它，你需要執行【從 Git 移除，並確保未來不會再提交】的步驟。
- STEP01：先將檔案加到gitignore
- STEP02：從 Git 版本庫中移除檔案
```
git rm --cached config.json 
git commit -m "從 Git 版本庫移除敏感檔案" 
git push origin main
```

- 如果這份檔案已經(push到GitHub/GitLab，你需要使用git filter-branch。
- 注意：這會改變 Git 歷史，可能會影響其他開發者，因此建議在小型團隊或個人專案中使用。

```
git filter-branch --force --index-filter "git rm --cached --ignore-unmatch <要清除紀錄的機密檔案>" --prune-empty --tag-name-filter cat -- --all

git push origin --force --all
```

## 9. tag
- `git tag` 用於 標記 (tag) Git 的特定版本，通常用來標記軟體的發佈版本，例如 `v1.0.0`、`v2.0.1`
- 標記特定版本（例如 `v1.0.0`）。
- 快速回到某個穩定版本（可以隨時 `checkout` 回標記）。
### 9.1. 創建 `tag`
- 創建【沒有描述的標籤】：git tag v1.0.0 
- 創建【有描述的標籤】：git tag -a v2.0.0 -m "有描述的標籤 2.0.0"


## 10. branch
- Git 的 分支 (branch) 是用來管理不同版本的變更，讓你可以同時開發多個功能，而不影響主線程 (`main` 或 `master`)。

![upgit_20250213_1739453196.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739453196.png)


### 10.1. 查看branch
- 查看本地所有分支：git branch
- 查看雲端所有分支：git branch -r
- 查看PC+雲端所有分支：git branch -a
- 示範：在github上新增分支
### 10.2. 建立分支
- 建立分支：git branch <新分支名稱>(eg：git branch feature-login)
	- 這會創建 `feature-login` 分支，但不會切換過去
	- 切換到新分支：git checkout <分支名稱>
- 推送新分支到遠端：git push -u origin <分支名稱>(eg：git push -u  feature-login)
- 刪除分支：git branch -d <分支名稱>
### 10.3. 分支合併 (merge&rebase)





- 要將分支feature-login合併到main(使用merge)
```
git checkout main # 切換到 `main` 分支
git merge feature-login # 合併 `feature-login`
```
