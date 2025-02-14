
- 確認遠端倉庫：git remote -v
```
(base) PS D:\github\git-demo> git remote -v
origin  https://github.com/kcwc1029/git-demo-cloud-to-pc.git (fetch)
origin  https://github.com/kcwc1029/git-demo-cloud-to-pc.git (push)
```
- 新增檔案 text02.txt

![upgit_20250214_1739525521.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739525521.png)

-   查看狀態：git status
```
(base) PS D:\github\git-demo> git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        text02.txt

nothing added to commit but untracked files present (use "git add" to track)
```

![upgit_20250214_1739525598.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739525598.png)

-   將變更加入暫存區 (Staging Area)：git add .

-   查看狀態：git status

![upgit_20250214_1739525672.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739525672.png)

-   將暫存區的變更存入 Git 倉庫：git commit -m "附加描述"

![upgit_20250214_1739525731.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739525731.png)

-   查看狀態：git status

![upgit_20250214_1739525760.png](https://raw.githubusercontent.com/kcwc1029/obsidian-upgit-image/main/2025/02/upgit_20250214_1739525760.png)

-   將 git 倉庫推到 github：git push




