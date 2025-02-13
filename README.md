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
- 將【儲存的資訊】以及【對檔案隨時間的變更】視為檔案並儲存。
![upgit_20250213_1739437259.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739437259.png)

### 2.1. git的三種狀態：
![upgit_20250213_1739437519.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739437519.png)

- 已修改 (Modified)
	- 檔案已經被更改，但還沒有加入版本控制系統中。
	- 這些變更仍然存在於工作目錄 (Working Directory) 中。
- 已暫存 (Staged)
	- 已修改的檔案被標記為下一次提交 (commit) 的候選對象。
	- 這些變更已經加入 暫存區 (Staging Area)，但尚未正式提交到 Git 倉庫。
- 已提交 (Committed)
	- 變更已經被永久存入 Git 倉庫 (Repository) 中，並保存在本地端的 Git 目錄。




## 3. 安裝git
- 從github新增目錄，再clone到本機
### 3.1. 安裝好後得初始設定

- 設定使用者身分
```
git config -- global user.name "John Doe"
git config -- global user.email johndoe@example.com
```

- 取得說明
```
git help 需要查詢的指令
eg：git help config
```
### 3.2. 在github 上面設定私人或公開
### 3.3. Lab：本地新增test01.txt，並上傳到github
![upgit_20250213_1739438782.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250213_1739438782.png)
- 新增檔案text.txt
- 查看狀態：git status
- 將變更加入暫存區 (Staging Area)：git add .
- 查看狀態：git status
- 將暫存區的變更存入 Git 倉庫：git commit -m "附加描述"
- 將git 倉庫推到github：git pull

## 4. Commit Message 之規範


## 5. 查看提交歷史





